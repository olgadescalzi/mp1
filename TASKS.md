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

- [ ] 1. Crear la salida base del pipeline en Parquet con las columnas mínimas del contrato del profesorado.
- [ ] 2. Limpiar el catálogo de estaciones: corregir coordenadas y altitudes, asignar distrito desde el barrio y marcar estaciones fuera de servicio (Datos R4–R7, CA4–CA7).
- [ ] 3. Limpiar viajes: conservar una fila por viaje, excluir los inválidos y normalizar `tipo_bici` y fechas para cumplir el contrato (Datos R1–R2, CA1–CA2, CD1–CD4).
- [ ] 4. Corregir los viajes afectados por los dos cambios de hora y verificar su duración y conservación (Datos R3, CA3, CD3).
- [ ] 5. Limpiar las lecturas de estado: excluir estaciones cerradas, lecturas que excedan la capacidad y sensores bloqueados (Datos R8–R10, CA8–CA9, CD5).
- [ ] 6. Limpiar los datos de abonados: convertir el año 1900 en nulo y normalizar el género vacío (Datos R11, CA10).

## Iteración 2 · Métricas

- [ ] 7. Calcular el total de bicicletas a partir de las lecturas de estado (Métricas §5).
- [ ] 8. Calcular el total de viajes válidos con la definición de Datos R1 y el factor de expansión de la muestra del 5 %.
- [ ] 9. Calcular la distribución porcentual de viajes por tipo de bicicleta (Métricas §5).
- [ ] 10. Calcular el número de viajes corregidos por cambios de hora (Métricas §5, Datos R3).
- [ ] 11. Calcular los viajes estimados por día laborable, dividiendo el total estimado entre los días laborables del periodo (Métricas §5, R7).

## Iteración 3 · Cuadro de mando

- [ ] 12. Crear la aplicación Streamlit que lea las tablas procesadas y arranque con el comando establecido en el contrato del profesorado.
- [ ] 13. Mostrar el total de bicicletas, los viajes válidos, el porcentaje por tipo de bicicleta y los viajes corregidos por cambios de hora (Cuadro de mando §5).

> **Pendiente de concreción del equipo, no incluido como tarea implementable:** definir cómo se elige la lectura que representa las 08:00 y cómo se resuelven empates o días sin datos para responder qué estación tiene más bicicletas cada día laborable. También faltan los esquemas y reglas para las tablas procesadas adicionales y las decisiones de diseño de pantallas, filtros y casos límite.
