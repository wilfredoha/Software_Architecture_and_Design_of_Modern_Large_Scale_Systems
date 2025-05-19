# 🧩 Introducción al Diseño de APIs para Arquitectos de Software

## 🎯 Objetivo de la Lección

En esta lección hablaremos sobre el diseño de la Interfaz de Programación de Aplicaciones (API) de un sistema. Comenzaremos con una introducción y la motivación detrás del diseño de APIs, luego abordaremos las categorías de APIs y finalizaremos con buenas prácticas y patrones para diseñar APIs eficaces.

---

## 🔍 ¿Qué es una API y por qué necesitamos diseñarla?

Una vez capturados todos los requerimientos funcionales, podemos visualizar nuestro sistema como una **caja negra** con un **comportamiento definido** y una **interfaz clara**. Esta interfaz representa un **contrato** entre los ingenieros que desarrollan el sistema y las aplicaciones clientes que lo consumen.

Dado que esta interfaz será invocada por otras aplicaciones a través de la red, la llamamos **API (Application Programming Interface)**. En sistemas de gran escala, las APIs pueden ser utilizadas por:

* Aplicaciones frontend como móviles o navegadores web
* Otros sistemas backend de empresas externas
* Sistemas internos de nuestra organización

Además, cada componente interno del sistema puede tener su propia API para interactuar con otros componentes.

---

## 🗂️ Tipos de APIs

Dependiendo del sistema y de los clientes que lo usan, las APIs se pueden clasificar en:

### 🌐 APIs Públicas
Están expuestas al público general. Cualquier desarrollador puede usarlas. Por lo general, se requiere un registro previo para mejorar el control, la seguridad y permitir la gestión de abusos.

### 🏢 APIs Privadas
Solo están disponibles internamente dentro de la organización. Permiten que otros equipos accedan al sistema sin exponerlo públicamente.

### 🤝 APIs de Socios (Partner APIs)
Son similares a las públicas, pero solo accesibles a empresas o usuarios con un acuerdo comercial con nosotros.

---

## ✅ Beneficios de un API Bien Definido

* **Aceleración del desarrollo** por parte de los clientes sin necesidad de conocer detalles internos.
* **Facilita la integración temprana**, incluso antes de que el sistema esté completamente implementado.
* **Guía el diseño interno** al definir los puntos de entrada del sistema.

---

## 🛠️ Buenas Prácticas y Patrones para Diseñar APIs

### 🔒 Encapsulamiento y Abstracción
La API debe ocultar completamente la implementación interna. Si el cliente necesita conocer la lógica del negocio para usarla, la API está mal diseñada.

### 🔗 Desacoplamiento
Debemos poder cambiar la implementación interna sin romper el contrato con los clientes existentes.

### 🧠 Facilidad de Uso
Una buena API debe ser:
* Fácil de entender y usar
* Difícil de usar incorrectamente
* Coherente en toda su estructura

Evita múltiples formas de hacer la misma operación y usa nombres descriptivos.

### ♻️ Idempotencia
Las operaciones idempotentes producen el mismo resultado si se ejecutan una o varias veces. Esto es esencial para sistemas distribuidos donde los mensajes pueden perderse o duplicarse.

Ejemplos:
* ✅ Actualizar una dirección → Idempotente
* ❌ Aumentar el saldo en $100 → No idempotente

### 📄 Paginación
Permite devolver resultados en segmentos para evitar respuestas muy grandes. El cliente especifica:
* Tamaño máximo de cada página
* Offset o posición de inicio

Esto mejora el rendimiento y la experiencia de usuario.

### ⏳ Operaciones Asíncronas
Para tareas de larga duración (como generación de reportes, análisis de big data o compresión de videos), es mejor usar APIs asíncronas. El cliente recibe una respuesta inmediata con un identificador para consultar el estado del proceso.

### 🆎 Versionado de API
Permite hacer cambios incompatibles sin afectar a los clientes existentes. Se pueden mantener varias versiones activas al mismo tiempo, descontinuando las anteriores de forma progresiva.

---

## 🧾 Resumen

En esta lección:

* Definimos una **API** como un contrato que permite a otros sistemas usar nuestro servicio sin conocer su implementación interna.
* Identificamos tres tipos de APIs: **públicas**, **privadas** y **de socios**.
* Exploramos buenas prácticas como:
  - Encapsulamiento
  - Facilidad de uso
  - Idempotencia
  - Paginación
  - Operaciones asíncronas
  - Versionado de API

Estas prácticas son fundamentales para construir APIs robustas, escalables y fáciles de mantener.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/05_SLA%2C_SLO%2C_SLI.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/03_API_Design/02_RPC.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
