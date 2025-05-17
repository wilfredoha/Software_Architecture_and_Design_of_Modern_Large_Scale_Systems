# 🧱 System Constraints in Software Architecture

En esta sección exploramos el tercer tipo de **driver arquitectónico** en el diseño de software: los **sistemas de restricciones** o **system constraints**. Estas restricciones limitan nuestras decisiones arquitectónicas y, por lo tanto, tienen un impacto directo en la estructura de nuestras soluciones.

---

## ❓ ¿Qué son las restricciones del sistema?

Una **restricción del sistema** es una decisión que ya ha sido tomada total o parcialmente antes de diseñar el sistema, limitando nuestros grados de libertad. A diferencia de los requerimientos funcionales y atributos de calidad (donde el arquitecto tiene libertad para elegir cómo cumplirlos), las restricciones imponen condiciones que **no se pueden negociar** o **se deben priorizar** desde el inicio.

> ⚠️ Aunque las restricciones limitan las opciones, también pueden verse como **puntos de partida sólidos**, por eso a menudo se las llama **los pilares de la arquitectura de software**.

---

## 🧩 Tipos de restricciones del sistema

Las restricciones generalmente provienen de **tres fuentes principales**:

### ⚙️ 1. Restricciones Técnicas

Son decisiones tecnológicas impuestas por:

- **Infraestructura existente** (por ejemplo, uso obligatorio de data centers on-premise).
- **Lenguajes de programación** ya utilizados o con mayor disponibilidad de talento.
- **Tecnologías heredadas**, frameworks internos, bases de datos específicas, etc.
- **Compatibilidad** con navegadores, sistemas operativos o dispositivos específicos.

> 🛠 Aunque suenan a decisiones de implementación, muchas veces estas restricciones afectan directamente la arquitectura.

📌 **Ejemplo**: Si una organización debe operar en sus propios servidores por razones de seguridad, se descartan arquitecturas basadas en funciones serverless o escalado automático en la nube.

---

### 💼 2. Restricciones del Negocio

Estas restricciones provienen de los objetivos estratégicos de la organización y pueden incluir:

- **Presupuesto limitado**
- **Plazos de entrega estrictos**
- **Integración obligatoria con terceros**
- **Priorización de ciertos dominios del negocio**

📌 **Ejemplo**: Un negocio puede decidir que el sistema de pagos será gestionado por un proveedor externo, lo que implica integrar su API y adaptar nuestra arquitectura a sus paradigmas.

---

### ⚖️ 3. Restricciones Legales y Regulatorias

Impuestas por gobiernos o entidades regulatorias. Algunos ejemplos incluyen:

- **HIPAA** (en EE. UU.) para sistemas con información médica.
- **GDPR** (en la Unión Europea) para servicios en línea que manejan datos personales.
- **Limitaciones de retención, almacenamiento y acceso** a ciertos datos.

📌 Estas regulaciones pueden determinar cómo se diseña el almacenamiento, acceso y cifrado de datos en nuestra arquitectura.

---

## 🧠 Consideraciones importantes

Al tratar con restricciones del sistema, debemos tener en cuenta dos principios clave:

### 🔍 1. No asumir restricciones a la ligera

No todas las restricciones son absolutas. Algunas son **autoimpuestas** y pueden renegociarse.

✅ **Acciones recomendadas**:
- Validar si la restricción es negociable.
- Consultar expertos si hay dudas sobre su vigencia o necesidad.
- Aprovechar proyectos nuevos para replantear tecnologías existentes.

📌 **Ejemplo**: Si estamos obligados a usar una base de datos específica, debemos confirmar si esto sigue siendo necesario o si existen mejores opciones actualmente.

---

### 🧳 2. Evitar el acoplamiento fuerte a las restricciones

Cuando una restricción es inevitable, debemos **diseñar nuestra arquitectura de forma desacoplada**, permitiendo cambiar esa decisión en el futuro.

✅ **Recomendaciones**:
- Usar interfaces abstractas.
- Aplicar principios como la inversión de dependencias.
- Encapsular integraciones con servicios de terceros.

📌 **Ejemplo**: Si usamos un proveedor externo de pagos, encapsulamos su lógica en una capa que podamos sustituir si cambiamos de proveedor más adelante.

---

## 🏁 Conclusión

Las restricciones del sistema son un componente crítico que influye directamente en nuestras decisiones arquitectónicas.

- Son **decisiones preexistentes** que limitan nuestras opciones técnicas.
- Se clasifican en: **técnicas, de negocio y legales**.
- Requieren un análisis cuidadoso para distinguir entre lo **negociable** y lo **no negociable**.
- Una buena arquitectura debe estar preparada para **adaptarse** si esas restricciones cambian en el futuro.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/01_System_Requirements_%26_Architectural_Drivers/03_System_Quality_Attributes_Requirements.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/01_Performance.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
