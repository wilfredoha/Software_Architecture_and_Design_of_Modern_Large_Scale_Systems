# 🧱 Arquitectura Multi-Tier

## 🎯 Introducción General

La **Arquitectura Multi-Tier** es uno de los patrones arquitectónicos más comunes en el desarrollo de software moderno. Organiza el sistema en múltiples **capas físicas y lógicas**, lo cual permite distribuir responsabilidades y facilitar el mantenimiento, escalabilidad y despliegue independiente por parte de diferentes equipos.

Aunque muchas veces se usan como sinónimos los términos *Multi-Tier* y *Multilayer*, en realidad son conceptos distintos:

* **Multilayer**: separación lógica dentro de una sola aplicación. A pesar de tener capas (por ejemplo, presentación, lógica, datos), se ejecuta como una unidad única.
* **Multi-Tier**: cada capa se ejecuta **físicamente** en una infraestructura distinta.

Este patrón impone algunas **restricciones importantes**:

1. **Comunicación entre capas adyacentes** mediante el **modelo cliente-servidor**, ideal para APIs RESTful.
2. **Evita saltarse capas**, promoviendo bajo acoplamiento y mayor flexibilidad evolutiva.

---

## 🧩 Variantes Comunes

### ✅ Arquitectura de Tres Capas (Three-Tier Architecture)

Una de las variantes más populares para aplicaciones web basadas en el modelo cliente-servidor.

#### 1️⃣ Capa de Presentación (Presentation Tier)

* Interfaz gráfica para el usuario.
* Ejemplos: páginas web, aplicaciones móviles, apps de escritorio.
* **No debe contener lógica de negocio**, ya que este código es visible al usuario y puede ser manipulado.

#### 2️⃣ Capa de Aplicación (Application Tier o Business Tier)

* Contiene toda la lógica de negocio.
* Procesa datos provenientes de la capa de presentación.
* Lugar central para el desarrollo backend.

#### 3️⃣ Capa de Datos (Data Tier)

* Encargada del almacenamiento y persistencia.
* Puede incluir bases de datos o archivos.
* Ejemplos: MySQL, MongoDB, almacenamiento en S3.

#### 🧪 Ventajas

* **Escalable horizontalmente** (por ejemplo, balanceo de carga en la capa de aplicación).
* Fácil de mantener: la lógica está concentrada en una sola capa.
* Ideal para: e-commerce, sitios de noticias, servicios de streaming.

#### ⚠️ Desventajas

* **Monolítica por naturaleza**: toda la lógica se encuentra en una sola base de código.
* Problemas de rendimiento (uso intensivo de CPU y memoria).
* Dificultad para escalar equipos de desarrollo (conflictos de integración, lentitud en el ciclo de vida del software).
* Modularización lógica limitada a despliegues conjuntos.

#### 🧾 Casos ideales

* Startups y organizaciones pequeñas.
* Código no muy extenso o complejo.
* Equipos de desarrollo reducidos.

---

### ✌️ Arquitectura de Dos Capas (Two-Tier Architecture)

Menos común, pero útil en ciertos contextos.

#### Estructura:

* **Capa 1**: combinación de presentación y lógica de negocio en una sola aplicación (por ejemplo, una app móvil).
* **Capa 2**: capa de datos remota para almacenamiento y respaldo.

#### Ejemplos:

* Editores de imágenes, música o documentos que funcionan localmente pero almacenan en la nube.

#### Ventajas:

* Elimina la sobrecarga de una capa intermedia.
* Experiencia más nativa y rápida.

---

### 🧱 Arquitectura de Cuatro Capas (Four-Tier Architecture)

Se agrega una capa entre la presentación y la lógica de negocio, comúnmente un **API Gateway**.

#### Funciones de la nueva capa:

* Seguridad.
* Traducción de formatos y APIs.
* Cacheo de datos.

#### Cuando usarla:

* Existen múltiples clientes con distintas necesidades.
* Se requieren diferentes contratos de API.
* Se desea separar responsabilidades como seguridad y caching.

---

## 🚫 ¿Cuándo no usar Multi-Tier?

Tener más de cuatro capas es poco común. Agregar más capas introduce latencia innecesaria y complejidad sin beneficios significativos.

---

## ✅ Conclusiones

* La **Arquitectura Multi-Tier** permite **separar responsabilidades** y escalar de forma independiente.
* La variante de **Tres Capas** es ideal para muchas aplicaciones modernas, aunque tiene limitaciones como su naturaleza monolítica.
* Existen otras variantes como la **Arquitectura de Dos Capas** (cliente pesado + servidor de datos) o la **de Cuatro Capas** (con API Gateway).
* Para sistemas más complejos o con necesidades de escalabilidad organizacional, será necesario considerar **otros patrones arquitectónicos** más flexibles.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/06_Software_Architecture_Patterns_and_Styles/01_Introduction_to_Software_Architecture_Patterns_%26_Styles.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/06_Software_Architecture_Patterns_and_Styles/03_Microservices_Architecture.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
