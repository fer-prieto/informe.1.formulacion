# Aplicación del proyecto del equipo: árbol del problema V1

**Proyecto:** Conectividad para las actividades académicas en la Escuela Profesional de Ingeniería Informática y de Sistemas (EPIIS), UNSAAC.

**Integrantes:** Paul Andre Auccacusi Huanca; José Carlos León Maldonado (líder); David Fernando Prieto Cardoso.

**Responsable de organizar los registros:** Pendiente de asignar en Notion. Confirmar si el líder asumirá esta función.

**Estados usados:** **D** = declarado por una persona o en el material del equipo, sin que eso implique verificación; **H** = hipótesis pendiente de contraste; **S** = solución anticipada, fuera del árbol del problema.

## Alcance y diagnóstico del equipo

- **Usuarios:** estudiantes y docentes de la EPIIS; el personal administrativo también figura entre quienes reportan problemas y debe incluirse en la validación.
- **Servicio/proceso:** acceso a Internet que apoya clases, prácticas, evaluaciones, coordinación y trámites en línea.
- **Lugar:** todo el pabellón de la EPIIS, niveles 1 a 4. El cuadro compartido incluye aulas 101–108 y 201–206; laboratorios 111, 207–208, 301–306, 309–312 y 419; oficinas y secretarías; biblioteca; centro federado; cubículos; auditorio; salas de estudio, docentes y exposiciones; y pasadizos/pasillos. Verificar el inventario exacto de ambientes contra el plano y el TDR.
- **Periodo del diagnóstico:** pendiente de delimitar; no se proporcionaron fechas de observación.

**Solución anticipada S (no es el problema ni una causa comprobada):** mejora de la infraestructura de red del pabellón, incluidos puntos de red, acceso Wi-Fi, configuración de DHCP en laboratorios y posibles ajustes de capacidad/topología. El cuadro proporcionado declara 25 puntos para el primer nivel, 49 para el segundo, 219 para el tercero y 125 para el cuarto: **418 en total según esos subtotales**. El detalle transcrito del cuarto nivel está incompleto, por lo que su subtotal y el total deben cotejarse con el documento fuente. Estas cantidades describen la propuesta, no prueban que exista una falla ni que esa solución sea necesaria.

## 1. Formular el problema central

### A. Solución anticipada que aparece en la propuesta S

Mejora e implementación de infraestructura de red para el pabellón completo: instalación de puntos de red y acceso Wi-Fi, automatización del direccionamiento IP en laboratorios y eventual ajuste de capacidad/topología. La propuesta incluye las cantidades resumidas por nivel en el apartado anterior; verificar el desglose del cuarto nivel.

### B. Situaciones observadas o reportadas y quién las reporta

- Se declaró que en algunas aulas no aparece la señal Wi-Fi; no se entregó registro con aula, fecha u hora.
- Estudiantes, docentes y personal administrativo reportaron cortes; no se proporcionaron actas ni un conteo de incidentes.
- El Ing. Ademir Portillo fue señalado como fuente de la declaración de que en laboratorios se requiere configurar la IP manualmente; faltan fecha y registro de la entrevista.
- Se mencionó lentitud, pero la lentitud en datos móviles personales no demuestra lentitud de la red institucional. No hay mediciones de esta última.

Estas afirmaciones se conservan como **D (declaradas)**, no como hechos medidos ni como relaciones causales demostradas.

### C. Problema central candidato

**Interrupciones, lentitud e impedimentos de acceso a Internet durante actividades académicas de estudiantes y docentes en los ambientes del pabellón de la EPIIS, en el periodo que delimite el diagnóstico.**

Es un candidato pendiente de constatación. Si los registros muestran que falta de señal, lentitud, cortes y configuración manual son problemas distintos, el equipo dividirá este enunciado en problemas centrales más específicos.

### D. Cómo se observará o medirá la condición y qué referencia justifica el calificativo

Registrar cada episodio con ambiente, fecha y hora, actividad afectada, síntoma, dispositivo y fuente. Separar: red no visible; red visible sin navegación; lentitud; corte; necesidad de configurar IP manualmente. Medir cobertura y disponibilidad por ambiente, pruebas de conectividad y velocidad en horas punta y valle, cortes y su duración, usuarios concurrentes y asignación DHCP en laboratorios. Definir antes de analizar los resultados qué umbral o requisito del servicio permitirá llamar “lento” o “interrumpido”; ese referente todavía está pendiente.

### Respaldo disponible del problema

