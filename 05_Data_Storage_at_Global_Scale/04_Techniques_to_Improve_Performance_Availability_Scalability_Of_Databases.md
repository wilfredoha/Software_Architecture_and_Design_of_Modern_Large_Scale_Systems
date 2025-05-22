# 🧠 Técnicas para Mejorar el Rendimiento, la Disponibilidad y la Escalabilidad de las Bases de Datos

Ahora que entendemos los diferentes tipos de bases de datos disponibles y cómo elegir la adecuada para cada caso de uso, es momento de estudiar cómo mejorar su comportamiento dentro de sistemas a gran escala.

En esta sección aprenderemos tres técnicas clave para mejorar el **rendimiento**, la **disponibilidad** y la **escalabilidad** de una base de datos:

* **Indexación**
* **Replicación**
* **Particionamiento (Sharding)**

---

## ⚡ 1. Indexación

**Objetivo:** Mejorar el rendimiento de las consultas acelerando las operaciones de búsqueda y recuperación.

### ¿Qué es un índice?

Un **índice** es una estructura auxiliar creada a partir de una columna (o conjunto de columnas) que permite localizar registros de forma eficiente, evitando escaneos completos de la tabla.

### Ventajas

* Recuperación más rápida de registros.
* Soporte para ordenamientos eficientes.
* Búsqueda en **tiempo sublineal** (por ejemplo: `O(log n)` o `O(1)`).

### Ejemplo práctico

Supongamos una tabla muy grande con información de usuarios. Si deseamos obtener todos los usuarios que viven en una ciudad específica, sin un índice, deberíamos escanear toda la tabla. Pero si tenemos un índice por ciudad:

* Una **tabla hash** permitiría localizar los usuarios por ciudad en tiempo constante.
* Un **árbol B (B-Tree)** permitiría búsquedas rápidas y también consultas ordenadas por edad, apellido, ingresos, etc.

### Índices compuestos

Podemos crear índices a partir de múltiples columnas. Por ejemplo: *(ciudad, apellido)* nos permite encontrar rápidamente todos los usuarios que viven en una ciudad **y** tienen un apellido específico, sin escanear resultados intermedios.

### Consideraciones

* **Ventaja:** Consultas más rápidas.
* **Costo:** Mayor uso de espacio y menor rendimiento en operaciones de escritura (insertar/actualizar).
* Aplicable tanto a bases de datos relacionales como no relacionales (ej. MongoDB).

---

## 🛡️ 2. Replicación

**Objetivo:** Mejorar la **disponibilidad** y el **rendimiento** del sistema mediante la duplicación de los datos.

### ¿Qué es la replicación?

Es el proceso de mantener **copias sincronizadas** de la base de datos en múltiples servidores. Cada copia se denomina **réplica**.

### Ventajas

* **Alta disponibilidad:** Si una réplica falla, otras pueden continuar atendiendo consultas.
* **Mayor rendimiento:** Las consultas pueden distribuirse entre réplicas para aumentar el **throughput** del sistema.

### Consideraciones

* Introduce **complejidad** en las operaciones de escritura: mantener la **consistencia** entre réplicas es un reto.
* Las bases de datos distribuidas requieren diseño cuidadoso, sobre todo a gran escala.
* Soportado en la mayoría de bases de datos modernas (relacionales y no relacionales).

---

## 🧩 3. Particionamiento (Sharding)

**Objetivo:** Mejorar la **escalabilidad** y el **rendimiento** al dividir los datos entre múltiples instancias de base de datos.

### ¿Qué es el particionamiento?

A diferencia de la replicación (donde todos los nodos tienen la misma información), en el particionamiento se **divide** la base de datos en partes llamadas **shards**, y cada shard contiene un subconjunto diferente de los datos.

### Ventajas

* **Escalabilidad horizontal:** Permite almacenar más datos distribuyéndolos entre múltiples máquinas.
* **Consultas paralelas:** Diferentes shards pueden atender diferentes consultas simultáneamente.

### Consideraciones

* Aumenta la complejidad: es necesario un sistema para **dirigir las consultas al shard correcto**.
* Desbalance entre shards puede generar cuellos de botella.
* Muy común en bases de datos no relacionales, que fueron diseñadas pensando en este modelo.
* En bases de datos relacionales, su uso depende del soporte del motor y del tipo de consultas (por ejemplo, `JOINs` o `transacciones` son más difíciles de manejar entre shards).

---

## 🧠 Observación final

Estas tres técnicas son **independientes** entre sí y **complementarias**. En sistemas reales de gran escala, **indexación**, **replicación** y **particionamiento** suelen utilizarse **conjuntamente** para lograr bases de datos robustas, disponibles, escalables y de alto rendimiento.

---

## 📚 Resumen

* **Indexación:** Mejora el rendimiento de lectura creando estructuras auxiliares para búsquedas rápidas.
* **Replicación:** Mejora la disponibilidad y el rendimiento distribuyendo copias de la base de datos.
* **Particionamiento:** Mejora la escalabilidad dividiendo los datos entre múltiples nodos.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/03_Non-Relational_Databases_-_Solutions.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/05_Brewer%E2%80%99s_(CAP)_Theorem.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
