# ⚙️ Fault Tolerance & High Availability

## 📌 Introducción

En la lección anterior, hablamos sobre **disponibilidad** en general y, en particular, sobre la **importancia de la alta disponibilidad** tanto para los usuarios como para el negocio.

En esta lección, nos enfocaremos en:
* Qué impide que obtengamos alta disponibilidad de forma predeterminada.
* Qué medidas y tácticas podemos tomar para mejorar la disponibilidad de nuestro sistema.

---

## 🚨 Fuentes de Fallas

Existen tres **categorías principales de fallas** que amenazan la disponibilidad del sistema:

### 1. 🧑‍💻 Errores Humanos
Incluyen:
* Subir una configuración defectuosa a producción.
* Ejecutar comandos o scripts incorrectos.
* Desplegar versiones no suficientemente testeadas del software.

### 2. 💾 Errores de Software
Incluyen:
* Recolectores de basura muy largos.
* Excepciones como:
  - OutOfMemory
  - NullPointerException
  - Fallos de segmentación (segmentation faults)

### 3. 🖥️ Fallos de Hardware
Incluyen:
* Fallas físicas en servidores, routers o dispositivos de almacenamiento.
* Cortes de energía por desastres naturales.
* Problemas de red por infraestructura deficiente o congestión.

---

## 🛡️ Tolerancia a Fallos: Clave para la Alta Disponibilidad

A pesar de las mejoras en:
* Revisión de código
* Pruebas y procesos de despliegue
* Mantenimiento continuo del hardware

...las fallas **son inevitables**.

La mejor estrategia para alcanzar **alta disponibilidad** es la **tolerancia a fallos**, que permite que el sistema permanezca **operativo y disponible** incluso si uno o varios componentes fallan.

Puede operar con:
* Rendimiento normal
* Rendimiento degradado
* Pero **sin volverse completamente inoperativo**

---

## 🧠 Tres Tácticas para Lograr Tolerancia a Fallos

### 1. 🚫 Prevención de Fallos

Eliminando **Single Points of Failure (SPOF)**:

Ejemplos comunes:
* Aplicación corriendo en un único servidor.
* Base de datos en una única instancia.

#### Solución: Replicación y Redundancia
* Ejecutar múltiples instancias de la aplicación en varios servidores.
* Base de datos replicada en múltiples nodos.

#### Tipos de Redundancia:
* **Espacial:** múltiples réplicas en diferentes nodos físicos.
* **Temporal:** repetir una operación varias veces hasta éxito o abandono.

#### Estrategias:
* **Active-Active:** todas las réplicas reciben tráfico y están sincronizadas.
  - ✅ Alta escalabilidad
  - ⚠️ Difícil de coordinar
* **Active-Passive:** solo una réplica principal recibe tráfico, las otras sincronizan pasivamente.
  - ✅ Fácil de implementar
  - ⚠️ No escalable horizontalmente

---

### 2. 🔍 Detección e Aislamiento de Fallos

Permite **identificar componentes defectuosos** y **aislarlos del sistema**.

#### Monitoreo y Health Checks
* Sistemas de monitoreo envían **mensajes de verificación de estado**.
* Alternativamente, se usan **heartbeats** periódicos desde las instancias.

#### Posibles métricas:
* Tasa de errores por minuto.
* Tiempo de respuesta elevado.
* Caídas de comunicación.

> ⚠️ Es preferible tener falsos positivos que falsos negativos.

---

### 3. ♻️ Recuperación de Fallos

La disponibilidad también depende del **tiempo de recuperación**.

#### Estrategias de recuperación:
* **Redireccionar tráfico** a nodos sanos.
* **Reiniciar instancias** con problemas.
* **Rollbacks**:
  - A versiones estables anteriores del software.
  - A estados válidos anteriores en bases de datos.

---

## ✅ Conclusiones

* Las fallas pueden venir de errores humanos, de software o hardware.
* La **tolerancia a fallos** es clave para alcanzar **alta disponibilidad**.
* Las tres tácticas esenciales son:
  1. Prevención de fallos
  2. Detección y aislamiento
  3. Recuperación ante fallos

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/03_Availability_-_Introduction_%26_Measurement.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/05_SLA%2C_SLO%2C_SLI.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
