# 🏗️ Arquitectura Lambda

## 📚 Introducción

La **Arquitectura Lambda** es un enfoque moderno y poderoso para el procesamiento de grandes volúmenes de datos. Combina lo mejor de dos mundos: el **procesamiento por lotes (batch)** y el **procesamiento en tiempo real (real-time)**, para ofrecer tanto análisis profundo como respuesta rápida.

Este modelo fue introducido por **Nathan Marz**, basado en su experiencia trabajando con grandes volúmenes de datos en Twitter y BackType.

## ⚖️ Problema con las arquitecturas tradicionales

### 🐘 Procesamiento por lotes

* Ideal para análisis históricos y modelos predictivos.
* Permite combinar datos de múltiples fuentes.
* Tiene alta latencia: los datos pueden tardar horas o más en estar disponibles para consulta.

### ⚡ Procesamiento en tiempo real

* Permite respuestas inmediatas a eventos recientes.
* Ideal para monitoreo, alertas y visualización instantánea.
* No ofrece una visión profunda del comportamiento histórico ni permite correcciones complejas.

En muchos casos, elegir solo uno de estos enfoques resulta insuficiente.

## 🔀 Motivación para la Arquitectura Lambda

Hay sistemas donde necesitamos ambas capacidades:

* **Monitoreo de métricas en servidores**: necesitamos ver logs en tiempo real, pero también comparar con el historial para detectar anomalías.
* **Aplicaciones de transporte (ej. ride sharing)**: se necesita conocer la ubicación de conductores y pasajeros en tiempo real, y también analizar datos históricos para identificar patrones de alta demanda.
* **Sistemas de publicidad (adtech)**: requieren monitorear impresiones y clics en tiempo real, pero también calcular el retorno de inversión basado en datos históricos.

## 🏗️ Capas de la Arquitectura Lambda

La arquitectura Lambda se divide en **tres capas** principales:

### 1️⃣ Capa de Batch

* Gestiona el dataset maestro, inmutable y en crecimiento.
* Usa sistemas de archivos distribuidos como HDFS.
* Realiza el procesamiento completo de los datos acumulados.
* Corrige errores, elimina duplicados y genera "batch views" precisas.
* Los resultados se almacenan en una base de datos de solo lectura para consultas.

### 2️⃣ Capa de Velocidad (Speed Layer)

* Procesa los datos recientes a medida que llegan.
* Usa colas o brokers de mensajes para manejar el flujo de eventos.
* Crea vistas en tiempo real ("real-time views") que se actualizan inmediatamente.
* Suple la latencia natural del procesamiento batch.
* No realiza correcciones ni análisis complejos.

### 3️⃣ Capa de Servicio (Serving Layer)

* Expone una interfaz para realizar consultas ad hoc.
* Fusiona los resultados de la capa batch y la capa de velocidad.
* Ofrece una vista completa y actualizada de los datos.

## 🧪 Ejemplo práctico: Sistema AdTech

En la industria de la publicidad digital, la arquitectura Lambda se puede aplicar de la siguiente manera:

* **Anunciantes**: desean mostrar anuncios de productos o eventos.
* **Productores de contenido**: sitios web que publican contenido gratuito y ceden espacio publicitario.
* **Nuestro sistema**: actúa como intermediario entre ambos.

### 🚦 Flujo del sistema

1. Un usuario abre una página web.
2. El sitio solicita un anuncio a nuestro sistema.
3. Nuestro sistema selecciona el anuncio más relevante y lo entrega al sitio.
4. Se generan tres tipos de eventos:
   * El usuario ve el anuncio.
   * El usuario hace clic en el anuncio.
   * El usuario realiza una compra.

Cada uno de estos eventos es procesado por las **capas de batch y velocidad** simultáneamente.

### 📊 Tipos de consultas posibles

* ¿Cuántos usuarios están viendo anuncios ahora? → *Responde la capa de velocidad*.
* ¿Cuántas impresiones hubo en las últimas 24 horas? → *Combina resultados de batch y velocidad*.
* ¿Cuál es el retorno de inversión de una campaña? → *Requiere análisis profundo de la capa batch*.

## ✅ Conclusión

La **Arquitectura Lambda** ofrece una solución híbrida que:

* Permite **baja latencia** y **alta precisión**.
* Combina la inmediatez del procesamiento en tiempo real con el análisis profundo del procesamiento batch.
* Es ideal para sistemas donde se requieren ambas capacidades para ofrecer valor a usuarios y al negocio.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/07_Big_Data_Architecture_Patterns/02_Big_Data_Processing_Strategies.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)

