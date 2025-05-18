# 🔄 Disponibilidad - Introducción y Medición

## 📌 Importancia de la Alta Disponibilidad

La **disponibilidad** es uno de los atributos de calidad más importantes al diseñar sistemas a gran escala, ya que tiene un enorme impacto tanto en los usuarios como en el negocio.

- **👥 Usuarios**: 
  - Frustración al intentar acceder a un servicio que no responde.
  - Por ejemplo, cargar una página y que esta no funcione o recibir un error al hacer checkout.

- **🏢 Negocios**: 
  - Pérdida directa de ingresos si el servicio no está disponible.
  - Fuga de clientes hacia la competencia si las caídas son frecuentes o prolongadas.

- **🚨 Sistemas Críticos**:
  - Fallas pueden poner vidas en peligro (por ejemplo, hospitales o control de tráfico aéreo).

**📍Ejemplo Real**: En febrero de 2017, una caída de AWS S3 afectó más de 100,000 sitios web. Fue tan severa que casi colapsa una gran parte de Internet.

---

## 📐 ¿Cómo Definimos la Disponibilidad?

La **disponibilidad** puede definirse como la fracción de tiempo (o la probabilidad) en que un sistema está **funcionalmente operativo y accesible** para el usuario.

- El tiempo en que el sistema está operativo = **uptime**.
- El tiempo en que el sistema está inoperativo = **downtime**.

> **Fórmula Básica**:  
> `Disponibilidad (%) = (Uptime) / (Uptime + Downtime)`

⚠️ A veces los términos *uptime* y *availability* se usan de forma intercambiable en documentos o SLA.

---

## 📊 Medición Alternativa: MTBF y MTTR

Una forma alternativa de estimar la disponibilidad es usar dos métricas estadísticas:

- **🕒 MTBF (Mean Time Between Failures)**: Tiempo promedio entre fallas.
- **🔧 MTTR (Mean Time To Recovery)**: Tiempo promedio para detectar y recuperarse de una falla.

> **Fórmula Alternativa**:  
> `Disponibilidad = MTBF / (MTBF + MTTR)`

💡 Si logramos reducir MTTR teóricamente a cero, alcanzamos una disponibilidad del 100%.  
Aunque en la práctica, esto es imposible, minimizar MTTR mejora significativamente la disponibilidad.

---

## 🎯 ¿Qué Nivel de Disponibilidad Debemos Apuntar?

Aunque el **100%** de disponibilidad es ideal, en la práctica no es alcanzable debido a mantenimientos planificados o emergencias.

### 🧮 Tabla de Disponibilidad

| Disponibilidad | Tiempo de Inactividad Aproximado |
|----------------|-------------------------------|
| 90%            | +2 horas por día / +36 días por año |
| 95%            | 1 hora por día / ~18 días por año |
| 99%            | ~15 min por día / ~3.5 días por año |
| 99.9% (tres nueves) | ~1.5 min por día / ~8 horas por año |
| 99.99% (cuatro nueves) | ~8.6 segundos por día / ~52 minutos por año |

✅ **Alta Disponibilidad** generalmente se define como **99.9% o más**, según estándares de proveedores en la nube.

🔢 En la industria también es común referirse al número de "nueves" en el porcentaje:
- 99.9% = **Tres nueves**
- 99.99% = **Cuatro nueves**
- 99.999% = **Cinco nueves**

---

## 🧠 Resumen de la Lección

- La alta disponibilidad es **crítica** tanto para usuarios como para el negocio.
- Las fallas pueden implicar **pérdida de ingresos** y **fuga de clientes**.
- Se define como el tiempo o probabilidad de estar **operativo y accesible**.
- Se puede medir usando:
  - Fórmula de *uptime/downtime*.
  - Fórmula estadística con **MTBF** y **MTTR**.
- El objetivo práctico es alcanzar **tres nueves (99.9%) o más** de disponibilidad.

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/02_Scalability.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/04_Fault_Tolerance_%26_High_Availability.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)