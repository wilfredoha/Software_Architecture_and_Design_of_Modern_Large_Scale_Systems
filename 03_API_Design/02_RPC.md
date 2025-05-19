# 🧠 RPC (Remote Procedure Call)

## 📌 Introducción

En esta lección estudiaremos el primer tipo de API, conocido como **Llamada a Procedimiento Remoto** o simplemente **RPC (Remote Procedure Call)**.

Primero aprenderemos qué es y cómo funciona. Luego discutiremos sus beneficios, desventajas y cuándo es recomendable usar este estilo de API.

## ❓ ¿Qué es un RPC?

Un **RPC** permite que una aplicación cliente ejecute una subrutina ubicada en un servidor remoto.

Lo distintivo de este tipo de API es que esta invocación remota **se siente como una llamada a un método local**, desde el punto de vista del desarrollador.  
A esta característica se le conoce como **transparencia local**.

Además, muchas implementaciones de RPC soportan **múltiples lenguajes de programación**, permitiendo que aplicaciones escritas en diferentes lenguajes se comuniquen entre sí.

## ⚙️ ¿Cómo funciona un RPC?

1. **Definición de la API:**  
   Se usa un **lenguaje de descripción de interfaces** (IDL) para declarar la API y los tipos de datos que utilizará. Este lenguaje depende del framework de RPC que se use.

2. **Generación de código:**  
   A partir de la definición de la API, se genera:
   * Un **stub del servidor** (implementación del lado servidor).
   * Un **stub del cliente** (implementación del lado cliente).
   * **DTOs** (Data Transfer Objects) para representar los tipos de datos.

3. **Ejecución en tiempo de ejecución:**
   * El cliente llama al método RPC como si fuera local.
   * El **stub del cliente** serializa los datos y se conecta con el servidor.
   * El **stub del servidor** recibe los datos, los deserializa y ejecuta el método real.
   * El resultado se serializa y se devuelve al cliente.
   * El **stub del cliente** deserializa la respuesta y la entrega como si fuera el resultado de una función local.

## ✅ Beneficios de RPC

* **Transparencia local:**  
  Para el desarrollador cliente, usar un método remoto se siente igual que usar uno local.

* **Abstracción de la red:**  
  Todos los detalles del transporte de datos están ocultos para el cliente.

* **Multi-lenguaje:**  
  Algunos frameworks permiten que el servidor y el cliente estén implementados en diferentes lenguajes.

## ⚠️ Desventajas de RPC

* **Lentitud:**  
  Las llamadas remotas son mucho más lentas que las locales, pero el código se ve igual, lo cual puede engañar al desarrollador.

* **Falta de confiabilidad:**  
  La red puede fallar, el servidor puede no recibir el mensaje, o el cliente puede no recibir la respuesta.

* **Ambigüedad ante fallos:**  
  Por ejemplo, si una tienda online llama a `debitarCuenta()` y ocurre un fallo, no es claro si debe reintentar (riesgo de cobro doble) o no (riesgo de no cobrar).

### 🔧 Mitigaciones sugeridas

* **Hacer las operaciones idempotentes** cuando sea posible.
* Proveer **versiones asíncronas** de los métodos que pueden ser lentos.

## 🕵️‍♂️ ¿Cuándo usar RPC?

* Es ideal para la **comunicación entre sistemas backend**.
* Es menos común en **clientes frontend** como navegadores web.
* Útil cuando se quiere **ocultar la complejidad de la red** y enfocarse en las acciones del sistema.
* No es adecuado cuando:
  * Se quiere controlar directamente la red (cookies, headers).
  * Se necesita un estilo centrado en los datos (CRUD).

## 🧾 Conclusión

* Un RPC define su API mediante un **IDL**, y genera automáticamente el **cliente stub** y el **servidor stub**.
* Sus ventajas son:
  * Transparencia local
  * Abstracción total de la red
* Sus desventajas incluyen:
  * Lentitud
  * Falta de confiabilidad
* Se recomienda para:
  * Comunicación backend-backend
  * Integración entre servicios con lenguajes distintos
  * Cuando se desea ocultar completamente la lógica de red

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/03_API_Design/01_Introduction_to_API_Design_for_Software_Architects.md)   [Siguiente]()

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
