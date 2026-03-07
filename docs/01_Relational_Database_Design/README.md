# 01 — Relational Database Design: ER/EER → Relacional → Normalización

## Objetivo
`Dominar el **diseño de bases de datos relacionales** de forma profesional, pasando por:`

- **Modelo Conceptual** (ER/EER): representar el problema y reglas del negocio.
- **Modelo Relacional**: traducir ER/EER a tablas con llaves y restricciones.
- **Normalización**: reducir redundancia y anomalías de actualización.
- **Práctica sistemática**: ejercicios por tema para consolidar criterio.

Esta unidad es el núcleo “ingenieril” del curso: aquí se aprende a diseñar bien antes de implementar en SQL.

---

## Contenido de la unidad (carpetas dentro de `docs/02 -  Dideño de Bases De Datos Relacionales/`)

<br>

### Sección 1 — Modelo Conceptual
- `Seccion 1 Modelo Conceptual/`
  - `1 Modelo Entidad-Relacion/`
    - `01 Teoria/`
    - `Exercice/`
  - `2 Modelo Entidad-Relacion Extendido/` *(EER: generalización/especialización, agregación, etc.)*
  - `Seccion 1 Modelo Conceptual/Seccion 1 Modelo Conceptual/` *(si existe en tu árbol, conservar como está y revisar naming después)*

<br>

### Sección 2 — Modelo Relacional
- `Seccion 2 Modelo Relacional/`
  - `01 Teoria/`
  - `02 Exercice/`

<br>

### Sección 3 — Normalización
- `Seccion 3 Normalización/`
  - `01 Teoria/`
  - `02 Exercice/`

*(Los nombres exactos pueden variar según tus carpetas actuales; usa esta guía como mapa conceptual del contenido.)*

---

## Cómo estudiar esta unidad (orden recomendado)

<br>

#### Fase A — ER (fundamentos)
1) Teoría de **Entidades, Atributos, Relaciones y Cardinalidad**  
2) Ejercicios (al menos 3 antes de avanzar)

<br>

#### Fase B — EER (extendido)
3) Generalización/Especialización  
4) Agregación (si aplica en tu material)  
5) Ejercicios

<br>

#### Fase C — Paso a Relacional
6) Reglas de mapeo ER/EER → Tablas  
7) Llaves primarias/foráneas, restricciones  
8) Ejercicios

<br>

#### Fase D — Normalización
9) 1FN → 2FN → 3FN (con ejemplos)  
10) Ejercicios (mínimo 3 completos)

---

## Indicadores de dominio (listo para pasar a SQL)

<br>

**`Puedes avanzar a QL cuando:`**

- Diseñas un ER completo sin inconsistencias (entidades/atributos/relaciones bien definidos).
- Asignas cardinalidades correctamente y justificas tus decisiones.
- Traducir ER/EER a un esquema relacional con PK/FK sin perder reglas.
- Detectas redundancias y aplicas normalización (al menos hasta 3FN) con criterio.
- Puedes explicar qué anomalía evita cada normalización (inserción/actualización/borrado).

---

<br>

## **Entregables de la unidad (pendiente de implementación)**

`Esta unidad tendrá entregables prácticos (ER/EER → Relacional → Normalización), pero quedan como **pendientes** hasta definir:`

- formato de entrega en comunidad (ej. grupo de Facebook)
- checklist de calidad (errores típicos y cómo evaluarlos)
- set de ejercicios “oficial” por nivel

✅ Cuando estén listos, se documentarán aquí con instrucciones claras y ejemplos.

---

<br>

## **Salida de la unidad (qué sigue)**

**`Cuando completes esta unidad, continúa con:`**

✅ `docs/03 -  Curso De Bases De Datos SQL/`  
y comienza la implementación del esquema en **MySQL** (DDL/DML + consultas).