# data-adicional/ — material de trabajo de la Formulación V2

Borradores derivados del informe, no contenido del PDF. Aquí se prepara y se
anota lo que después se migra a `src/main/sections/*.tex`; `main.tex` no enlaza
nada de esta carpeta.

Estado: borradores revisables. Nada de este material ha sido validado con
terceros; las posturas, umbrales y cotizaciones siguen pendientes y así se
declara en cada archivo.

## Reglas duras

1. **No se enlaza desde `main.tex`.** El informe compila sin esta carpeta.
2. **No se copia literal al informe.** Se parafrasea y se cita por
   `library.bib`; una cifra sin `archivo:línea` de origen no entra.
3. **Se conserva el estado de cada afirmación**: D (declarado), H (hipótesis) o
   S (solución anticipada), igual que en `src/main/sections/2.problema.tex:7`.
4. **Ningún umbral nuevo.** Donde falta medición, el valor queda como `T_…` a
   fijar en la Fase 1, con acción, responsable y plazo.
5. **No se inventan** actas, encuestas, registros ni cotizaciones. Lo pendiente
   se escribe como pendiente con su plan.
6. **No confundir unidades**: esto es gestión de interesados (segunda unidad).
   La matriz de involucrados y beneficiarios del 13 oct es otro capítulo.

## Archivos

| Archivo | Qué contiene | En qué se basa |
| --- | --- | --- |
| `1-requisitos.md` | Cinco requisitos replanteados con la ficha de cinco campos: original y necesidad, evidencia con fuente/fecha/límite, redacción mejorada, prueba de aceptación y costo con fuente y supuesto pendiente. Incluye la tabla de pendientes con responsable y plazo. | V1: `5.alcance.tex:55-89` (RF-01, RF-02, RF-03, RNF-01 a RNF-04), `2.problema.tex:40,71,89,153`, `4.alternativas.tex:7,23`, `7.costos.tex:7,16-29`. Método: deck del 05 nov (ficha de corrección) y del 20 oct (redacción verificable y clasificación funcional / no funcional / operativo / restricción). |
| `2-plan-involucramiento.md` | Tabla A de poder–interés y postura (actual → deseada) y Tabla B de plan: acción concreta, responsable, frecuencia y evidencia. Más la justificación con la evidencia disponible y los vacíos. | Actores dispersos en `1.finalidad.tex:7`, `2.problema.tex:16,52`, `5.alcance.tex:33`, `6.viabilidad.tex:36-40` y `7.costos.tex:51-57`. Método: deck del 12 nov (plantilla `Actor · actual → deseado · acción · responsable · indicador/evidencia`). |
| `3-entrevista.md` | Instrumento de entrevista y validación técnica para el Ing. Ademir Portillo: ocho afirmaciones del informe que él debe confirmar o corregir, más operación de la red, evidencia que puede entregar, ventanas de intervención y firma de conformidad. | `2.problema.tex:16,40` (E3 y la lista de ambientes en `:52`), `2.problema.tex:89` (CI2), `5.alcance.tex:55,73-74`, `7.costos.tex:7`. |
| `4-trazabilidad.md` | Cadena evidencia → necesidad → objetivo → requisito → entregable → prueba → costo; tres afirmaciones críticas acotadas; registro V1 → V2 con impacto; y las inconsistencias de la V1 que deben corregirse. | Todas las secciones del informe. Método: matriz de trazabilidad del 20 oct y cadena de valor del 05 nov. |

## Cómo usar esta información

1. **Para sustentar**: cada respuesta sale de un archivo de aquí y cita su
   `archivo:línea` del informe. Si no hay línea, no hay afirmación: se registra
   como pendiente.
2. **Orden de lectura**: `1-requisitos.md` → `4-trazabilidad.md` (para ver qué
   requisito se queda sin objetivo) → `2-plan-involucramiento.md` (quién valida
   qué) → `3-entrevista.md` (qué se pregunta hoy y qué cambia después).
3. **Después de la entrevista**: la declaración de E3 pasa de «fecha pendiente»
   a fuente fechada. Hay que actualizar `2.problema.tex:40` y la sección 1 y 2 de
   `4-trazabilidad.md`.
4. **Después de la Fase 1**: los `T_…` y las `N` se reemplazan por las mediciones
   y se actualizan las fichas de `1-requisitos.md`.
5. **Si el producto se pide dentro del informe**: el contenido migra a
   `5.alcance.tex` (requisitos) y a una sección nueva de gestión de interesados;
   el borrador no se copia tal cual.

## Vacíos conocidos

- Posturas de la Tabla A son hipótesis: no hay actas ni entrevistas previas.
- Las cinco partidas de costo siguen sin cotización con RUC y fecha.
- Las Figuras 1 y 2 (`8.anexos.tex`) no tienen fecha, hora ni laboratorio.
- RF-03, RNF-01 y RNF-02 no tienen objetivo al que responder (ver
  `4-trazabilidad.md`, sección 1).
