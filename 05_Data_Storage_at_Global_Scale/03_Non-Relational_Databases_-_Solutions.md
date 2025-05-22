# 📦 Non-Relational Databases - Soluciones

Este documento complementa la introducción a las bases de datos no relacionales, presentando ejemplos concretos de soluciones tecnológicas clasificadas según su tipo.

---

## 🔑 Almacenes Clave/Valor (Key/Value Stores)

Los almacenes clave/valor son ideales para aplicaciones que requieren alta velocidad de lectura y escritura, como sistemas de caché, contadores o almacenamiento de sesiones.

### Ejemplos comunes:

* **Redis**  
  Popular por su velocidad y soporte para estructuras de datos avanzadas en memoria. Muy utilizado para caché, pub/sub y colas de mensajes ligeras.

* **Aerospike**  
  Optimizado para cargas de trabajo de alto rendimiento con baja latencia. Usado frecuentemente en publicidad en tiempo real y análisis financiero.

* **Amazon DynamoDB**  
  Servicio gestionado de AWS altamente escalable, ideal para aplicaciones con necesidades impredecibles o crecientes de almacenamiento y rendimiento.

---

## 📄 Almacenes de Documentos (Document Stores)

Este tipo de base de datos permite almacenar y consultar documentos estructurados (por ejemplo, JSON), permitiendo una mayor flexibilidad que las bases de datos relacionales.

### Ejemplos comunes:

* **Cassandra**  
  Aunque a menudo se considera una base de datos de columnas, también se adapta al modelo de documentos. Escala horizontalmente y es ideal para grandes volúmenes de datos distribuidos.

* **MongoDB**  
  La solución más popular de bases de datos de documentos. Soporta esquemas dinámicos y es ampliamente utilizada para aplicaciones web modernas y microservicios.

---

## 🧠 Bases de Datos de Grafos (Graph Databases)

Estas bases de datos están diseñadas para representar y consultar relaciones complejas entre datos. Son ideales para casos de uso que involucran redes, conexiones y dependencias.

### Ejemplos comunes:

* **Amazon Neptune**  
  Base de datos de grafos completamente gestionada por AWS. Soporta los modelos Property Graph y RDF. Ideal para sistemas de recomendaciones y detección de fraudes.

* **Neo4j**  
  Una de las bases de datos de grafos más maduras y populares del mercado. Muy utilizada para representar relaciones sociales, motores de recomendación y análisis de redes.

---

## 🧭 Conclusión

La elección de una base de datos no relacional debe basarse en el caso de uso específico, considerando las ventajas de cada tipo:

* **Key/Value Stores**: ideales para almacenamiento simple, rápido y distribuido.
* **Document Stores**: permiten esquemas flexibles y estructuras anidadas.
* **Graph Databases**: diseñadas para explorar relaciones complejas entre entidades.

Para arquitecturas modernas, no es raro encontrar sistemas híbridos que combinan bases de datos relacionales y no relacionales según las necesidades funcionales y no funcionales del sistema.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/02_Non-Relational_Databases.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/04_Techniques_to_Improve_Performance_Availability_Scalability_Of_Databases.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
