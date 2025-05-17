# System Quality Attributes Requirements

En esta sección, exploramos en profundidad los **atributos de calidad del sistema**, también conocidos como **requisitos no funcionales**, fundamentales para una arquitectura de software sólida y sostenible.

## 📌 ¿Por qué son importantes los atributos de calidad?

Numerosos estudios demuestran que los sistemas suelen ser rediseñados, no por deficiencias funcionales, sino porque:

- No son lo suficientemente rápidos.
- No escalan bien ante el aumento de usuarios o volumen de datos.
- Son difíciles de mantener, extender o asegurar.

En muchos casos, el rediseño no implica nueva funcionalidad, sino una mejor estructura para cumplir con requisitos de calidad previamente ignorados.

## 🧾 Definición de Atributo de Calidad

> Los **atributos de calidad** son requisitos no funcionales que describen cómo de bien el sistema realiza sus funciones, midiendo propiedades globales como rendimiento, disponibilidad, escalabilidad, seguridad, etc.

- **No dicen qué hace el sistema**, sino **cómo lo hace**.
- Están directamente relacionados con las decisiones arquitectónicas.

### Ejemplo 1: Atributo de Rendimiento

**Funcionalidad:** Buscar productos en una tienda en línea.

**Atributo de calidad:** El sistema debe mostrar los resultados de búsqueda en menos de 100 ms.

### Ejemplo 2: Atributo de Disponibilidad

> El sistema debe estar disponible el 99.9% del tiempo.

### Ejemplo 3: Atributo de Desplegabilidad (Deployability)

> El equipo de desarrollo puede desplegar nuevas versiones al menos dos veces por semana.

## 🎯 Consideraciones clave sobre atributos de calidad

### 1. Medibles y testeables

> Si no podemos medir un atributo, no podemos garantizar su cumplimiento.

❌ Ejemplo ambiguo: "La confirmación de compra debe mostrarse rápidamente."

✅ Mejor: "La confirmación debe mostrarse en menos de 200 ms."

### 2. No existe una arquitectura única que lo logre todo

Algunos atributos **entran en conflicto entre sí**, por lo que debemos **priorizar**:

- ⏱ Rendimiento vs. 🔒 Seguridad (ej. login rápido vs. autenticación segura)
- 💾 Escalabilidad vs. 💰 Costos

El trabajo del arquitecto es **hacer trade-offs informados** según los objetivos del negocio.

### 3. Factibilidad

Es nuestro trabajo asegurar que los atributos de calidad sean realistas y alcanzables.

🔍 Algunos ejemplos de requisitos inviables:

- Latencia de < 100 ms entre Sudamérica y US-East (por limitaciones físicas).
- 100% de disponibilidad (requiere tolerancia a fallos imposibles de garantizar).
- Protección completa contra ciberataques.
- Transmisión de videos en alta resolución en áreas con bajo ancho de banda.
- Crecimiento de almacenamiento desproporcionado.

> ✔️ Si hay dudas, debemos consultar con expertos en el dominio antes de comprometerse con el requisito.

## 🧠 Conclusiones

- Los rediseños suelen originarse por deficiencias en atributos de calidad, no funcionales.
- Los atributos de calidad **describen cómo se comporta el sistema**, no qué hace.
- Debemos asegurar que sean:
  - 📏 Medibles
  - ⚖️ Priorizables (mediante trade-offs)
  - ✅ Factibles

Diseñar con estos requisitos desde el inicio mejora la sostenibilidad, escalabilidad y mantenibilidad del sistema, reduciendo la necesidad de rediseños costosos en el futuro.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/01_System_Requirements_%26_Architectural_Drivers/02_Feature_Requirements_-_Step_by_Step_Process.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/01_System_Requirements_%26_Architectural_Drivers/04_System_Constraints_in_Software_Architecture.md)  
[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
