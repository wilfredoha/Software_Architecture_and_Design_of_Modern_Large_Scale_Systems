# 🗃️ Bases de Datos No Relacionales

## 📌 Introducción y motivación

Las bases de datos no relacionales, también conocidas como **bases de datos NoSQL**, surgieron como una alternativa moderna a las bases de datos relacionales. Su popularidad comenzó a crecer a mediados de los años 2000 como respuesta a las limitaciones de las bases de datos relacionales tradicionales.

Una de las principales desventajas de las bases de datos relacionales es que **todas las filas de una tabla deben compartir el mismo esquema**. Esto significa que, si deseamos agregar un nuevo atributo a algunos registros, debemos modificar el esquema completo de la tabla, incluso si el nuevo dato solo aplica a un subconjunto de los registros.

Las bases de datos no relacionales solucionan este problema al permitir **estructuras de datos flexibles**, donde los registros pueden tener diferentes atributos sin necesidad de alterar un esquema global.

Otro problema de las bases de datos relacionales es que **solamente ofrecen una estructura de datos: la tabla**. Si bien esto es útil para los humanos al analizar información, no es tan natural para los lenguajes de programación, que generalmente utilizan listas, arreglos, mapas y otros tipos de estructuras más familiares para los desarrolladores.

Además, las bases de datos relacionales fueron originalmente diseñadas para el almacenamiento eficiente cuando el espacio era costoso. Por el contrario, las bases de datos NoSQL **están más orientadas al rendimiento de las consultas**, permitiendo mayor velocidad en ciertos escenarios.

## ⚖️ Compromisos y desventajas

Como en todo en ingeniería de software, usar bases de datos no relacionales implica ciertos compromisos:

* **Esquemas flexibles** implican **dificultad para el análisis** de datos, ya que los registros pueden variar considerablemente en estructura.
* **Operaciones complejas como JOINs** suelen estar limitadas o no soportadas.
* **Las garantías de transacciones ACID** no siempre están disponibles, aunque existen algunas excepciones.

## 🧩 Tipos de bases de datos NoSQL

A continuación, veremos tres categorías principales de bases de datos no relacionales, cada una orientada a diferentes casos de uso.

### 🔑 Almacenes Clave/Valor

Este es el tipo más simple de base de datos NoSQL. Cada registro se compone de una clave única y un valor asociado. Este valor puede ser un entero, una cadena, una lista, un conjunto, un binario, etc.

**Ejemplos de casos de uso:**

* Contadores compartidos entre servicios
* Cachés para páginas o fragmentos de datos

Estas bases pueden verse como **diccionarios o tablas hash distribuidas** a gran escala, y son ideales cuando necesitamos accesos rápidos mediante una clave.

### 📄 Almacenes de Documentos

En este tipo de bases de datos, los datos se almacenan en **documentos con estructura interna**, como objetos JSON, YAML o XML. Cada documento puede tener atributos distintos y tipos de datos variados.

**Ejemplos de casos de uso:**

* Perfiles de usuarios con información personalizada
* Gestión de contenido generado por usuarios (comentarios, imágenes, videos)

Los almacenes de documentos son particularmente adecuados cuando **los datos no tienen una estructura fija** y pueden representarse como objetos complejos.

### 🔗 Bases de Datos de Grafos

Este tipo de base extiende el modelo de documentos al permitir **relaciones explícitas entre registros**, optimizando operaciones como traversales y análisis de relaciones.

**Ejemplos de casos de uso:**

* Detección de fraudes (usuarios lógicamente vinculados)
* Motores de recomendación (patrones de compra entre usuarios)

Las bases de datos de grafos son ideales para **navegar y analizar relaciones complejas** dentro de los datos.

## 🧠 ¿Cuándo utilizar bases de datos NoSQL?

La elección entre una base de datos relacional o no relacional depende del caso de uso y de los requisitos del sistema. Aquí algunas situaciones donde las bases de datos NoSQL sobresalen:

* **Alto rendimiento en consultas**: Ideal para cachés o resultados precomputados.
* **Grandes volúmenes de datos en tiempo real**: Por ejemplo, sistemas de big data.
* **Estructuras de datos no uniformes**: Como perfiles de usuarios o contenido multimedia generado por usuarios.

En otros casos más tradicionales o donde se requiere consistencia fuerte, **una base de datos relacional sigue siendo una opción más segura** y sencilla de mantener.

## ✅ Conclusiones

En esta sección aprendimos sobre el segundo tipo de base de datos: **las bases de datos no relacionales o NoSQL**. Exploramos sus principales ventajas:

* **Esquemas flexibles**
* **Consultas rápidas**
* **Estructuras de datos más naturales para los lenguajes de programación**

También analizamos sus tres categorías principales:

1. **Almacenes clave/valor**
2. **Almacenes de documentos**
3. **Bases de datos de grafos**

Finalmente, discutimos cuándo es recomendable optar por este tipo de base de datos y en qué escenarios puede ofrecer una ventaja significativa sobre los sistemas relacionales tradicionales.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/01_Relational_Databases_%26_ACID_Transactions.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/03_Non-Relational_Databases_-_Solutions.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
