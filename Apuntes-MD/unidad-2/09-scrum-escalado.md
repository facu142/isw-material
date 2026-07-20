# 09 — Scrum Escalado (Nexus y LeSS)

> Págs. 113-123 del apunte. Cubre los frameworks para escalar Scrum a múltiples equipos.

## ¿Cuándo escalar Scrum?

> Cuando tenés **más de un equipo de Scrum** trabajando sobre el **mismo producto**.

![Matriz de Scaled Scrum](imgs/p113_img1.png)

- **1 equipo + 1 producto** → Scrum clásico.
- **Más equipos + más productos** → Portfolio Management.
- **Múltiples equipos + 1 producto** → **Scaled Scrum** (Nexus, LeSS).

> **El dolor** (Painful) es la zona del medio: más de un equipo pero sin coordinación = desastre.

---

## Nexus

> **Nexus** es un grupo de **aproximadamente 3 a 9 Scrum Teams** que trabajan sobre un **único Product Backlog** para construir un **Integrated Increment**.

### Nexus Integration Team (NIT)

> Equipo pequeño de personas (representantes de los Scrum Teams) cuya responsabilidad es **identificar y resolver dependencias**, asegurar la calidad de la integración y mantener la transparencia.

**Ejemplo de intervención del NIT**:
- Equipo X no realiza pruebas de rendimiento en sus entregas.
- Equipo Y no documenta los endpoints del API.
- Equipo Z usa un formato diferente para los logs.
- El NIT **organiza un taller** con representantes de todos los equipos para alinear una **única Definition of Ready**.

### Eventos de Nexus

Nexus **agrega o extiende** los eventos de Scrum:

- **Nexus Sprint**: los Scrum Teams producen un **solo Integrated Increment**.
- **Refinamiento del Product Backlog entre Equipos**: reduce o elimina las **dependencias** entre equipos.
  - *Ejemplo*: en lugar de que un equipo trabaje solo en backend y otro solo en frontend, ambos podrían manejar **funcionalidades completas** (frontend + backend) de una sección específica.
- **Nexus Sprint Planning**: coordinan las actividades de todos los Scrum Teams. Genera:
  - **Objetivo del Nexus Sprint** (común a todos).
  - **Objetivos del Sprint** individuales (cada equipo puede tener el suyo).
  - **Nexus Sprint Backlog** (común).
  - **Sprint Backlog** de cada equipo.
- **Nexus Daily Scrum**: asisten solo representantes de cada Scrum Team. Se discuten problemas de **integración** y se inspecciona el progreso hacia el objetivo del Nexus Sprint.
- **Nexus Sprint Review**: reemplaza a las Sprint Reviews individuales. Brinda feedback al **Integrated Increment**.
- **Nexus Sprint Retrospective**: planifica mejoras en todo el Nexus.

### Artefactos de Nexus

- **Product Backlog**: hay **uno solo** que contiene todo lo que el Nexus necesita.
- **Nexus Sprint Backlog**: compuesto por el Objetivo del Nexus Sprint y los elementos de cada Scrum Team. Resalta las **dependencias**.
- **Integrated Increment**: la suma de todo el trabajo integrado. Su compromiso es la **DoD** común.

---

## LeSS (Large-Scale Scrum)

> **LeSS** es un marco que permite **escalar Scrum** y se aplica a productos de entre **2 a 8 equipos**. Propone:

- Un **solo Product Owner**.
- Un **Scrum Master** que puede servir de **1 a 3 equipos**.
- Un **único Product Backlog**.
- **Sprint común** para todos los equipos.
- **Más de 8 equipos** → usar **LeSS Huge**.

> LeSS trata de **aplicar los conceptos y principios de Scrum a gran escala de la manera más sencilla posible**.

### Principios de LeSS

- **Scrum a gran escala es Scrum**: no es un Scrum nuevo, es aplicar Scrum existente a escala.
- **Transparencia**: basada en tareas "realizadas" tangibles, ciclos cortos, trabajo en equipo, definiciones comunes y eliminación del miedo.
- **Más con menos**:
  - No queremos más roles (más roles = menos responsabilidad).
  - No queremos más artefactos (más distancia entre equipos y clientes).
  - No queremos más procesos (menos aprendizaje).
