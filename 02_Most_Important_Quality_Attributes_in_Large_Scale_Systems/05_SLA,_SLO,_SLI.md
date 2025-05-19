# 📏 SLA, SLO y SLI

## 🧾 Introducción

Después de explorar los principales **atributos de calidad**, es momento de cerrar esta sección con tres conceptos fundamentales que encapsulan las **promesas que hacemos a nuestros usuarios** en cuanto a la calidad del servicio:

* **SLA**: Service Level Agreement (Acuerdo de Nivel de Servicio)  
* **SLO**: Service Level Objective (Objetivo de Nivel de Servicio)  
* **SLI**: Service Level Indicator (Indicador de Nivel de Servicio)

---

## 🤝 SLA - Service Level Agreement

Un **SLA** es un **acuerdo legal** entre el proveedor del servicio (nosotros) y los clientes o usuarios. Este acuerdo representa las **promesas explícitas** que hacemos en relación con atributos de calidad como:

* Disponibilidad  
* Rendimiento  
* Durabilidad de los datos  
* Tiempo de respuesta ante fallas  

### 📉 Consecuencias de Incumplimiento

El SLA también define las **penalizaciones** si no cumplimos con lo prometido, tales como:

* Reembolsos parciales o totales  
* Extensión de suscripciones o licencias  
* Créditos por servicio  

### 🔄 SLA Internos vs. Externos

* **SLAs externos**: Usuales para usuarios pagos. A veces también se aplican a usuarios gratuitos, como en un periodo de prueba con problemas de disponibilidad.
* **SLAs internos**: Entre equipos dentro de la misma empresa. Aunque no suelen tener penalizaciones, ayudan a coordinar esfuerzos para cumplir con SLAs externos.

---

## 🎯 SLO - Service Level Objective

Un **SLO** es un **objetivo específico** que define un valor o rango que el sistema debe cumplir respecto a una métrica.

### 📌 Ejemplos comunes de SLOs:

* Disponibilidad del 99.9% (three nines)  
* Tiempo de respuesta menor a 100 ms en el percentil 90  
* Resolución de incidentes en menos de 48 horas  

Los SLOs representan los requisitos de calidad recogidos al diseñar el sistema, y cada uno puede formar parte del SLA general si este existe.

> 🔹 Incluso si no tenemos un SLA formal, **los SLOs son esenciales** para establecer expectativas con usuarios internos o externos.

---

## 📊 SLI - Service Level Indicator

Un **SLI** es una **métrica cuantitativa** que refleja nuestro cumplimiento con un SLO.

### 🧮 Ejemplos de SLIs:

* Porcentaje de solicitudes exitosas → usado para medir disponibilidad  
* Tiempo de respuesta por solicitud → usado para medir rendimiento  
* Distribución percentil de latencias → para comparar con el objetivo de SLO

Los SLIs se obtienen de sistemas de monitoreo o análisis de logs, y permiten **validar si los SLOs se están cumpliendo**.

> 📌 Los atributos de calidad deben ser **medibles y verificables**, ya que sin eso no se pueden definir SLIs confiables.

---

## 🧠 Consideraciones Clave al Definir SLOs

### 1. 🎯 Enfocarse en lo que importa
No debemos definir SLOs para cada métrica disponible.  
**Debemos enfocarnos en lo que más valoran los usuarios** y construir nuestros SLOs con base en eso.

### 2. 📉 Menos es más
Cuantos **menos SLOs** tengamos, más fácil será:
* Priorizarlos
* Diseñar la arquitectura en torno a ellos
* Mantener el enfoque

### 3. 🧮 Objetivos realistas y margen de error
No prometas más de lo necesario.  
**Ejemplo**: Si podemos ofrecer 99.99% de disponibilidad, comprometámonos solo con el 99.9% (externamente).  
Esto:
* Reduce costos
* Evita penalizaciones
* Proporciona margen para imprevistos

> 🧩 Empresas suelen usar **SLOs internos más estrictos** que los SLOs definidos en el SLA público.

### 4. 🆘 Tener un plan de recuperación
Cuando no cumplimos con un SLO, debemos tener un plan claro, incluyendo:
* Alertas automáticas
* Escalamiento automático
* Rollbacks y reinicios
* Manuales de emergencia para el equipo on-call

---

## ✅ Conclusión

* **SLA**: Contrato legal entre proveedor y cliente. Contiene los SLOs más importantes.  
* **SLO**: Objetivos específicos de calidad que debemos alcanzar.  
* **SLI**: Métricas para medir si cumplimos con los SLOs.

Definir SLOs sólidos y medibles es responsabilidad de arquitectos y desarrolladores, mientras que los SLAs suelen estar en manos del área legal y de negocio.  
Un buen diseño de sistema **parte de SLOs bien definidos y realistas**.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/02_Most_Important_Quality_Attributes_in_Large_Scale_Systems/04_Fault_Tolerance_%26_High_Availability.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/03_API_Design/01_Introduction_to_API_Design_for_Software_Architects.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