| Fuente declarada | Qué demuestra y qué no demuestra |
|---|---|
| E1. Declaración de aulas sin señal Wi-Fi; observación sin registro. Fecha, hora y ambientes exactos: pendientes. | D: se reportó percepción de falta de señal. No demuestra frecuencia, cobertura medida, magnitud ni causa. |
| E2. Quejas de estudiantes, docentes y personal administrativo por cortes. Fechas, actas y localizador: pendientes. | D: hay reclamos reportados. No cuantifica incidentes ni identifica su origen. |
| E3. Declaración atribuida al Ing. Ademir Portillo sobre el uso obligatorio de IP manual en laboratorios. Fecha y registro: pendientes. | D: se reportó ese requisito. No demuestra que DHCP esté ausente o mal configurado, ni por qué se requiere IP manual. |
| E4. Referencia a lentitud en datos móviles particulares. Fecha y fuente específica: pendientes. | D: se mencionó el uso de una red particular. No demuestra lentitud de la red institucional. |

**Estado del problema y dato principal que falta:** problema candidato sustentado por declaraciones, todavía no documentado mediante registros fechados. Faltan episodios observables por ambiente, periodo, tarea afectada y síntoma, además de mediciones de la red institucional.

## 2. Proponer y ordenar las causas

Las causas y flechas siguientes son candidatas. Que un síntoma haya sido declarado no prueba que la explicación propuesta lo haya producido.

### Causas directas candidatas

| ID | Condición que podría contribuir directamente al problema | Mecanismo propuesto y estado |
|---|---|---|
| CD1 | Wi-Fi no visible o sin acceso utilizable en algunas aulas reportadas. | Sin conexión disponible, una actividad que requiere Internet podría detenerse. D como reporte; ubicación y existencia pendientes de verificar. |
| CD2 | Necesidad reportada de configurar la IP manualmente en laboratorios. | La configuración manual añade pasos y podría demorar o impedir el acceso durante una actividad. D como declaración; efecto pendiente de comprobar. |
| CD3 | Cortes de conexión reportados durante el uso. | La pérdida de conexión podría interrumpir tareas y obligar a reconectar. D como queja, sin registro ni frecuencia. |
| CD4 | Acceso institucional descrito como lento. | Una respuesta lenta podría demorar tareas en línea. Declaración sin medición; la lentitud de datos móviles no la verifica. |

### Causas indirectas candidatas

| ID | Condición que podría explicar una causa directa | Causa directa que explicaría y mecanismo; estado |
|---|---|---|
| CI1 | Cobertura insuficiente o puntos de acceso mal ubicados o apagados. | Podría explicar CD1 si deja zonas sin señal. H; verificar cobertura y estado de los equipos. |
| CI2 | DHCP ausente o mal configurado en laboratorios. | Podría explicar CD2 si los dispositivos no reciben automáticamente una dirección IP válida. H; revisar configuración y concesiones. |
| CI3 | Falla de autenticación o del enlace. | Podría explicar CD3 si impide mantener la sesión de red. H; contrastar con registros sincronizados del incidente. |
| CI4 | Congestión o capacidad de ancho de banda insuficiente en horas punta. | Podría explicar CD4 si el rendimiento cae con mayor concurrencia. H; comparar mediciones y cantidad de usuarios. |

**Explicaciones rivales por comprobar:** configuración o falla del dispositivo del usuario; cableado antiguo; interferencia; autenticación; conexión del participante o proveedor externo; y diferencias entre la red institucional y los datos móviles personales.

**Observaciones que debilitarían las hipótesis:** señal y punto de acceso operativos en el aula y hora reportadas; DHCP que entrega direcciones válidas cuando ocurre el problema; registros de enlace/autenticación normales durante un corte; o lentitud también fuera de horas punta y con pocos usuarios. Si aparece alguna de estas observaciones, revisar la rama y sus explicaciones rivales.

## 3. Ordenar los efectos y dibujar el árbol

| ID y nivel | Condición resultante candidata | De qué nodo se deriva y cómo; estado |
|---|---|---|
| ED1 Directo | Tareas académicas en línea demoradas o pendientes, por ejemplo prácticas, evaluaciones o actividades de clase que requieren Internet. | Podrían derivarse de la interrupción, lentitud o impedimento de acceso. H; no se aportaron actividades ni fechas que lo documenten. |
| EI1 Indirecto | Menor continuidad de las actividades de aprendizaje mediadas por Internet y posible afectación de la experiencia o calidad percibida del aprendizaje. | Podría producirse si los retrasos o tareas pendientes son repetidos y afectan el desarrollo de las actividades. H; no hay mediciones ni evidencia de impacto en aprendizaje. |

