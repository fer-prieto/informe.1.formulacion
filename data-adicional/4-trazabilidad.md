# Trazabilidad y registro V1 → V2

Curso IF483BIN · EPIIS–UNSAAC · Equipo: Auccacusi, León, Prieto

Instrumento base: matriz de trazabilidad del 20 oct (código · necesidad ·
requerimiento · fuente · verificación) y cadena evidencia → problema → objetivo →
alternativa → requisito → costo del 05 nov. Cierra las fichas de
`1-requisitos.md` y el plan de `2-plan-involucramiento.md`.

## 1. Cadena completa por requisito

| Requisito (V2) | Evidencia · fuente | Necesidad / causa | Objetivo (`3.objetivos.tex`) | Entregable (`5.alcance.tex:23-26`) | Verificación | Partida de costo (`7.costos.tex`) |
| --- | --- | --- | --- | --- | --- | --- |
| RF-01 Asignación automática de IP | E3 (`2.problema.tex:40`), sin fecha | CD2 → CI2, ambas en D/H (`2.problema.tex:71,89`) | Objetivo específico 3: verificar configuración y concesiones DHCP | Rediseño lógico: VLAN y DHCP en los laboratorios confirmados | Prueba de concesión con N equipos, en punta y valle | 5. Servicios S/ 3,500 + 1. Switches S/ 13,600 si el DHCP va en ellos |
| RF-02 Desempeño Wi-Fi interna | Figura 1, 0.14 Mbps (`8.anexos.tex:5`), sin fecha | CD4 → CI4, ambas en D/H | Objetivo específico 2: verificar cobertura y estado de los AP | Despliegue físico en los 4 laboratorios críticos | Prueba interna contra servidor de la VLAN | 2. AP S/ 4,000 + 1. Switches S/ 13,600 + 4. Materiales S/ 1,800 + 5. Servicios |
| RF-03 Servicios locales desde VLAN | Declaración de usuarios (`5.alcance.tex:14`), sin inventario | Necesidad declarada, **sin causa en el árbol** | **Sin objetivo explícito en V1** | Rediseño lógico + pruebas de aceptación | Matriz servicio × VLAN, antes y después | Sin hardware; horas dentro de 5. Servicios S/ 3,500 |
| RNF-01 Continuidad y ventanas | Aforo y ocupación declarados (`5.alcance.tex:13`) | **Sin causa en el árbol**; riesgo R-04 (`7.costos.tex:54`) | **Sin objetivo explícito en V1** | Ventanas de intervención del cronograma (`6.viabilidad.tex:38-39`) | Inspección documental del registro de ventanas | Sin partida propia; posible recargo en 5. Servicios |
| RNF-02 Capacidad y concurrencia | Aforo 24 (`5.alcance.tex:13`), declarado | CI4 en H | **Sin objetivo explícito en V1** | Dimensionamiento de switches y AP | Prueba de carga con N dispositivos | Dimensiona 1, 2 y 4 |

Dos hallazgos de la cadena:

- **Tres requisitos no tienen objetivo al que responder** (RF-03, RNF-01,
  RNF-02). En la V2 hay que agregar el objetivo o retirar el requisito; dejarlos
  sin objetivo es exactamente lo que el 05 nov llama requisito desconectado.
- **Ningún requisito llega a una fuente fechada.** Todas las evidencias están en
  D o H; la entrevista con el Ing. Portillo es la primera que puede producir una fuente con
  fecha (E3).

## 2. Tres afirmaciones críticas, acotadas

| # | Afirmación de la V1 | Estado | Evidencia | Límite | Cómo se acota |
| --- | --- | --- | --- | --- | --- |
| A1 | «El acceso a Internet durante las actividades académicas es deficiente» | D | E1–E4: declaraciones de falta de señal, cortes, IP manual y lentitud (`2.problema.tex:38-41`) | Ninguna medición de la red institucional; la lentitud reportada corresponde a datos móviles personales | Se afirma como problema **candidato** y se mide en la Fase 1 por ambiente, fecha y hora |
| A2 | «Hay 8 laboratorios con fallas de asignación DHCP» | H | `4.alternativas.tex:7`, citando Figuras 1 y 2 | Las figuras son pruebas de velocidad (0.14 y 8.63 Mbps), la segunda desde el punto del docente: no documentan DHCP | Se convierte en «8 laboratorios por confirmar» hasta tener la lista y la prueba por aula |
| A3 | «Cada aula sostiene 24 usuarios concurrentes» | D | Aforo de 24 alumnos (`5.alcance.tex:13`) | Es capacidad de asientos, no de dispositivos ni de sesiones simultáneas | Se sustituye por N del inventario de la Fase 1, con el aforo como techo |

