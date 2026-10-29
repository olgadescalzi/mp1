# TASKS · Cuadro de mando BiciBCN

> **La lista de tareas, en pasos pequeños.** El agente propone el desglose a partir de SPECS.md; el equipo lo aprueba.
> El agente marca `[x]` y añade la línea `Agente:` cuando los tests pasan. Una persona del equipo completa `Verificado por:`.

<!--
Formato de cada tarea (una tarea = algo que se implementa y verifica en una sola conversación):

- [ ] 1. Qué se hace, en una línea (R…, CA…)

Cuando el agente la termina:

- [x] 1. Qué se hace, en una línea (R…, CA…)
  - Agente: qué hizo y cómo lo comprobó (tests, cifras).
  - Verificado por: nombre · cómo lo comprobó (diff leído, cifra recalculada a mano, pantalla revisada).

Agrupad las tareas por iteración. Pista para empezar: la primera tarea suele ser un pipeline
que copia los CSV a Parquet sin limpiar, para tener el contrato de AGENTS.md funcionando cuanto antes.
-->

## Iteración 1 · Datos limpios

- [ ] 1. Completar y aprobar las especificaciones del análisis de las 8:00, las métricas, las salidas y los criterios verificables; completar diseño y arquitectura.
- [ ] 2. Crear la carga de CSV y el pipeline inicial que genere las tablas Parquet acordadas y cumpla los esquemas mínimos (CD1–CD5).
- [ ] 3. Limpiar el catálogo de estaciones: coordenadas, altitud, distrito y servicio según los requisitos (R4–R7; CA4–CA7).
- [ ] 4. Limpiar los viajes: deduplicación, validez, tipos de bici y corrección de cambios de hora (R1–R3; CA1–CA3; CD1–CD4).
- [ ] 5. Limpiar las lecturas de estado: excluir estaciones cerradas, ocupaciones imposibles y sensores bloqueados (R8–R10; CA8–CA9; CD5).
- [ ] 6. Limpiar abonados y generar las tablas auxiliares que se acuerden en las especificaciones (R11; CA10).

## Iteración 2 · Métricas

- [ ] 7. Calcular las bicis disponibles a las 8:00 y la estación con más bicis por día laborable, conforme a las decisiones aprobadas en la tarea 1.
- [ ] 8. Calcular las métricas de viajes acordadas: viajes válidos y estimados, promedio por día laborable, proporción por tipo de bici y viajes corregidos por cambio de hora.

## Iteración 3 · Cuadro de mando

- [ ] 9. Implementar el cuadro de mando en Streamlit con el análisis de las 8:00 y las métricas, siguiendo el diseño aprobado.
- [ ] 10. Ejecutar la validación final de pipeline, tests aplicables y trazabilidad de criterios.