- **Enfoque en el producto integral**: un Product Backlog, un PO, un producto entregable, un Sprint, **independientemente de si son 3 o 33 equipos**.
- **Centrado en el cliente**.
- **Mejorar hasta lograr la perfección**.
- **Teoría de cola**: cómo se comportan los sistemas con colas, para gestionar tamaños, WIP, multitarea, paquetes de trabajo y variabilidad.

### Roles

- **Un Product Owner**.
- **De 2 a 8 equipos**.
- **Un Scrum Master para 1 a 3 equipos**.
- **Feature teams**: equipos full-stack multifuncionales, inter-componentes, en código compartido.

### Eventos

- **LeSS Sprint**: **un sprint** a nivel producto, no uno por equipo. Todos comienzan y terminan juntos.
- **Sprint Planning One**: atendida por el PO y los equipos. Juntos seleccionan **tentativamente** los ítems que cada equipo trabajará. Identifican oportunidades para trabajar juntos.
- **Sprint Planning Two**: cada equipo trabaja para determinar **cómo** llevará a cabo sus tareas.
- **Daily Scrum**: cada equipo tiene la suya (15 minutos, 3 preguntas).
- **Sprint Review**: presentación de resultados a stakeholders.
- **Sprint Retrospective**: cada equipo individualmente hace la suya.
- **Overall Retrospective**: con todos los equipos, respondiendo:
  - ¿Qué tan bien trabajamos juntos?
  - ¿Estamos aprendiendo juntos?
  - ¿Hay algo que hizo un equipo que debería compartirse?
- **Product Backlog Refinement (PBR)**: evento **formal esperado** (reunión-taller), no una "actividad" no especificada.
  - **PBR multi-equipo**: varios equipos en la misma sala al mismo tiempo. Es el evento **más importante** en LeSS para alinear equipos.

### Artefactos

- **Product Backlog**: un solo PB. Los ítems **no están pre-asignados** a los equipos.
- **Sprint Backlog**: cada equipo tiene el suyo.
- **Incremento del producto potencialmente entregable**: la salida de cada Sprint.

### DoD en LeSS

- **Existe una DoD común a todos los equipos**.
- Cada equipo puede tener su DoD **más detallada**, pero **siempre expandiendo** de la común.
- El objetivo es mejorar la DoD para que resulte en el envío del producto en cada Sprint (o incluso más seguido).

---

## LeSS Huge

> **LeSS Huge** es la versión extendida para **más de 8 equipos** (hasta cientos o miles de personas).

- El **Product Backlog se divide en Áreas de Requisitos** (lo que facilita la gestión).
- Se asigna un **Product Owner de Área** por cada área de requisitos (un solo PO no puede gestionar todo).
- Se descompone en **vistas** según el área. Cada vista es una descomposición más detallada del PB para el área que corresponda.

---

## Comparación Nexus vs. LeSS

| Aspecto | Nexus | LeSS |
|---|---|---|
| **Equipos** | 3-9. | 2-8 (LeSS estándar), más con LeSS Huge. |
| **Product Owner** | 1. | 1 (con áreas si es LeSS Huge). |
| **Scrum Master** | 1 (NIT). | 1 cada 1-3 equipos. |
| **Enfoque** | Mantener Scrum + integración. | Scrum a gran escala "más con menos". |
| **Dependencias** | NIT las gestiona. | PBR multi-equipo las reduce. |

---

## Chivo para el oral

1. **¿Cuándo escalar?** Cuando hay **más de un equipo Scrum** sobre el mismo producto. Con 1 producto + 1 equipo → Scrum clásico.
2. **Nexus**: 3-9 equipos Scrum con un **Nexus Integration Team** (NIT) que gestiona dependencias. Eventos y artefactos similares a Scrum, con un **Integrated Increment**.
3. **LeSS**: 2-8 equipos, **un Sprint común**, un Product Backlog, Scrum Masters cada 1-3 equipos. Principio **"más con menos"**: no agregar roles ni artefactos. **PBR multi-equipo** es el evento clave.
4. **LeSS Huge**: más de 8 equipos, Product Backlog dividido en **Áreas de Requisitos** con un PO por área.
5. **Cerrá con la idea**: escalar Scrum es **agregar equipos, no agregar roles**. Se mantiene la filosofía "más con menos" y se enfatiza la **integración continua** y la **reducción de dependencias**.

> **Si te preguntan "¿qué pasa con más de 8 equipos?"** → **LeSS Huge**, donde el PB se divide por áreas de requisitos y hay un PO por área.
