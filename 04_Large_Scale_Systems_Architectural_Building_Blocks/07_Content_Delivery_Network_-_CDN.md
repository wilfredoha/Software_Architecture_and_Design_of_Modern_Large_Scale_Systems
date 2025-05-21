# 🌍 Content Delivery Network (CDN)

## 📌 ¿Qué es un CDN?

Una **Content Delivery Network (CDN)** es una red global de servidores distribuidos geográficamente, diseñados para **acelerar la entrega de contenido** a los usuarios finales. Aunque un CDN no es un componente arquitectónico como tal, es una de las tecnologías más importantes que sustentan el internet moderno.

## 🧩 Problema que resuelve un CDN

Incluso con alojamiento web distribuido en varios centros de datos usando tecnologías como **Global Server Load Balancing**, la **latencia** sigue siendo un problema debido a:

* La **distancia física** entre el usuario final y el servidor.
* Los múltiples **saltos de red** entre routers.

Esto genera tiempos de carga lentos, afectando negativamente la experiencia de usuario.

## 🌐 Ejemplo de impacto sin CDN

Supongamos que un usuario en **Brasil** quiere acceder a nuestro sitio alojado en la **costa este de EE. UU.**:

* Latencia entre usuario y servidor: **200ms**
* Handshake TCP (3 viajes): **600ms**
* Solicitud HTTP y carga de HTML: **400ms**
* Carga asincrónica de 10 assets (CSS, JS, imágenes): **2200ms**

**Total estimado: más de 3 segundos** para cargar completamente el sitio.

> Según Google (2016), el 53% de los usuarios móviles abandonan un sitio si tarda más de 3 segundos en cargar.

## 🚀 Cómo mejora un CDN el rendimiento

Con un **CDN**, el contenido está en servidores **más cercanos al usuario**, reduciendo la latencia:

* Latencia entre usuario y CDN: **50ms**
* Handshake TCP: **150ms**
* Solicitud HTTP: **100ms**
* Carga de assets: **550ms**

**Total: menos de 1 segundo** para cargar completamente la página.

### 🧰 Técnicas que utilizan los CDNs

* **Caché en servidores perimetrales (edge servers)**
* **Almacenamiento optimizado**
* **Compresión (Gzip)**
* **Minificación de archivos JS**

## 🏛 Usos comunes de un CDN

Los CDNs se usan ampliamente para entregar:

* Sitios web estáticos y dinámicos
* Archivos multimedia (videos en vivo y bajo demanda)
* Archivos como imágenes, CSS, JS
* Servicios financieros, e-commerce, medios, redes sociales, SaaS

## ✅ Beneficios de los CDNs

* ⚡ **Rendimiento**: menor latencia y carga más rápida
* 📶 **Disponibilidad**: redundancia geográfica
* 🔐 **Seguridad**: mitigación de ataques DDoS

## 🔄 Estrategias de publicación de contenido

### 📥 Estrategia Pull

* El CDN **obtiene el contenido** desde nuestro sistema cuando un usuario lo solicita por primera vez.
* El contenido se **almacena temporalmente** (TTL configurable).
* Al expirar el TTL:
  * Si el contenido **no ha cambiado**, se renueva la expiración.
  * Si **ha cambiado**, el CDN lo actualiza desde nuestros servidores.

**Ventajas:**

* Menor mantenimiento.
* El CDN maneja automáticamente la caché.

**Desventajas:**

* Mayor latencia para el primer usuario.
* Picos de tráfico si múltiples activos expiran al mismo tiempo.
* Depende de la alta disponibilidad de nuestro sistema.

### 📤 Estrategia Push

* Nosotros **publicamos el contenido directamente** en los servidores del CDN.
* Si el contenido cambia, debemos **subir la nueva versión** manualmente o mediante automatización.

**Ventajas:**

* Casi todo el tráfico es atendido por el CDN.
* Menor dependencia de nuestro sistema backend.

**Desventajas:**

* Mayor complejidad operativa si el contenido cambia frecuentemente.
* Riesgo de mostrar contenido obsoleto si no se actualiza correctamente.

## 🧠 Conclusiones

* Un **CDN mejora el rendimiento, disponibilidad y seguridad** de nuestros servicios.
* Debemos elegir la **estrategia adecuada** (Pull o Push) según la naturaleza de nuestro contenido.
* Los CDNs son una pieza clave para ofrecer una **excelente experiencia de usuario** en la web y dispositivos móviles.

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/06_API_Gateway_Solutions_%26_Cloud_Technologies.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/08_CDN_Solutions_%26_Cloud_Technologies.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
