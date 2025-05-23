# 🗄️ Almacenamiento Escalable de Datos No Estructurados

Ahora que hemos cubierto ampliamente el tema de las bases de datos, ya tenemos los conocimientos necesarios para almacenar y acceder a datos estructurados de manera eficaz.

Sin embargo, hay otro tipo de datos que aún no hemos tratado y que es igual de importante: **los datos no estructurados**.

---

## 📌 ¿Qué son los datos no estructurados?

Los **datos no estructurados** son aquellos que no siguen una estructura, esquema o modelo definido. 

Aunque en una base de datos NoSQL los documentos pueden variar en su estructura, cada registro aún tiene una forma bien definida. Pero cuando hablamos de archivos binarios como **audio, video, imágenes o documentos PDF**, sin herramientas especiales para decodificarlos, lo que tenemos es simplemente un **BLOB (Binary Large Object)**.

Algunas bases de datos permiten almacenar blobs, pero normalmente están optimizadas para datos estructurados y tienen límites estrictos de tamaño, lo que las hace inadecuadas para manejar archivos binarios grandes.

---

## 📦 Casos de uso comunes

1. **Carga de archivos por parte del usuario**  
   Imágenes, videos o documentos que suben los usuarios pueden ser procesados, comprimidos, transcodificados y trasladados para compartirlos o almacenarlos.

2. **Backups y archivado de bases de datos**  
   Copias de seguridad periódicas (snapshots) pueden almacenarse como datos no estructurados para recuperación ante desastres o auditoría legal.

3. **Alojamiento web**  
   Todo el contenido multimedia en una página web (imágenes, miniaturas, descargas) es no estructurado y debe almacenarse con capacidad de actualización frecuente.

4. **Análisis y machine learning**  
   Conjuntos de datos enormes, como lecturas de sensores IoT o imágenes satelitales, requieren almacenamiento que escale a terabytes o petabytes.

---

## 📂 Sistema de Archivos Distribuido (Distributed File System)

Un **sistema de archivos distribuido** proporciona una abstracción similar al almacenamiento local, pero sobre una red de dispositivos.

### ✅ Ventajas:
* Acceso directo como si fuera un disco local, sin APIs especiales.
* Posibilidad de modificar archivos directamente.
* Alto rendimiento para operaciones de análisis de datos.

### ❌ Desventajas:
* Límite en la cantidad de archivos (problema si hay muchos archivos pequeños).
* Difícil de exponer mediante una API web.
* Requiere abstracciones adicionales para servir contenido a navegadores.

---

## 🪣 Almacenamiento de Objetos (Object Store)

Un **object store** es una solución escalable diseñada específicamente para datos no estructurados a escala de internet.

### ✅ Ventajas:
* Escalabilidad prácticamente ilimitada.
* Soporte para objetos de gran tamaño (varios TB).
* API HTTP REST ideal para contenido web.
* **Versionado de objetos** nativo (sin herramientas externas).
* Organización plana en **buckets**, sin jerarquías de carpetas.

### Estructura de un objeto:
* **Identificador único**
* **Contenido**
* **Metadatos** (tipo, tamaño, formato)
* **Lista de control de acceso (ACL)**

### Niveles de almacenamiento en la nube:
1. **Nivel superior**: Alta disponibilidad (~99.99%), baja latencia, alta durabilidad (11 nueves). Ideal para contenido frecuente.
2. **Niveles medios**: Costos reducidos, menor disponibilidad. Útiles para backups ocasionales.
3. **Nivel bajo**: Muy bajo costo, pensado para archivado legal de largo plazo (empresas financieras, salud).

### ❌ Desventajas:
* **Los objetos son inmutables**: no se puede modificar en sitio, solo reemplazar.
* Requiere **API REST** para lectura/escritura.
* No es ideal para operaciones de alto rendimiento.

---

## 🧩 Alternativas locales y en entornos híbridos

Cuando el uso de un object store en la nube no es viable (por restricciones legales, de rendimiento o presupuesto), existen soluciones **open source** y **de terceros** que replican el comportamiento de los object stores en entornos on-premise.

Muchas de estas soluciones son compatibles con las APIs de la nube, lo que facilita implementaciones híbridas.

---

## 🔁 Replicación y durabilidad

Tanto en sistemas de archivos distribuidos como en object stores, se utiliza **replicación de datos** para asegurar que la pérdida de un dispositivo físico no implique pérdida real de datos.

---

## 🧠 Conclusión

Hemos aprendido:

* Qué son los **datos no estructurados** y por qué no son adecuados para bases de datos relacionales o NoSQL.
* Casos de uso comunes: cargas de usuarios, backups, web hosting y ML.
* Dos soluciones escalables:
  * **Sistema de archivos distribuido**: alto rendimiento, pero con limitaciones en escalabilidad web.
  * **Object store**: ideal para la web, escalabilidad extrema y versionado incorporado.

Cada solución tiene su espacio dependiendo del caso de uso. Lo importante es conocer sus ventajas y limitaciones para elegir la más adecuada.

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/05_Brewer%E2%80%99s_(CAP)_Theorem.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/05_Data_Storage_at_Global_Scale/07_Scalable_Unstructured_Data_Storage_-_Cloud_and_Open_Source_Solutions.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)