**Beneficio esperado de la propuesta, no resultado demostrado:** si el diagnóstico confirma el problema y se implementa una solución eficaz, un acceso más continuo podría facilitar clases y prácticas y contribuir a una mejor experiencia de aprendizaje. No se presenta como efecto observado ni como causalidad comprobada.

### Árbol V1 del proyecto
![[Pasted image 20261014184149.png]]
**Versión y fecha:** V1, 14/10/2026. El periodo de observación sigue pendiente. **S** (instalación/mejora de red, puntos de red, Wi-Fi, DHCP y ajustes de capacidad/topología) se registra fuera del árbol. Todas las flechas están en estado H; los nodos declarados no están por ello documentados.

## 4. Contrastar las relaciones causales prioritarias

### Registro del vínculo 1 — prioridad: señal Wi-Fi y acceso interrumpido

**Código y relación:** **F2 — CD1 (Wi-Fi no visible o no utilizable en el ambiente) → P1 (impedimento o interrupción del acceso durante una actividad académica).**

**Mecanismo y condición:** si en un ambiente y momento determinados no hay señal o acceso utilizable, un dispositivo que depende de esa red podría no conectarse y la actividad académica que requiere Internet podría detenerse. No se espera necesariamente esa consecuencia si existe una alternativa funcional o el problema se limita a un dispositivo.

**Evidencia de A, de B y del vínculo:** A: E1, declaración de aulas sin señal, sin ambiente, fecha ni medición registrados. B: problema candidato construido a partir de los reportes; no hay registro fechado de una actividad interrumpida. El vínculo entre ambos no está medido. **Estado: H.**

**Explicación rival o evidencia contradictoria:** falla o configuración del dispositivo; SSID o autenticación; punto de acceso apagado; interferencia; o caída del enlace externo. Señal y acceso funcionales en el aula y momento reportados debilitarían esta relación.

**Dato o prueba diagnóstica:** registrar aula, fecha/hora, tarea y dispositivo; revisar estado del AP y medir si varios dispositivos detectan y usan la red; anotar si la tarea se detuvo. Apoyaría la hipótesis una falta de señal/acceso coincidente con la interrupción en varios dispositivos y sin una explicación rival suficiente. La debilitaría que la red funcione y el fallo ocurra solo en un dispositivo.

**Estado, límites, responsable y fecha:** H, pendiente de comprobación; el reporte disponible no permite estimar frecuencia ni atribuir causa. Responsable y fecha por asignar en Notion.

### Registro del vínculo 2 — prioridad: IP manual y acceso dificultoso

**Código y relación:** **F4 — CD2 (necesidad reportada de configurar IP manualmente en laboratorios) → P1 (dificultad o demora para acceder a Internet durante una actividad).**

**Mecanismo y condición:** si el equipo no obtiene automáticamente una dirección IP válida y se necesita configurarla manualmente, el paso adicional podría retrasar o impedir el acceso. La relación se espera solo si esa configuración coincide con una demora o impedimento en una actividad concreta.

**Evidencia de A, de B y del vínculo:** A: E3, declaración atribuida al Ing. Ademir Portillo; fecha, registro y laboratorios específicos pendientes. B: el problema es candidato y no se entregaron episodios fechados. La declaración no demuestra por sí sola que DHCP sea la causa ni que haya ocurrido una demora académica. **Estado del vínculo: H.**

**Explicación rival o evidencia contradictoria:** configuración del dispositivo, política de acceso del laboratorio u otra restricción. Si DHCP entrega una dirección válida durante el episodio o la configuración manual no cambia el acceso, se debilitaría la hipótesis de que DHCP explica la dificultad.

**Dato o prueba diagnóstica:** revisar configuración y concesiones DHCP; probar varios dispositivos en los laboratorios; registrar si reciben IP automáticamente, cuánto tarda el acceso y qué actividad se ve afectada; comparar con un caso en que la conexión funcione. Apoyaría la hipótesis que no se asigne una IP válida y que la configuración manual restablezca el acceso en el episodio. La debilitaría que DHCP funcione o que el problema persista sin relación con la IP.

**Estado, límites, responsable y fecha:** H, pendiente de comprobación; existe una declaración, no un registro técnico ni una prueba del vínculo causal. Responsable y fecha por asignar en Notion.
