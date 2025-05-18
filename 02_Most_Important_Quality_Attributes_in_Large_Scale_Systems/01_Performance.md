# 🚀 Performance in Large-Scale Systems

En esta sección iniciamos el estudio detallado de los **atributos de calidad más importantes** en los sistemas a gran escala. Uno de los primeros y más críticos es **el rendimiento (performance)**.

Aunque existen muchos atributos de calidad, el rendimiento es casi siempre relevante, sin importar el caso de uso. En esta lección aprenderás:

- Qué es el rendimiento en arquitectura de software
- Las métricas clave: **response time** y **throughput**
- Consideraciones importantes al establecer metas y analizar el rendimiento

---

## ⏱️ Métrica #1: Tiempo de respuesta (Response Time)

Cuando hablamos de rendimiento, muchas veces pensamos automáticamente en **velocidad**. Un sistema que responde rápido se percibe como de alto rendimiento.

### 📌 Definición formal

El **tiempo de respuesta** es el tiempo que transcurre **entre que un cliente envía una solicitud y recibe una respuesta**.

### 🔍 Componentes del tiempo de respuesta

1. **Processing Time (Tiempo de procesamiento):**
   - Tiempo que el sistema gasta activamente procesando la solicitud.
   - Incluye ejecución de código, consultas a la base de datos y construcción de la respuesta.

2. **Waiting Time (Tiempo de espera):**
   - Tiempo en que la solicitud o la respuesta **esperan inactivamente** en colas de red o software.
   - A veces también se denomina **latencia**, aunque este término puede prestarse a confusión.

💡 Es común llamar al response time como **end-to-end latency** para evitar ambigüedades.

### 📉 ¿Por qué es importante?

Especialmente en componentes que están en el **camino crítico de interacción del usuario**, el tiempo de respuesta impacta directamente en la experiencia del cliente. Usuarios impacientes abandonan rápidamente sistemas lentos.

---

## 📊 Métrica #2: Throughput

No todos los sistemas necesitan tiempos de respuesta rápidos. Algunos requieren **procesar grandes volúmenes de información**.

### 📌 Definición

El **throughput** es la cantidad de trabajo o datos que el sistema puede procesar **por unidad de tiempo**.

- Se puede medir en **tareas por segundo**
- O en **datos por segundo** (bits, bytes, MB, etc.)

📦 **Ejemplo**: Un sistema distribuido que procesa logs necesita **alto throughput**, no necesariamente respuesta rápida.

---

## 📌 Consideración 1: Medición correcta del tiempo de respuesta

Muchos ingenieros caen en el error de medir solo el **processing time** (tiempo dentro del código) y olvidan el **waiting time**.

### ⚠️ Problema

- El usuario experimenta una respuesta lenta.
- Pero los gráficos muestran tiempos "normales".
- Esto ocurre cuando las solicitudes esperan en colas debido a carga alta.

📊 **Ejemplo ilustrativo**:

- 2 solicitudes llegan al mismo tiempo.
- Solo una se puede procesar a la vez.
- La primera responde en 10ms.
- La segunda espera 10ms y luego se procesa (total 20ms).
- El promedio real es **15ms**, pero si solo se mide el código, ambas parecen de 10ms.

---

## 📌 Consideración 2: Distribución del tiempo de respuesta

En sistemas reales, nunca todos los usuarios experimentan el mismo tiempo de respuesta. Siempre hay una **distribución** de resultados.

### 📈 Cómo analizar esta distribución

1. **Histograma**: agrupa las muestras por rangos de tiempo.
2. **Distribución percentil**:
   - El **x-percentil** indica que x% de las solicitudes tuvieron un tiempo **menor o igual**.
   - Ejemplo: 90-percentil = 52ms → el 90% de las solicitudes respondió en menos de 52ms.

### 🎯 Métricas recomendadas

- **Median (P50)**: 50% de solicitudes son más rápidas que este valor.
- **Tail latency (P95, P99)**: cuántas solicitudes tienen respuestas excepcionalmente lentas.

> 🔍 **No uses solo promedios**. Estos **ocultan los problemas** que afectan a un porcentaje significativo de usuarios.

📌 **Ejemplo de objetivo**:
- "El 95% de las respuestas deben ser menores a 30ms"
- O más agresivo: "El 99% deben estar por debajo de 30ms"

---

## 📌 Consideración 3: Degradación del rendimiento

El rendimiento no es estático. Puede **degradarse rápidamente** al aumentar la carga.

### 🔥 ¿Qué observar?

- Punto de degradación: cuando el rendimiento empieza a decaer notablemente.
- Causas comunes:
  - **CPU al 100%**
  - **Consumo excesivo de memoria**
  - **Exceso de conexiones simultáneas**
  - **Colas saturadas**

📉 Un sistema bien diseñado **degrada suavemente**, no abruptamente.

---

## ✅ Resumen

| Concepto | Descripción |
|---------|-------------|
| 🕒 **Tiempo de respuesta** | Tiempo total desde que se hace una solicitud hasta que se recibe la respuesta. Incluye tiempo de procesamiento y espera. |
| 📦 **Throughput** | Cantidad de tareas o datos que el sistema puede procesar por unidad de tiempo. |
| 📊 **Distribución percentil** | Análisis que permite entender qué porcentaje de usuarios experimenta qué tiempos de respuesta. |
| ⚠️ **Punto de degradación** | Carga a partir de la cual el rendimiento comienza a deteriorarse significativamente. |

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/01_System_Requirements_%26_Architectural_Drivers/04_System_Constraints_in_Software_Architecture.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/02_Scalability.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
