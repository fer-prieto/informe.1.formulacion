# data/ — corpus documental del curso

Materiales del curso **IF483BIN Formulación y Proyectos de TI (EPIIS–UNSAAC)**
convertidos a Markdown: diapositivas de sesión, fichas de taller, consignas de
evaluación y el caso documental del TDR de videoconferencia de 2021.

Esta carpeta **no es contenido del informe**. Es la fuente de consulta desde la
que se redacta `src/main/sections/*.tex`.

## Reglas duras

1. **No se edita.** Cada archivo es una captura de un documento de un tercero
   (docente, equipo de 2021, documento curricular). Corregir una extracción
   significa una **captura nueva** con fecha nueva, no reescribir la existente.
2. **No se copia literal al informe.** Se parafrasea; si hace falta, se cita por
   `library.bib` (la referencia va a `library.bib`, no al `.md`).
3. **`main.tex` no enlaza nada de `data/`.** El PDF no depende de esta carpeta.
4. **Lo que dice una diapositiva no es norma.** `data/` registra lo dictado en
   clase; para marco legal/normativo (Invierte.pe, D. Leg. 1252, PMBOK) se cita la
   fuente oficial, no el deck.
5. **`[H]` en las diapositivas = hipótesis didáctica**, no hecho del caso. Nunca
   presentar como diagnóstico verificado.

## La fecha del nombre es de captura, no de sesión

Convención: `AAAA-MM-DD_slug.md`. El prefijo es la fecha en que el material se
registró, que **casi siempre coincide** con la sesión pero **no siempre**:

| Archivo | Fecha del nombre | Sesión real | Por qué difiere |
| --- | --- | --- | --- |
| `2026-10-01_sesion_29_set_validacion_diagnostico_proyectos_ti_unsaac.md` | 01 oct (jue) | 29 set (mar) | Capturado después |
| `2026-10-13_sesion_06_oct_objetivos_alternativas_ti_unsaac.md` | 13 oct (mar) | 06 oct (mar) | Capturado después |
| `2026-11-02_clase_22oct2026_costos_riesgos_caso_tdr_final_unsaac.md` | 02 nov (lun) | 22 oct (jue) | Re-extracción paginada |
| `2026-10-23_indicaciones_primera_sustentacion_formulacion_v1.md` | 23 oct (vie) | — (consigna) | Encabezado interno dice 22 oct |

Al buscar material por semana, **ordenar por la sesión real**, no por el nombre.

## Cuatro familias (no mezclar)

| Etiqueta | Qué es | Se usa para | No se usa para |
| --- | --- | --- | --- |
| **SESIÓN** | Deck dictado en clase (`.pptx` convertido). Lleva "Objetivo de la sesión", ruta de trabajo, taller | Reconstruir qué se enseñó, criterios del docente, métodos y vocabulario del curso | Sustentar datos del proyecto ni normas |
| **FICHA/GUÍA** | Material de trabajo para el estudiante, del mismo día que una sesión | Saber qué producto se esperaba y con qué formato | Explicar teoría completa |
| **CASO** | Fuente primaria externa analizada en clase (TDR 2021) | Ejemplo documental, lectura crítica | Datos vigentes, precios, diagnóstico propio |
| **EVALUACIÓN/PROGRAMA** | Rúbricas, atributos del graduado, sílabo, consignas de entrega | Alinear el informe con lo que se califica | Guiar el contenido técnico |

## Inventario

