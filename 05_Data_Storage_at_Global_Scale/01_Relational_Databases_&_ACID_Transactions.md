# 🧩 Bases de Datos Relacionales y Transacciones ACID

## 🎯 Introducción

Ahora que dominamos los bloques arquitectónicos más importantes en cuanto a tráfico, gestión de APIs y entrega de contenido, es momento de hablar sobre **bases de datos**.

Existe una gran variedad de opciones, lo que puede ser abrumador. Por eso, en lugar de seguir la moda, aprenderemos un **método sistemático para elegir la base de datos adecuada** para cada caso de uso.

En esta sección comenzaremos con el **primer tipo de base de datos**, llamada **base de datos relacional**. Veremos qué son, sus ventajas, desventajas, y cuándo conviene utilizarlas.

---

## 🗃️ ¿Qué es una base de datos relacional?

Una base de datos relacional almacena los datos en **tablas**. Cada fila representa un registro, y todas las filas están relacionadas entre sí a través de un conjunto predefinido de columnas.

Cada columna tiene un **nombre**, un **tipo** de datos y puede tener **restricciones**. A este conjunto estructurado se le conoce como **esquema**.

Cada registro es identificado de forma única mediante una **clave primaria**, que puede estar compuesta por una o varias columnas.

Gracias a este esquema fijo, se puede utilizar un lenguaje robusto para consultar y modificar los datos. El lenguaje estándar es **SQL (Structured Query Language)**.

---

## 📚 Ventajas de las bases de datos relacionales

* Soportan **consultas complejas** y flexibles mediante SQL.
* **Eliminan duplicación de datos** mediante relaciones entre tablas.
* Su estructura en tablas es **natural y fácil de entender** para humanos.
* Soportan **transacciones ACID**, una propiedad esencial para la confiabilidad de datos.

---

## 🔐 Transacciones ACID

Las bases de datos relacionales garantizan propiedades ACID:

### 🔸 Atomicidad
* Todas las operaciones de una transacción ocurren **completamente o no ocurren en absoluto**.
* Ejemplo: una transferencia de dinero entre dos cuentas debe reflejarse de forma total o no suceder.

### 🔸 Consistencia
* Una transacción mantiene el sistema en un **estado válido**, respetando las restricciones.
* Ejemplo: si un usuario no puede tener más de $1000, una transacción que lo sobrepase será rechazada.

### 🔸 Aislamiento
* Las transacciones concurrentes no afectan el resultado entre sí.
* Evita que una transacción vea datos intermedios de otra.

### 🔸 Durabilidad
* Una vez completada una transacción, sus efectos son **persistentes** incluso ante fallos del sistema.

---

## 🛒 Ejemplo práctico

Supón que tenemos una tienda en línea con una tabla `Productos` y una tabla `Órdenes`. En lugar de duplicar los datos del producto en cada orden, guardamos solo su ID y usamos una **operación JOIN** para obtener la información combinada.

Esto **ahorra espacio**, mejora el mantenimiento y facilita los reportes.

---

## ❌ Desventajas de las bases de datos relacionales

* El **esquema es rígido**: debe definirse antes de usar una tabla.
* Cambiar el esquema requiere **tiempo de mantenimiento** y puede afectar la disponibilidad.
* Son **más complejas de escalar y mantener**.
* Las consultas pueden ser **más lentas** comparadas con bases de datos no relacionales.

---

## 📌 ¿Cuándo usar una base de datos relacional?

Usa una base de datos relacional si:

* Necesitas **consultas complejas y flexibles**.
* Requieres **transacciones ACID** confiables.
* Tu modelo de datos **naturaleza tabular y estructurada**.

Evítalas si:

* No hay relaciones claras entre los registros.
* Lo más importante es la **velocidad de lectura**.

---

## 🧠 Conclusión

Las bases de datos relacionales (también llamadas **bases SQL**) ofrecen una forma estructurada y poderosa de almacenar y consultar datos, gracias a:

* Consultas SQL avanzadas.
* Relaciones entre tablas que evitan duplicación.
* Un modelo intuitivo para humanos.
* Garantías de transacciones ACID.

Sin embargo, también tienen limitaciones como su rigidez y complejidad de escalado.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/08_CDN_Solutions_%26_Cloud_Technologies.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/02_Non-Relational_Databases.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)