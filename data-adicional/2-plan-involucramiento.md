# Plan de involucramiento — Formulación V2

Curso IF483BIN · EPIIS–UNSAAC · Equipo: Auccacusi, León, Prieto

Plantilla del 12 nov: `Actor | Actual → deseado | Acción concreta | Responsable |
Indicador / evidencia`, con frecuencia añadida. Es gestión de interesados
(segunda unidad): cómo se dirige la participación durante la ejecución. **No** es
la matriz de involucrados y beneficiarios del 13 oct, que corresponde a la
primera unidad y a otro capítulo.

Punto de partida: el informe V1 no tiene sección de interesados; los actores se
recuperan dispersos de `1.finalidad.tex:7`, `2.problema.tex:16,40,52`,
`5.alcance.tex:33`, `6.viabilidad.tex:36-40` y `7.costos.tex:51-57`. Las posturas
de la tabla A son **H**: no hay acta, entrevista ni registro que las respalde
todavía.

## Tabla A · Diagnóstico poder–interés y postura

| Actor | Rol frente al proyecto | Poder | Interés | Estrategia | Postura actual → deseada | Brecha a gestionar |
| --- | --- | --- | --- | --- | --- | --- |
| Dirección de la EPIIS | Patrocina y aprueba presupuesto y ventanas | Alto | Alto | Gestionar de cerca | Lidera → lidera | Aprobaciones oportunas, no solo respaldo |
| Soporte EPIIS / Ing. de Redes | Opera la red; dueño técnico de VLAN y DHCP (`6.viabilidad.tex:37`) | Alto | Alto | Gestionar de cerca | Neutral → apoya | Acceso de lectura a la configuración y validación de cada cambio |
| Logística / Abastecimiento UNSAAC | Ejecuta la compra de la Fase 0 (`6.viabilidad.tex:36`) | Alto | Bajo | Mantener satisfechos | Neutral → neutral informado | TDR cerrado y cotizaciones a tiempo (R-01) |
| Ing. Ademir Portillo | Referente técnico que reportó la IP manual (`2.problema.tex:16`) | Bajo | Alto | Mantener informado | Desconoce el proyecto → apoya | Acta fechada que convierta E3 en fuente verificable |
| Docentes que usan los laboratorios | Definen el horario de uso y sufren las ventanas de intervención | Bajo | Alto | Mantener informados | Desconocen → apoyan | Conformidad con las ventanas (RNF-01) |
| Estudiantes de los laboratorios | Usuarios de la red; participan en las pruebas | Bajo | Alto | Mantener informados | Desconocen → apoyan | Participación efectiva en la prueba de aceptación |
| Oficina de TI central (UNSAAC) | Dueña del enlace externo, fuera del alcance de la intervención | Alto | Bajo | Mantener satisfechos | Neutral → neutral con escalamiento comprometido | Respuesta formal al informe de estrés (R-02) |

## Tabla B · Plan de involucramiento

| Actor | Actual → deseado | Acción concreta | Responsable | Frecuencia | Indicador / evidencia |
| --- | --- | --- | --- | --- | --- |
| Dirección de la EPIIS | Lidera → lidera | Reunión de aprobación del presupuesto (S/ 27,940) y del plan de ventanas de intervención | Auccacusi | Inicio de Fase 0 y cierre | Acta o resolución de aprobación firmada |
| Soporte EPIIS / Ing. de Redes | Neutral → apoya | Acta de acceso de lectura a la configuración de DHCP y VLAN; revisión conjunta de rangos, concesiones y PortFast | Auccacusi | Fase 1 día 2; revisión en Fase 2 | Acta firmada + capturas fechadas de la configuración y de la tabla de concesiones |
| Logística / Abastecimiento | Neutral → neutral informado | Entrega del TDR con especificaciones cerradas y de 2 cotizaciones con RUC y fecha | Prieto | Inicio de Fase 0; seguimiento quincenal | Cargo de recepción del TDR, cotizaciones y orden de compra |
| Ing. Ademir Portillo | Desconoce → apoya | Entrevista con acta (`3-entrevista-portillo.md`) y validación de la afirmación «IP manual»: falla o política | León | Fase 1 día 1; revalidación en Fase 4 | Acta firmada por el entrevistado, con fecha y hora |
| Docentes de laboratorio | Desconocen → apoyan | Reunión de ventanas de intervención y aviso escrito antes de cada trabajo | León | Antes de Fase 3 y por hito | Cronograma de ventanas aceptado + correo o lista de asistencia |
| Estudiantes de laboratorio | Desconocen → apoyan | Convocatoria a la prueba piloto en hora punta y registro de incidencias durante una semana | Prieto | Fase 1 y Fase 4 | Planilla por equipo + registro de incidencias con fecha |
| Oficina de TI central | Neutral → escalamiento | Presentar el resultado de la prueba de estrés del enlace y solicitar compromiso de ancho de banda | Auccacusi | Una vez en Fase 1; seguimiento mensual | Informe de la prueba + respuesta formal (R-02) |

## Justificación con la evidencia disponible

La plantilla exige justificar cada acción con evidencia; esto es lo que existe
hoy y lo que falta:

| Actor | Evidencia disponible hoy | Hueco declarado |
| --- | --- | --- |
| Dirección | El cronograma asigna «Equipo Formulador» a la Fase 4 (`6.viabilidad.tex:40`) | No hay acta de aprobación ni de designación de responsable |
| Soporte EPIIS | Aparece como responsable de la Fase 1 (`6.viabilidad.tex:37`) | No hay acta de acceso ni inventario de puertos |
| Logística | Es la causa del riesgo R-01 (`7.costos.tex:51`) | No hay TDR entregado ni cotización con fecha |
| Ing. Portillo | Declaración E3, sin fecha ni acta (`2.problema.tex:40`) | Todo: la entrevista con el Ing. Portillo es la que lo convierte en fuente fechada |
| Docentes | El informe declara que reportan cortes (`1.finalidad.tex:17`) | Sin actas ni conteo de incidentes; sin horario de clases |
| Estudiantes | Aforo y uso de Colab/Drive declarados (`5.alcance.tex:13-14`) | Sin registro de incidencias ni de participación en pruebas |
| TI central | El enlace se declara excluido y a cargo de la UNSAAC (`5.alcance.tex:33`) | Sin ancho de banda contratado ni prueba de estrés |

## Reglas de comunicación, cambio y conflicto

- **Informar / consultar / involucrar** según la tabla A: la Dirección y Soporte
  deciden; Logística y TI central reciben información; docentes y estudiantes se
  involucran en validaciones y aceptación.
- **Cambio solicitado ≠ cambio aprobado**: solicitud → registro → análisis de
  impacto en alcance, cronograma, costo y riesgos → decisión → comunicación →
  seguimiento. Quien no esté en la columna «Responsable» no aprueba cambios.
- **Resistencia**: detectar la señal → escuchar la causa → negociar dentro del
  alcance → acordar y documentar → monitorear si mejoró la participación.
  Caso concreto del proyecto: si Soporte EPIIS resiste tocar el DHCP antes de la
  Fase 1, la salida es acordar una ventana de solo lectura y un acta.

## Vacíos que este plan no cubre todavía

- Las posturas actuales son hipótesis: no hay entrevistas ni actas previas.
- No existe sección de interesados en el informe; este plan es material de
  trabajo, no un apartado aprobado del documento.
- No se identificó al titular formal de la red del pabellón (cargo y nombre);
  hay que confirmarlo en la entrevista a Soporte EPIIS.