| Archivo | Familia | Sesión / tema real | Estado |
| --- | --- | --- | --- |
| `2026-09-17_t1_fpti.md` | PROGRAMA + SESIÓN | 17 sep. Sílabo (pp. 1–3) + deck «Formulación y evaluación de proyectos en TI» | Completo, 33 pp. Mezcla dos cosas |
| `2026-09-22_evaluacion_de_atributos_del_graduado.md` | EVALUACIÓN | — Rúbrica AG_C05 (niveles 4–1, indicadores AG-C05.01/02 al 50 %) | Tablas aplanadas: no citar literal |
| `2026-09-24_sesion_24_set_formulacion_proyectos_ti_unsaac.md` | SESIÓN | 24 set (jue). «De la idea a una necesidad sustentada» | Completo, 11 pp. |
| `2026-10-01_sesion_29_set_validacion_diagnostico_proyectos_ti_unsaac.md` | SESIÓN | 29 set (mar). «De la propuesta preliminar a un problema sustentado» | Completo, 13 pp. |
| `2026-10-01_sesion_01_oct_analisis_causal_problema_proyectos_ti_unsaac.md` | SESIÓN | 01 oct (jue). «Del problema sustentado al análisis causal» | Completo, 17 pp. |
| `2026-10-01_ficha_aplicacion_analisis_causal_proyecto_ti_unsaac.md` | FICHA | 01 oct. Árbol del problema: ejemplo resuelto (pp. 1–4) + ficha en blanco (pp. 5–9) | Completo |
| `2026-10-13_sesion_06_oct_objetivos_alternativas_ti_unsaac.md` | SESIÓN | 06 oct (mar). «Del problema a los objetivos y alternativas» | Completo, 32 pp. |
| `2026-10-13_presentacion_clase_13oct2026.md` | SESIÓN | 13 oct (mar). «Análisis de involucrados y beneficiarios» — **unidad 1** | Extracción irregular: paginado perdido, tablas aplanadas |
| `2026-10-15_presentacion_viabilidad_ti_15oct2026.md` | SESIÓN | 15 oct (jue). «Viabilidad de proyectos de TI» (7 dimensiones, Invierte.pe) | Completo, 40 pp. |
| `2026-10-20_presentacion_20oct_alcance_requerimientos_ti_unsaac.md` | SESIÓN | 20 oct (mar). «Alcance y requerimientos» | Completo, 22 pp. |
| `2026-11-02_clase_22oct2026_costos_riesgos_caso_tdr_final_unsaac.md` | SESIÓN | 22 oct (jue). «Costos, riesgos y consolidación V1» | **Canónico**, 35 pp. paginadas |
| `2026-10-22_guia_estudiantes_caso_tdr_videoconferencia_22oct2026.md` | GUÍA | 22 oct. Lectura crítica del TDR + actividad de taller | Completo |
| `2026-10-22_tdr_sistema_de_videoconferencia.md` | CASO | TDR académico 2021 (17 pp., 13 cláusulas, S/ 45 281,56) | Fuente primaria; histórico |
| `2026-10-23_indicaciones_primera_sustentacion_formulacion_v1.md` | EVALUACIÓN | Sustentación V1: informe 27 oct, exposición 29 oct | Completo: 7 apartados + rúbrica 20 pts |
| `2026-11-05_presentacion_05nov2026_unsaac.md` | SESIÓN | 05 nov (jue). «Validación y fortalecimiento de la Formulación V1» | Completo |
| `2026-11-12_formulacion_ti_gestion_interesados_12_noviembre_2026_ajustada.md` | SESIÓN | 12 nov (jue). «Gestión de interesados» — **unidad 2** | Versión «ajustada» (revisada) |

## Familias en detalle

### SESIÓN (lo más importante)

Los decks forman una secuencia continua; cada uno asume el anterior:

```text
17 sep  deck teórico (qué es formular un proyecto TI)   [dentro de 09-17]
22 sep  continúa el mismo deck hasta la diapositiva 15  (no hay archivo propio)
24 set  necesidad, problema, finalidad, objetivo        [09-24]
29 set  validar diagnóstico: hecho / hipótesis / solución anticipada
01 oct  análisis causal: árbol problema, causas, efectos
06 oct  objetivo central, medios-fines, alternativas
13 oct  involucrados, usuarios, beneficiarios, matriz
15 oct  viabilidad: 7 dimensiones + Invierte.pe
20 oct  alcance, requisitos funcionales y no funcionales
22 oct  costos (TCO), riesgos (P×I, EMV), cadena V1
05 nov  auditoría de la V1: evidencia, requisitos, costos
12 nov  gestión de interesados → abre la SEGUNDA UNIDAD
```

Notas de secuencia:

- El deck del 17 sep se siguió usando el 22 sep; el deck del 24 set lo dice
  explícitamente («se avanzó hasta la diapositiva 15»). No existe un archivo
  aparte para el 22 sep.
- **13 oct y 12 nov no son lo mismo.** 13 oct (unidad 1) es *análisis de
  involucrados*: quién tiene el problema y quién recibe la mejora. 12 nov
  (unidad 2) es *gestión de interesados*: cómo se dirige su participación durante
  la ejecución. Usar el deck equivocado cambia el capítulo del informe.
