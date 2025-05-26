# 🧩 Event Driven Architecture

## 📘 Introducción

La **Arquitectura Orientada a Eventos (EDA)** es un estilo arquitectónico en el cual los componentes del sistema se comunican entre sí mediante eventos. A diferencia de los enfoques tradicionales, donde los servicios deben conocerse directamente y comunicarse de forma síncrona, en EDA los servicios están **desacoplados** y se comunican de forma **asíncrona** a través de eventos emitidos y consumidos.

---

## 🧱 Componentes Principales

Una arquitectura orientada a eventos generalmente consta de tres componentes fundamentales:

* **Emisores de eventos (Producers)**: generan eventos cuando ocurre una acción o cambio en el sistema.
* **Canal de eventos (Message Broker)**: transporta los eventos desde los emisores hacia los consumidores.
* **Consumidores de eventos (Consumers)**: escuchan eventos específicos y reaccionan en consecuencia.

---

## ⚙️ Ventajas de la Arquitectura Orientada a Eventos

* **Desacoplamiento entre servicios**: un servicio no necesita conocer a los demás.
* **Alta escalabilidad horizontal y organizacional**.
* **Comunicación completamente asíncrona**.
* **Fácil incorporación de nuevos servicios sin afectar los existentes**.
* **Análisis en tiempo real de flujos de datos**.

---

## 🏦 Ejemplo: Sistema Bancario

### Servicios Iniciales

1. **Frontend Service**: interfaz para que el usuario interactúe (depósitos, transferencias, etc.).
2. **Account Service**: actualiza y mantiene el saldo de cada usuario.

Cuando el frontend produce un evento como "transferencia realizada", el account service lo consume para actualizar el balance.

### Escalabilidad

Agregar nuevos servicios es simple:

* **Servicio de Notificaciones**: se suscribe a los mismos eventos y envía alertas push.
* **Servicio de Detección de Fraude**: analiza eventos en tiempo real para identificar actividades sospechosas.
* **Integraciones externas**: como servicios públicos o de nómina, que actúan como productores de eventos.

Todo esto **sin modificar** los servicios existentes.

---

## 🛰️ Event Sourcing

**Event Sourcing** es un patrón arquitectónico que consiste en almacenar todos los eventos que afectan a una entidad del negocio y reconstruir su estado a partir de ellos.

### Características

* Solo se almacenan eventos inmutables.
* El estado actual se obtiene al **reproducir** los eventos desde el inicio.
* No es necesario mantener una base de datos tradicional para el estado actual.

### Ejemplo

Si un usuario fue cargado por error con $100, se puede emitir un nuevo evento de crédito de $100 como compensación, sin modificar registros anteriores.

* Se pueden generar resúmenes periódicos (*snapshots*) para acelerar consultas.
* Permite auditoría completa del historial del sistema.

---

## 🔄 CQRS (Command Query Responsibility Segregation)

### Definición

Separación de las operaciones de escritura (**Commands**) y lectura (**Queries**) en diferentes modelos o servicios.

### Problema 1: Lecturas y escrituras simultáneas

* En bases de datos con alta carga de lectura y escritura, las operaciones compiten por recursos.
* CQRS permite optimizar **por separado**:

  * Un servicio para manejar **actualizaciones**.
  * Otro servicio para manejar **consultas**.

Ambos usan bases de datos diferentes, especializadas en su tipo de operación.

### Problema 2: Joins entre microservicios

* En microservicios, los datos están distribuidos y ya no se pueden unir fácilmente con SQL.
* CQRS permite construir un **servicio adicional (materialized view)** que:

  * Se suscribe a eventos de varios servicios.
  * Construye una vista conjunta lista para consultar.

### Ejemplo: Tienda en línea

* **Product Service**: nombre, inventario, precio, etc.
* **Review Service**: reseñas de productos.
* **Product Search Service**:

  * Combina datos de ambos servicios.
  * Responde rápidamente a búsquedas y filtros por rating.

---

## 🏁 Conclusión

La **Arquitectura Orientada a Eventos**:

* Facilita el desacoplamiento y la escalabilidad.
* Permite análisis en tiempo real.
* Soporta patrones avanzados como:

  * **Event Sourcing**: reconstrucción del estado a partir de eventos.
  * **CQRS**: separación eficiente de lectura y escritura.

Es especialmente poderosa cuando se combina con microservicios, permitiendo construir sistemas robustos, escalables y altamente adaptables.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/06_Software_Architecture_Patterns_and_Styles/03_Microservices_Architecture.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/07_Big_Data_Architecture_Patterns/01_Introduction_to_Big_Data.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
