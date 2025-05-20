# 🌐 DNS, Balanceo de Carga y GSLB

## 🧱 Introducción

En esta sección exploraremos uno de los bloques de construcción más fundamentales y omnipresentes en la arquitectura de software para sistemas a gran escala: **el balanceador de carga**.

Este componente es indispensable en casi el 100% de los sistemas reales a gran escala. A lo largo de esta sección, aprenderás:

* Qué es un balanceador de carga y cuál es su propósito principal.
* Qué atributos de calidad aporta al sistema.
* Cuáles son los tipos principales de soluciones de balanceo de carga.
* Cómo utilizar estas soluciones para diseñar sistemas reales a gran escala.

---

## ⚖️ ¿Qué es un Balanceador de Carga?

Como su nombre indica, **un balanceador de carga distribuye el tráfico entre un conjunto de servidores**, garantizando que ninguno de ellos se sobrecargue.

### 🚫 Sin balanceador

* El cliente necesita conocer las direcciones IP de todos los servidores.
* Hay un fuerte acoplamiento entre el cliente y la implementación interna del sistema.

### ✅ Con balanceador

* El sistema parece ser un único servidor potente.
* Permite escalar horizontalmente y abstrae la complejidad del backend.
* Facilita la gestión y mejora la mantenibilidad.

---

## ⭐ Atributos de Calidad que Aporta un Balanceador

### 📈 Escalabilidad

* Escala horizontal dinámica: añadir o quitar servidores según la demanda.
* Posibilidad de aplicar **autoescalado** en la nube.

### 🔁 Alta disponibilidad

* Monitorea la salud de los servidores.
* Redirige el tráfico únicamente a servidores saludables.

### 🚀 Rendimiento

* Puede introducir una pequeña latencia adicional.
* Aumenta el **throughput** general al permitir múltiples instancias de backend.

### 🔧 Mantenibilidad

* Permite mantenimiento con cero downtime mediante **releases escalonadas** (rolling updates).

---

## 🧰 Tipos de Soluciones de Balanceo

### 📛 Balanceo de Carga vía DNS

* DNS traduce dominios como `midominio.com` a direcciones IP.
* Es posible registrar múltiples IP para un mismo dominio.
* El balanceo se realiza con **round-robin**.

#### ⚠️ Limitaciones del balanceo DNS

* No detecta fallos en servidores.
* Tiene efectos negativos por el **caché DNS**.
* No considera la capacidad ni carga actual de los servidores.
* Exposición directa de IPs de backend (menor seguridad).
* El cliente puede sobrecargar un solo servidor.

---

### 🖥️ Balanceadores de Carga Hardware y Software

* **Hardware**: dispositivos dedicados optimizados.
* **Software**: programas que corren en servidores genéricos.

#### ✅ Ventajas

* No exponen la infraestructura interna.
* Permiten monitoreo activo (health checks).
* Soportan algoritmos de balanceo más inteligentes:
  * Según uso de CPU, conexiones abiertas, carga actual, etc.
* Mejoran la seguridad y control.

#### 🧱 Casos de uso interno

* Separación de servicios (frontend, facturación, cumplimiento).
* Cada servicio puede escalar independientemente.

---

### 🌍 GSLB – Global Server Load Balancing

* Combina funciones de DNS con capacidades avanzadas de balanceo.
* Se usa en sistemas distribuidos globalmente (multidatacenter).

#### 🎯 Características

* Determina la ubicación del cliente (GeoDNS).
* Redirige al **datacenter más cercano** o más óptimo.
* Tiene capacidades de monitoreo como un balanceador tradicional.

#### 🛡️ Beneficios

* Mejora de rendimiento para cada usuario.
* Soporte para **recuperación ante desastres**.
* Alta disponibilidad global.

#### ➕ Redundancia

* Varios balanceadores por región registrados en DNS o GSLB.
* El cliente puede elegir entre múltiples opciones disponibles.

---

## 🧾 Resumen

En esta sección aprendimos sobre:

* El balanceador de carga como bloque esencial de arquitectura.
* Cuatro tipos de soluciones:
  * Balanceo vía DNS
  * Balanceadores de hardware
  * Balanceadores de software
  * GSLB (Global Server Load Balancing)
* Cómo estas soluciones aportan:
  * Escalabilidad
  * Alta disponibilidad
  * Rendimiento
  * Mantenibilidad
  * Seguridad

Estas herramientas nos permiten construir **sistemas distribuidos, resilientes y escalables** para millones de usuarios en distintas ubicaciones geográficas.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/03_API_Design/03_REST_API.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/02_Load_Balancing_Solutions_%26_Cloud_Technologies.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
