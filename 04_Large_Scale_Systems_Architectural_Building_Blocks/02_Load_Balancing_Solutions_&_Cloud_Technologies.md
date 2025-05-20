# 🌐 Soluciones de Balanceo de Carga y Tecnologías en la Nube

## ⚙️ Soluciones Open Source de Balanceo de Carga

### 🧱 HAProxy

**HAProxy** es un balanceador de carga **TCP/HTTP** gratuito y de código abierto, confiable y de alto rendimiento.  
Está especialmente diseñado para sitios web con **altísimo tráfico**, y alimenta una parte significativa de los sitios más visitados del mundo.  
Es considerado el estándar de facto en balanceadores de carga open-source y está incluido en la mayoría de las distribuciones Linux populares.  

**Características principales:**
* Alto rendimiento
* Gran confiabilidad
* Soporte para la mayoría de sistemas operativos estilo Unix

---

### 🧭 NGINX

**NGINX** es un servidor HTTP de alto rendimiento y un proxy inverso (balanceador de carga), gratuito y de código abierto.  
Es conocido por su rendimiento, estabilidad, conjunto de funcionalidades y configuración sencilla.

**Características principales:**
* Balanceo de carga a nivel HTTP (L7)
* Configuración simple
* Amplio soporte de módulos

---

## ☁️ Soluciones de Balanceo de Carga en la Nube

### 🟨 AWS - Elastic Load Balancing (ELB)

**Amazon ELB** es una solución altamente escalable de balanceo de carga que se integra perfectamente con todos los servicios de AWS.

**Modos de operación disponibles:**

* **Application Load Balancer (L7)** – Ideal para balanceo avanzado de tráfico HTTP y HTTPS.
* **Network Load Balancer (L4)** – Ideal para balancear tráfico TCP y UDP.
* **Gateway Load Balancer** – Ideal para desplegar, escalar y gestionar appliances virtuales de terceros.
* **Classic Load Balancer (L4 y L7)** – Ideal para enrutar tráfico hacia instancias EC2.

---

### 🟥 GCP - Cloud Load Balancing

**Google Cloud Load Balancing** es una solución robusta y altamente escalable que permite poner tus recursos detrás de una única dirección IP (externa o interna dentro de una red VPC).

**Tipos de balanceadores disponibles:**

* **External HTTP(S) Load Balancer (L7)** – Para servicios escalables accesibles desde internet.
* **Internal HTTP(S) Load Balancer (L7)** – Para servicios escalables internos.
* **External TCP/UDP Load Balancer (L4)** – Para tráfico externo basado en TCP/UDP.
* **Internal TCP/UDP Load Balancer (L4)** – Para tráfico interno en TCP/UDP.

---

### 🟦 Microsoft Azure Load Balancer

Azure ofrece tres tipos de soluciones de balanceo:

* **Standard Load Balancer** – Balanceador de capa 4 público e interno.
* **Gateway Load Balancer** – Alto rendimiento y disponibilidad para appliances virtuales de red de terceros.
* **Basic Load Balancer** – Ideal para aplicaciones de pequeña escala.

---

## 🌍 Soluciones GSLB (Global Server Load Balancing)

* **Amazon Route 53** – Servicio DNS altamente disponible y escalable.
* **AWS Global Accelerator** – Mejora la disponibilidad, rendimiento y seguridad de tus aplicaciones públicas.
* **Google Cloud DNS** – DNS de baja latencia, confiable y resiliente con alcance global.
* **Azure Traffic Manager** – Balanceo de carga basado en DNS para distribuir tráfico de forma eficiente.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/01_DNS%2C_Load_Balancing_%26_GSLB.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/03_Message_Brokers.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)