- El corte de unidad es explícito en el deck del 12 nov («PRIMERA UNIDAD ·
  FORMULACIÓN» vs «SEGUNDA UNIDAD · GESTIÓN»).

### FICHA / GUÍA

- `2026-10-01_ficha_aplicacion_analisis_causal_proyecto_ti_unsaac.md`: ejemplo resuelto del caso videoconferencia
  (pasos 1–6, CD/CI/ED/EI) + ficha en blanco para el equipo. Es el mejor modelo
  de *forma* de un árbol del problema con registro de evidencia.
- `2026-10-22_guia_estudiantes_caso_tdr_videoconferencia_22oct2026.md`: rejilla de lectura crítica del TDR
  (hecho / vacío / inconsistencia / mejora). Repetible para el proyecto propio.

### CASO

`2026-10-22_tdr_sistema_de_videoconferencia.md` es el trabajo académico de 2021
que el curso usa como caso conductor: finalidad, antecedentes, objetivos, marco
normativo COVID, marco teórico de videoconferencia, requerimientos, alcance y
13 cláusulas. **Todo lo cuantitativo es histórico:** S/ 45 281,56 no es un precio
de hoy, y la ausencia de una partida no prueba que no se ejecutó.

### EVALUACIÓN / PROGRAMA

- `2026-09-17_t1_fpti.md` pp. 1–3: información general de la asignatura (IF483BIN,
  3 créditos, mar–jue 2:00 p.m., IN201/IN207) y los temas de las dos unidades.
  Es el sílabo: sirve para nombrar temas como los nombra el curso, nada más.
- `2026-09-22_evaluacion_de_atributos_del_graduado.md`: rúbrica de acreditación
  AG_C05 «Gestión de proyectos». Sirve para justificar el enfoque por
  competencias; sus tablas están rotas, así que se resume, no se transcribe.
- `2026-10-23_indicaciones_primera_sustentacion_formulacion_v1.md`: la consigna operativa.
  **Manda sobre las diapositivas** cuando hay conflicto de formato: exige 7
  apartados (finalidad; problema; objetivos; alternativas; alcance y requisitos;
  viabilidad y cronograma; costos y riesgos), rúbrica de 20 puntos y una lista
  explícita de lo que *no* se exige todavía. Declara ser una adaptación
  pedagógica: si aparece otra indicación oficial posterior, se valida con el
  docente.

## Rarezas conocidas

1. **El deck del 22 oct se capturó dos veces.** Se conserva solo
   `2026-11-02_clase_22oct2026_costos_riesgos_caso_tdr_final_unsaac.md` (1/35–35/35,
   con las notas «Complemento didáctico · ejemplos simulados; validar con fuentes
   reales»). La otra captura, sin paginar, era idéntica palabra por palabra y se
   eliminó; si se necesita, está en el historial de git.
2. **`2026-10-13_presentacion_clase_13oct2026.md`** conserva solo 5 marcas de
   página (`Page 1, 3, 4, 24, 28`) para un deck de 28 diapositivas: el contenido
   está, pero los pies («Bloque IV · 12 min 23») quedaron incrustados en el texto
   y el paginado no sirve para referenciar.
3. **`2026-09-22_evaluacion_de_atributos_del_graduado.md`** es la extracción más degradada de la carpeta:
   encabezados de columna partidos en sílabas. Cualquier cifra citada de ahí hay
   que verificarla con el PDF original.
4. **`2026-09-17_t1_fpti.md`** sirve para dos cosas distintas (sílabo y primera
   sesión). Si se cita, precisar páginas: 1–3 sílabo, 4 en adelante clase.

## Cómo trabajar con esta carpeta

```bash
rg -n 'tema' data/          # buscar por contenido, no por nombre
rg -l '22 de octubre' data/ # localizar por la sesión (fecha dentro del archivo)
```

Antes de afirmar algo en el informe:

1. ¿La afirmación sale de un deck (dictado) o del TDR (fuente primaria)? Si sale
   de un deck, es criterio de clase: redactar como criterio, no como dato.
2. ¿Es un número del TDR 2021? Marcarlo como histórico.
3. ¿Está marcado `[H]` o «por validar»? Entonces va como hipótesis con su
   pregunta de validación, nunca como hallazgo.
4. ¿Es formato de entrega? La consigna del `2026-10-23` tiene prioridad.
