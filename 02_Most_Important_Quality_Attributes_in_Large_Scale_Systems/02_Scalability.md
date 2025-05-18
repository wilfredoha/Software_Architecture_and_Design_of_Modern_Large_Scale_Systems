# 🚀 Scalability

En esta lección, exploraremos uno de los atributos de calidad más importantes en el diseño de sistemas modernos: la **escalabilidad**.

---

## 🎯 Motivación

La carga y el tráfico en un sistema rara vez se mantienen constantes. Pueden seguir distintos patrones:

- **Patrones estacionales:** como en sitios de comercio electrónico con picos en épocas de descuentos.
- **Eventos globales:** como búsquedas masivas en motores de búsqueda tras una noticia importante.
- **Variación diaria:** por ejemplo, herramientas usadas principalmente durante horas laborales.

A medida que el negocio crece, también lo hace el número de usuarios y, por tanto, la carga. Diseñar sistemas escalables es clave para responder a estos cambios de forma eficiente.

---

## 🧠 Definición de Escalabilidad

**Escalabilidad** es la **capacidad de un sistema para manejar una cantidad creciente de trabajo de forma sencilla y rentable agregando recursos**.

Esto se puede visualizar como una curva que relaciona el trabajo realizado con los recursos añadidos. Lo ideal sería una **escalabilidad lineal**, pero en la práctica, lo común es:

- **Sublineal:** más recursos, pero menor rendimiento por recurso.
- **Con sobrecarga:** más recursos, pero peor desempeño.

---

## 🧭 Las 3 Dimensiones de la Escalabilidad

### 🏗️ 1. Escalabilidad Vertical (Vertical Scaling)

Implica mejorar los recursos de una única máquina:

- CPUs más rápidas.
- Más memoria RAM.
- Mejor almacenamiento o red.

📈 **Ventajas:**

- Fácil de implementar.
- No requiere cambios en la aplicación.

⚠️ **Desventajas:**

- Hay un límite físico al hardware.
- Introduce un punto único de fallo.
- No proporciona tolerancia a fallos ni alta disponibilidad.

---

### 🌐 2. Escalabilidad Horizontal (Horizontal Scaling)

Implica agregar más instancias de la aplicación o base de datos en máquinas diferentes:

- Se distribuye la carga entre múltiples nodos.
- Mejora la tolerancia a fallos.

📈 **Ventajas:**

- Escalado casi ilimitado.
- Alta disponibilidad y tolerancia a fallos si se diseña correctamente.

⚠️ **Desventajas:**

- Mayor complejidad.
- Requiere cambios en el diseño de la aplicación.

---

### 🧑‍💻 3. Escalabilidad del Equipo (Organizacional)

Desde la perspectiva de desarrollo, escalar significa:

- Agregar nuevas funcionalidades.
- Corregir errores.
- Hacer despliegues frecuentes.

🔁 Con un monolito, aumentar el número de ingenieros puede reducir la productividad debido a:

- Reuniones más largas y frecuentes.
- Conflictos al fusionar código.
- Mayor curva de aprendizaje.
- Pruebas más lentas y complicadas.
- Despliegues más riesgosos.

📦 **Solución:** Modularizar y, eventualmente, dividir el sistema en **microservicios**:

- Cada equipo trabaja de forma independiente.
- Menos fricción entre desarrolladores.
- Mayor velocidad de entrega.

---

## 🧩 Comparación de las Dimensiones

| Dimensión         | Enfoque               | Ventajas principales                         | Desventajas principales                          |
|------------------|------------------------|----------------------------------------------|--------------------------------------------------|
| 🏗️ Vertical       | Mejorar una máquina     | Simple, sin cambios de código                | Límite físico, punto único de fallo              |
| 🌐 Horizontal     | Agregar más máquinas    | Alta disponibilidad, escalado flexible       | Requiere rediseño, mayor complejidad             |
| 🧑‍💻 Organizacional | Escalar el equipo        | Mayor productividad, entregas más rápidas    | Coordinación compleja sin arquitectura modular   |

Estas dimensiones son **ortogonales**, lo que significa que se pueden aplicar de forma independiente o combinadas, según las necesidades del sistema.

---

## 🧾 Conclusión

En esta lección vimos:

- 🔄 La naturaleza variable del tráfico y su impacto.
- 🧠 Una definición formal de escalabilidad.
- 🏗️🌐🧑‍💻 Las tres dimensiones de escalabilidad:
  - Vertical
  - Horizontal
  - Organizacional

La escalabilidad no solo afecta el rendimiento del sistema, sino también la capacidad de tu equipo para innovar y entregar valor de forma continua.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/01_Performance.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/03_Availability_-_Introduction_%26_Measurement.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
