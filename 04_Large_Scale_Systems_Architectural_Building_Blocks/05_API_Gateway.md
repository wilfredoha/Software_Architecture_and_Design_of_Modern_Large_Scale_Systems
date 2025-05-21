# 🧭 API Gateway

## 📌 Introducción

En esta lección aprendimos sobre el **API Gateway**, un bloque fundamental de construcción arquitectónica y un patrón de diseño utilizado ampliamente por sistemas a gran escala en la industria. Antes de explorar sus ventajas, es clave comprender el problema que resuelve.

Imaginemos que construimos una plataforma de **videos compartidos y transmisión**, donde los usuarios pueden subir, ver y comentar videos. Al principio, teníamos un solo servicio encargado de servir el frontend y manejar perfiles, suscripciones, notificaciones, almacenamiento, transmisión de videos y comentarios, además de la seguridad y autenticación.

Con el tiempo, esta única base de código se volvió compleja, por lo que la dividimos en **múltiples servicios**, cada uno enfocado en una responsabilidad específica.

## ⚙️ El Problema

Dividir el sistema trae consecuencias:

* La única API original ahora se divide en varias APIs.
* El código del cliente (frontend) debe conocer la estructura interna del sistema para llamar a los servicios correctos.
* Cada servicio debe implementar su propia seguridad, autenticación y autorización, lo que genera **duplicación y sobrecarga de rendimiento**.

## 🧱 Solución: API Gateway

El **API Gateway** es un **servicio de gestión de APIs** que se coloca entre el cliente y los servicios backend. Este patrón se conoce como **composición de APIs**, donde todas las APIs internas se exponen como una sola API externa unificada.

### ✅ Beneficios del API Gateway

#### 🔐 Seguridad Centralizada

* Consolidación de autenticación y autorización.
* Terminación SSL.
* Control de accesos por roles.
* Prevención de ataques DoS mediante **limitación de tasa (rate limiting)**.

#### 🚀 Mejoras en el Rendimiento

* **Routing de peticiones**: una sola llamada del cliente puede ser descompuesta internamente hacia múltiples servicios.
* **Agregación de respuestas** en una sola respuesta al cliente.
* **Caché** de contenido y respuestas, reduciendo el tiempo de respuesta.

#### 🧭 Monitoreo y Observabilidad

* Visibilidad en tiempo real del tráfico y carga.
* Generación de alertas ante anomalías.
* Mejora de la **disponibilidad** del sistema.

#### 🔁 Traducción de Protocolos

* Exponer una API REST con JSON mientras que internamente se usan RPC, XML u otros protocolos.
* Facilita la integración con sistemas externos, como plataformas de publicidad o distribución de contenido.

## 🚫 Antipatrones y Consideraciones

### ❌ No incluir lógica de negocio

* El API Gateway **no debe contener lógica de negocio**.
* Su rol es enrutar, autenticar y componer APIs. Las decisiones deben residir en los servicios backend.

### ⚠️ Punto Único de Falla

* Todo el tráfico pasa por el API Gateway, lo que puede convertirlo en un **Single Point of Failure**.
* Solución: múltiples instancias del gateway detrás de un **balanceador de carga** y procesos cuidadosos de despliegue.

### ⛔ Evitar el bypass del API Gateway

* Acceder directamente a servicios backend rompe la **abstracción del Gateway**.
* Impide actualizaciones seguras y desacopla mal el sistema.
* Se debe evitar **optimizar prematuramente** sacrificando la arquitectura.

## 📚 Resumen

En esta lección aprendimos que el **API Gateway**:

* Es un patrón fundamental en sistemas distribuidos.
* Nos ayuda a unificar las APIs internas en una sola interfaz para el cliente.
* Aporta beneficios como **seguridad, rendimiento, observabilidad y flexibilidad**.
* Debe ser usado con buenas prácticas, sin lógica de negocio y con despliegues controlados.
* No debe ser evitado ni omitido para preservar su valor como capa de abstracción.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/04_Message_Brokers_Solutions_%26_Cloud_Technologies.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/06_API_Gateway_Solutions_%26_Cloud_Technologies.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
