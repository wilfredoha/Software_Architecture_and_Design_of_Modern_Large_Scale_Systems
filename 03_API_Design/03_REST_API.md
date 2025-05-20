
# 🌐 REST API

## 📘 Introducción

En esta sección aprenderemos sobre otro estilo de APIs llamado **REST API**. Comenzaremos entendiendo los conceptos generales y beneficios, y más adelante aprenderemos cómo definir una API REST paso a paso.

## 🧠 ¿Qué es una REST API?

REST (Representational State Transfer) es un **estilo arquitectónico** para diseñar APIs que son fáciles de usar y entender. Fue propuesto por Roy Fielding en su disertación doctoral en el año 2000.

**No es un estándar ni un protocolo**, sino un conjunto de restricciones arquitectónicas y buenas prácticas para definir APIs web que soportan atributos de calidad como:

* Escalabilidad
* Alta disponibilidad
* Buen rendimiento

Una API que sigue estas restricciones se conoce como una **API RESTful**.

## 🔄 Comparación entre RPC y REST

**RPC (Remote Procedure Call):**

* Basado en métodos expuestos al cliente.
* Ampliar la API = añadir más métodos.

**REST:**

* Enfocado en recursos con nombre.
* Manipulación a través de un número limitado de métodos estándar.
* Cliente solicita una **representación del estado actual** del recurso.
* Utiliza generalmente el protocolo **HTTP**.

Ejemplo: Si una revista en línea ofrece su **página de inicio** como recurso, la representación puede ser una página HTML con artículos e imágenes. Pero internamente, esa página puede estar compuesta por múltiples entidades en distintas bases de datos o servicios.

## 🔗 HATEOAS (Hypermedia as the Engine of Application State)

REST APIs pueden ser **dinámicas** gracias a los enlaces hipermedia:

* La respuesta de un recurso puede incluir **enlaces a otras operaciones posibles**.
* Ejemplo: Una API de correo puede responder con los mensajes del usuario y enlaces para responder, reenviar o eliminar.

## ⚙️ Atributos de Calidad en REST APIs

1. **Sin estado (Stateless)**:
   * El servidor no mantiene información de sesión.
   * Facilita la escalabilidad: múltiples servidores pueden manejar las solicitudes sin coordinarse.

2. **Cacheabilidad**:
   * Las respuestas pueden marcarse como **cacheables o no**.
   * Reduce la carga del sistema y mejora el rendimiento.

## 📁 Recursos en REST

* Cada recurso tiene una **URI única**.
* Organizados jerárquicamente con `/`.
* Tipos:
  * **Recurso simple**: Tiene estado y puede contener subrecursos.
  * **Recurso colección**: Conjunto de recursos del mismo tipo.

**Ejemplo jerárquico (servicio de streaming de películas):**

```
/movies
/movies/{movieId}
/movies/{movieId}/actors
/movies/{movieId}/reviews
/actors/{actorId}/profile
```

## 🧾 Representación de Recursos

Puede ser:

* JSON (el más común)
* HTML
* Imagen
* Archivo binario
* Código ejecutable (JavaScript)

## ✅ Buenas Prácticas al Nombrar Recursos

1. **Usar sustantivos, no verbos**:
   * Las acciones se representan con métodos HTTP, no con el nombre del recurso.

2. **Colecciones en plural, recursos simples en singular**:
   * `/movies` (colección), `/movies/123` (recurso simple)

3. **Nombres claros y significativos**:
   * Evitar nombres genéricos como `/items`, `/entities`.

4. **Identificadores únicos y amigables con URLs**.

## 🧰 Métodos REST (mapeados a HTTP)

| Operación | Método HTTP | Descripción                                 |
|-----------|-------------|---------------------------------------------|
| Crear     | POST        | Crear un nuevo recurso                      |
| Leer      | GET         | Obtener el estado del recurso               |
| Actualizar| PUT         | Actualizar un recurso existente             |
| Eliminar  | DELETE      | Eliminar un recurso                         |

* `GET` es **seguro** (no cambia estado) e **idempotente**.
* `PUT` y `DELETE` son **idempotentes**.
* `POST` puede ser cacheable si se definen correctamente los headers.

## 🧪 Ejemplo Paso a Paso: API de Streaming de Películas

### 1. Identificar Entidades

* `users`
* `movies`
* `reviews`
* `actors`

### 2. Mapear Entidades a URIs

* `/users`
* `/movies`
* `/movies/{movieId}/reviews`
* `/movies/{movieId}/actors`
* `/actors/{actorId}`

### 3. Elegir Representaciones

* JSON es el formato común.
* Ejemplo de representación de `/movies`:

```
json
{
  "movies": [
    { "id": 1, "title": "Inception" },
    { "id": 2, "title": "Interstellar" }
  ]
}
```

### 4. Asignar Métodos HTTP
POST /users → crear nuevo usuario

GET /users/123 → obtener info del usuario

PUT /users/123 → actualizar perfil del usuario

DELETE /users/123 → eliminar usuario

Repetir este proceso para todos los recursos.

🏁 Conclusión
REST es un estilo arquitectónico enfocado en recursos.

Utiliza HTTP y métodos estándar.

Permite lograr sistemas escalables, disponibles y eficientes.

Requiere organizar recursos con URIs significativas.

Facilita la evolución y mantenimiento del sistema.

---

[Anterior]()   [Siguiente]()

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)