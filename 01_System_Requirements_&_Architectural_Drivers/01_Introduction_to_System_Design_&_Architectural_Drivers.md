# 🎯 Introduction to System Design & Architectural Drivers

En esta sección abordamos la importancia de **recolectar, clasificar y analizar requisitos** como primer paso en el diseño de sistemas a gran escala. Este proceso es fundamental para acotar lo que se necesita construir y trazar el camino hacia una arquitectura adecuada.

## 🧠 Motivación

Los **requisitos del sistema** son simplemente una forma formal de determinar qué se necesita construir para el cliente. Aunque como ingenieros de software estamos acostumbrados a recibir requisitos informales, el diseño de sistemas a gran escala implica:

- Un mayor **alcance y nivel de abstracción**.
- Una mayor **ambigüedad** en los requisitos.

### Diferencias frente a proyectos pequeños

| Característica | Proyectos pequeños | Sistemas a gran escala |
|----------------|--------------------|-------------------------|
| Alcance        | Método o clase     | Sistema completo        |
| Entrada/Salida | Claras             | Difusas                 |
| Ambigüedad     | Baja               | Alta                    |
| Flexibilidad   | Alta               | Limitada por contexto   |

Ejemplo: Diseñar un sistema de almacenamiento de archivos o una plataforma de transporte puede abrumar si no se tienen requisitos claros desde el inicio.

## 🤔 Ambigüedad y su impacto

Los requisitos muchas veces provienen de personas no técnicas y son imprecisos. Es nuestro trabajo **traducir esas necesidades en requisitos técnicos claros**.

Además, el cliente rara vez sabe exactamente lo que necesita. Solo conoce el problema, por lo tanto, **plantear las preguntas correctas ya forma parte de la solución**.

📌 Ejemplo: Un cliente solicita una app para hacer ride-sharing tipo “hitchhiking”. Las preguntas clave incluyen:

- ¿Es en tiempo real o planificada?
- ¿Móvil, escritorio o ambos?
- ¿Pagos integrados o entre usuario y conductor?

## 🚧 Riesgos de no tener requisitos claros

Aunque parezca que en software todo se puede corregir rápidamente, **los sistemas a gran escala no son fáciles de cambiar**:

- Requieren meses y múltiples equipos.
- Se invierte en hardware y licencias.
- Existen contratos, plazos y compromisos.
- No cumplir puede afectar seriamente la reputación.

Por tanto, **definir correctamente los requisitos es crítico**.

## 🗂️ Clasificación de requisitos

Los requisitos se dividen en tres categorías principales, conocidas como **impulsores arquitectónicos (architectural drivers)**:

### 1. ✅ Requisitos funcionales (Features)

Describen **qué hace el sistema**, o su comportamiento. Se representan como funciones de caja negra: entradas → sistema → salidas.

**Ejemplo 1:**
- Entrada: Login del usuario.
- Salida: Mapa con conductores cercanos.

**Ejemplo 2:**
- Entrada: Finalización del viaje.
- Salida: Cargo a tarjeta y transferencia al conductor.

> ⚠️ Importante: **No determinan la arquitectura**, ya que diferentes arquitecturas pueden cumplir las mismas funciones.

### 2. 🏗️ Atributos de calidad (Non-Functional Requirements)

Describen **cómo debe comportarse el sistema** en cuanto a rendimiento, escalabilidad, seguridad, etc.

- Ejemplos: disponibilidad, rendimiento, tolerancia a fallos, etc.
- Estos **sí afectan directamente la arquitectura**.
  
> La **arquitectura de software define los atributos de calidad** del sistema.

### 3. 🚫 Restricciones del sistema

Son limitaciones impuestas, como:

- Plazos estrictos.
- Presupuesto limitado.
- Pocos ingenieros disponibles.

Estas restricciones nos fuerzan a hacer **trade-offs** que afectan las decisiones arquitectónicas.

## 🧭 Conclusión

Los tres tipos de requisitos que influyen directamente en el diseño del sistema son:

1. **Funcionales (Features)**  
2. **No funcionales (Quality Attributes)**  
3. **Restricciones (Constraints)**

Estos se conocen como **impulsores arquitectónicos**, ya que guían nuestras decisiones desde un universo infinito de posibilidades hacia una solución concreta que cumpla con las necesidades del cliente.

---

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/01_System_Requirements_%26_Architectural_Drivers/02_Feature_Requirements_-_Step_by_Step_Process.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
