
# 🧱 Arquitectura de Microservicios

## 📌 Introducción

En esta sección aprenderemos sobre un patrón arquitectónico muy popular y útil llamado **Arquitectura de Microservicios**. Comenzaremos entendiendo su **motivación** al compararlo con la **arquitectura monolítica de tres capas**, y luego revisaremos sus **ventajas**, **mejores prácticas** y **desafíos** asociados.

---

## 🧩 ¿Qué es la Arquitectura de Microservicios?

En contraste con la arquitectura monolítica, donde toda la lógica de negocio está centralizada en un único servicio, la arquitectura de microservicios organiza esta lógica como una **colección de servicios pequeños, independientes y desplegables por separado**.

Cada microservicio:

* Tiene un **alcance funcional reducido**
* Es **desarrollado y mantenido por un equipo pequeño**
* Se despliega de forma independiente

---

## 🆚 Comparación con la Arquitectura Monolítica

### Arquitectura Monolítica (Tres Capas)

* Adecuada para equipos pequeños y bases de código simples
* A medida que crece, se vuelve difícil de:
  * Depurar
  * Escalar
  * Probar y mantener
  * Cargar completamente en el IDE

### Problemas comunes:

* Conflictos frecuentes entre ramas de código
* Reuniones más largas y menos productivas
* Escasa escalabilidad organizacional

---

## ✅ Ventajas de los Microservicios

* **Código más pequeño y manejable** por servicio
* **Carga rápida** en el IDE
* **Compilación y pruebas más rápidas**
* **Mayor facilidad para añadir nuevas funcionalidades**
* **Menor uso de CPU y memoria**
* **Escalabilidad horizontal** eficiente
* **Autonomía tecnológica** por equipo
* **Mejor seguridad** mediante **aislamiento de fallas (Fault Isolation)**

---

## ⚠️ Consideraciones antes de migrar

Aunque las ventajas son numerosas, **no se obtienen automáticamente** solo por dividir el monolito. Es necesario:

1. Seguir buenas prácticas
2. Aceptar cierta **complejidad y sobrecarga operacional**

---

## 🧠 Buenas Prácticas

### 1. Principio de Responsabilidad Única

Cada microservicio debe encargarse de **una única capacidad del negocio**, dominio, recurso o acción.

#### Ejemplo: App de citas

* **User Profile Service**: gestiona perfiles de usuario
* **Image Service**: gestiona imágenes de perfil
* **Matching Service**: empareja usuarios
* **Billing Service**: gestiona pagos

#### Ejemplo: E-commerce

* **Product Search Service**: búsqueda personalizada
* **Product Inventory Service**: datos de productos
* **Checkout Service**: proceso de compra
* **Tax Calculator**: cálculo de impuestos
* **Shipping & Billing Services**: envío y facturación

---

### 2. Base de Datos Independiente por Servicio

* Cada servicio debe tener su **propia base de datos**
* **Evitar bases de datos compartidas** que generen acoplamientos
* Aceptar cierta **duplicación de datos**
* Permitir que cada base de datos sea un **detalle de implementación encapsulado**

---

## 🔚 Conclusión

La **arquitectura de microservicios** es una excelente opción cuando:

* La complejidad del sistema ha superado la capacidad del monolito
* Se requiere escalar de forma organizacional y técnica

**Pero**:

* Es mejor comenzar con un monolito simple
* Migrar solo cuando el monolito deje de ser efectivo
* Seguir las buenas prácticas para evitar una "bola de lodo" (Big Ball of Mud)

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/06_Software_Architecture_Patterns_and_Styles/02_Multi-Tier_Architecture.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/06_Software_Architecture_Patterns_and_Styles/04_Event_Driven_Architecture.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