## 3. Registro V1 → V2 (qué cambió y qué arrastra)

| Requisito | Qué cambió | Por qué | Impacto en otros apartados |
| --- | --- | --- | --- |
| RF-01 | Se elimina «5 s»; se define qué es una IP válida; se fija el inicio de la medición; se separa la navegación a Internet | Umbral inventado y causa en H tratada como hecho | `5.alcance.tex:85` (criterio), `3.objetivos.tex:22` (indicador 3), `7.costos.tex:7` y `4.alternativas.tex:23` (dónde corre el DHCP) |
| RF-02 | Se elimina «0.14 Mbps» como meta; se separa red interna de salida a Internet; se exige condición de concurrencia | La meta era un dato único y se medía algo fuera del alcance | `5.alcance.tex:86`, dimensionamiento de la partida 2, fechas y condiciones de las Figuras 1 y 2 |
| RF-03 | Redacción en positivo; absorbe el duplicado RNF-04 | Requisito repetido (`5.alcance.tex:63` y `:76`) | `5.alcance.tex:76` se elimina; hace falta inventario de servidores |
| RNF-01 | Se separa ventana de intervención de disponibilidad; se exige autorización escrita y duración máxima | El título prometía disponibilidad y el texto fijaba un horario sin fuente | `6.viabilidad.tex:7`, riesgo R-04 (`7.costos.tex:54`) |
| RNF-02 | Se define qué se mide; N remite al inventario; el aforo queda como techo | La cifra venía del aforo, no de un inventario | `5.alcance.tex:13-14` (perfil de carga y usuarios) |
| RNF-03 | No se reescribe: pasa a restricción RI-01 | Por la clasificación del 20 oct es compatibilidad/integración, no calidad | Cambia de grupo en `5.alcance.tex:75` |
| RNF-04 | Se elimina | Duplicado de RF-03 | — |

## 4. Impacto si un eslabón cambia

- Si la Fase 1 muestra DHCP operativo → RF-01 no aplica en esos laboratorios; se
  cae la mitad lógica de la Alternativa B y la partida 5 se reduce a instalación
  física (riesgo R-03, `7.costos.tex:53`).
- Si la lentitud es del enlace de la UNSAAC → RF-02 no se cumple con hardware
  nuevo: la respuesta es escalar a TI central (R-02), no comprar más AP.
- Si la IP manual resulta ser política del laboratorio → CD2 deja de ser causa y
  el problema central candidato (`2.problema.tex:22`) se divide.
- Si el inventario muestra más dispositivos que el aforo → cambian N, RNF-02 y
  el dimensionamiento de las partidas 1, 2 y 4.

## 5. Inconsistencias de la V1 detectadas (para corregir antes de la V2)

| # | Inconsistencia | Dónde |
| --- | --- | --- |
| 1 | Tres conteos distintos de laboratorios: 12 en el alcance, 8 con fallas DHCP, 4 críticos; el problema lista 14 ambientes | `5.alcance.tex:7,23,24` vs `2.problema.tex:52` |
| 2 | El DHCP corre en un «servidor dedicado» o en el switch L3, según el apartado | `4.alternativas.tex:23` vs `7.costos.tex:7` |
| 3 | RF-03 y RNF-04 son el mismo requisito | `5.alcance.tex:63` y `:76` |
| 4 | Se declara «sin costos recurrentes» y a la vez se compran licencias de gestión y soporte | `7.costos.tex:34` vs partida 3 |
| 5 | No hay horizonte de TCO definido | `7.costos.tex:39` |
| 6 | El presupuesto no tiene fuente ni fecha por partida (la aritmética sí cuadra: 25,400 + 10 % = 27,940) | `7.costos.tex:16-29` |
| 7 | Las Figuras 1 y 2 no tienen fecha, hora ni laboratorio, y la segunda se tomó en el punto del docente | `8.anexos.tex:5-7` |

## 6. Qué falta para que la matriz esté completa

- Fuente fechada por requisito: depende de la entrevista con el Ing. Portillo y de los
  registros de la Fase 1.
- Objetivo explícito para RF-03, RNF-01 y RNF-02, o su retiro.
- Cotizaciones con RUC y fecha para las cinco partidas.
