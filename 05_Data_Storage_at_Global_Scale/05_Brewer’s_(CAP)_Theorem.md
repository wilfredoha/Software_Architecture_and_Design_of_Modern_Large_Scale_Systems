# ⚖️ Brewer’s (CAP) Theorem

## 📘 Introducción

En la lección anterior aprendimos técnicas para mejorar el **rendimiento**, la **escalabilidad** y la **disponibilidad** de las bases de datos. Algunas de estas técnicas convirtieron nuestra base de datos en una **base de datos distribuida**.

Aunque los detalles de implementación y gestión de bases de datos distribuidas están fuera del alcance de este curso, hay un concepto fundamental que todo **arquitecto de software** y **diseñador de sistemas** debe comprender: el **Teorema CAP**, también conocido como **Teorema de Brewer**.

## 📚 ¿Qué es el Teorema CAP?

El Teorema CAP fue introducido por el profesor **Eric Brewer** a finales de los años 90. Afirma que:

> En presencia de una **partición de red**, una base de datos distribuida **no puede garantizar simultáneamente** **consistencia** y **disponibilidad**.

Es decir, en presencia de un fallo en la comunicación entre réplicas, **solo se puede elegir entre garantizar la consistencia o garantizar la disponibilidad**, pero no ambas.

## 🧠 Intuición detrás del Teorema CAP

Supongamos que tenemos una base de datos replicada en varios nodos para lograr alta disponibilidad. Esta base de datos es un **almacenamiento clave-valor NoSQL**, y contiene un contador que múltiples servicios leen e incrementan.

Cuando la red funciona bien, cualquier actualización al contador se propaga entre las réplicas sin problema. Por ejemplo:

* El Servicio A incrementa el contador en la Réplica 1.
* Si el Servicio B consulta la Réplica 2, esta puede comunicarse con las otras réplicas y devolver el valor actualizado.

Este comportamiento es posible **si todas las réplicas pueden comunicarse entre sí**.

Pero, ¿qué ocurre si se produce una **partición de red** y, por ejemplo, la Réplica 3 queda aislada?

### 🎯 Dos opciones ante una partición de red:

1. **Priorizar la disponibilidad**: La Réplica 3 responde con su valor local, aunque esté desactualizado → **inconsistencia garantizada**.
2. **Priorizar la consistencia**: La Réplica 3 devuelve un error indicando que no puede garantizar un valor actualizado → **disponibilidad comprometida**.

Esto es precisamente lo que establece el Teorema CAP:  
En presencia de una partición de red, debemos elegir entre **consistencia** o **disponibilidad**.

## 🧾 Definiciones formales

### ✅ Consistencia

Cada solicitud de lectura devuelve **el valor más reciente** escrito o un error.  
Todos los clientes ven **el mismo valor al mismo tiempo**, sin importar qué réplica consulten.

### ☑️ Disponibilidad

Cada solicitud recibe una **respuesta válida y sin error**, pero **no se garantiza** que el valor sea el más reciente.

### 🧱 Tolerancia a particiones

El sistema continúa operando **a pesar de la pérdida o retraso de mensajes** en la red entre los nodos.

## 🧩 Interpretación práctica

El Teorema CAP implica que al configurar o elegir una base de datos distribuida, **debemos sacrificar una de las tres propiedades**:

* **C + A (sin tolerancia a particiones)**: no es viable en sistemas distribuidos reales.
* **C + P (sin disponibilidad)**: los usuarios pueden recibir errores durante una partición.
* **A + P (sin consistencia)**: puede haber respuestas con datos desactualizados.

### 🤔 ¿Podemos tener C y A?

Sí, **solo si no existe una partición de red**, es decir, si la base de datos es **centralizada** (monolítica, en una sola máquina). Pero esto **no escala** ni ofrece **tolerancia a fallos**.

En sistemas distribuidos reales, **la tolerancia a particiones es obligatoria**, por lo tanto **debemos elegir entre consistencia y disponibilidad**.

## ⚖️ ¿Cuándo elegir consistencia sobre disponibilidad?

* En un sistema de **inventario** de una tienda online:
  * Si solo queda 1 unidad en stock, ambos clientes deben ver el mismo valor.
  * Se prioriza la **consistencia**.

* En un sistema de **redes sociales**:
  * El contador puede representar "likes" o "vistas".
  * Es aceptable mostrar un número ligeramente desactualizado.
  * Se prioriza la **disponibilidad**.

## 🎚️ No todo es blanco o negro

En la práctica, las bases de datos distribuidas permiten **ajustar el equilibrio** entre consistencia y disponibilidad mediante configuraciones como:

* Número de réplicas que deben confirmar una escritura.
* Tiempo máximo de espera para lectura consistente.
* Reintentos automáticos.

Cada vez que aumentamos la **consistencia**, disminuimos la **disponibilidad**, y viceversa.

## 🧠 Conclusión

El **Teorema CAP** es un ejemplo clave de los **compromisos** (trade-offs) que debemos hacer al diseñar sistemas distribuidos a gran escala.

Debemos considerar cuidadosamente estos compromisos al definir los **atributos de calidad** durante la fase de diseño de arquitectura.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/04_Techniques_to_Improve_Performance_Availability_Scalability_Of_Databases.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/06_Scalable_Unstructured_Data_Storage.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
