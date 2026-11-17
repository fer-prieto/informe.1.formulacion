# Cinco requisitos replanteados — Formulación V2

Curso IF483BIN · EPIIS–UNSAAC · Equipo: Paul Andre Auccacusi Huanca (211355),
Jose Carlos Leon Maldonado (215786), David Fernando Prieto Cardoso (210179)

Base: `src/main/sections/5.alcance.tex` (V1). Formato: ficha de corrección de
cinco campos del 05 nov y redacción
`[sujeto] + deberá + [capacidad] + [contexto] + [criterio de verificación]`
del 20 oct. Todas las referencias `archivo:línea` apuntan al informe.

## Qué se reescribe y qué no

| Código V1 | Estado en V2 | Motivo |
| --- | --- | --- |
| RF-01 Asignación IP | Ficha 1 | Umbral inventado y causa tratada como hecho |
| RF-02 Wi-Fi 4 laboratorios | Ficha 2 | Meta sin sustento y medición de algo fuera del alcance |
| RF-03 Servicios locales | Ficha 3 | Redactado en negativo; absorbe el duplicado RNF-04 |
| RNF-01 Disponibilidad | Ficha 4 | Confunde ventana horaria con disponibilidad |
| RNF-02 Capacidad | Ficha 5 | La cifra sale del aforo, no de un inventario |
| RNF-03 Compatibilidad | No se reescribe | Por la clasificación del curso es una **restricción**: pasa a RI-01 |
| RNF-04 Segmentación segura | Se elimina | Es el mismo requisito que RF-03 (`5.alcance.tex:63` y `:76`) |

Regla aplicada: ningún umbral nuevo. Donde la V1 no tiene fuente, el valor queda
como `T_…` a fijar con la línea base de la Fase 1, con acción y responsable.

---

## Ficha 1 — RF-01 Asignación automática de IP

**1. Requisito original y necesidad a la que responde**

- Original (V1): «la red debe asignar una dirección IPv4 válida (DHCP) en menos
  de 5 segundos al conectar un equipo por cable en los 8 laboratorios
  afectados» (`5.alcance.tex:55`).
- Necesidad: que nadie tenga que configurar la IP a mano en los laboratorios
  (CD2, `2.problema.tex:71`).
- Fallas detectadas:
  - los «5 segundos» no tienen fuente, y el mismo informe dice que los umbrales
    se fijan después de la Fase 1 (`5.alcance.tex:89`, `3.objetivos.tex:22`);
  - «8 laboratorios» no se identifican: el problema lista 14 ambientes
    (`2.problema.tex:52`) y el alcance dice 12 (`5.alcance.tex:7`);
  - trata la causa como hecho: CI2 «DHCP ausente o mal configurado» está en
    estado H (`2.problema.tex:89`);
  - la IP manual podría ser una política del laboratorio, no una falla
    (`2.problema.tex:153`);
  - «IPv4 válida» no está definida (rango de la VLAN, máscara, puerta de
    enlace, DNS; no sirve una 169.254.x.x);
  - «al conectar» no fija desde cuándo se mide: sin PortFast, STP agrega unos
    30 s;
  - la prueba exige «navegación exitosa», que depende del enlace de la UNSAAC,
    excluido del alcance (`5.alcance.tex:33`, R-02 en `7.costos.tex:52`);
  - «24 equipos» viene del aforo de alumnos (`5.alcance.tex:13`), no de un
    inventario de PCs;
  - contradicción sobre dónde corre el DHCP: «servidor DHCP dedicado»
    (`4.alternativas.tex:23`) frente a «se retiró el servidor y el rol pasa al
    switch L3» (`7.costos.tex:7`).

**2. Evidencia: fuente, fecha y límite**

| Evidencia | Fuente | Fecha | Límite (qué no demuestra) |
| --- | --- | --- | --- |
| E3, declaración sobre IP manual | `2.problema.tex:40`, atribuida al Ing. Ademir Portillo | pendiente (sin acta) | No demuestra que DHCP falle, ni en qué laboratorios, ni que haya demorado una actividad |
| «8 laboratorios con fallas DHCP» | `4.alternativas.tex:7`, citando Figuras 1 y 2 | sin fecha | Las figuras son pruebas de velocidad (0.14 / 8.63 Mbps): no dicen nada de la asignación DHCP |
| Árbol V1 | equipo formulador | 14/10/2026 (`2.problema.tex:124`) | El vínculo CD2→P1 está en H |
| «5 s» | ninguna | — | Umbral inventado |

Conclusión: hoy RF-01 se apoya en una sola declaración sin fecha. Se sostiene
como requisito **condicionado** a la Fase 1, no como requisito confirmado.

**3. Redacción mejorada (sin umbrales inventados)**

> En los laboratorios que el diagnóstico de la Fase 1 confirme con falla de
> asignación, todo equipo conectado por cable a un puerto de usuario deberá
> obtener, sin configuración manual, una configuración IPv4 completa —dirección
> dentro del rango asignado a la VLAN del laboratorio, máscara, puerta de enlace
> y DNS— incluso cuando se conecten a la vez todos los equipos cableados del
> laboratorio. El tiempo máximo admisible (T_IP), medido desde que el puerto se
> activa hasta que el equipo recibe su dirección, se fija con la línea base
> medida en la Fase 1.

Condición de aplicación: se activa solo si la Fase 1 confirma (a) que los
equipos no obtienen configuración automática y (b) que la configuración manual
no responde a una política vigente del laboratorio.

Pendientes: lista de laboratorios con falla, cantidad de equipos cableados y
T_IP (tabla final de pendientes).

**4. Prueba o criterio de aceptación**

Con el DHCP configurado y PortFast en los puertos de usuario, se conectan a la
vez los N equipos cableados del inventario, en hora punta (09:00–11:00 o
16:00–18:00) y en hora valle. Se acepta si:

1. el 100 % de los N equipos recibe una dirección dentro del rango de su VLAN,
   sin 169.254.x.x y sin IP fija;
2. cada equipo hace ping a la puerta de enlace y resuelve un nombre en el DNS
   configurado;
3. el tiempo puerto activo → dirección recibida es ≤ T_IP en todos los equipos;
4. no aparecen direcciones duplicadas ni se agota el rango.

Evidencia que se registra: fecha, hora, laboratorio y responsable; tabla de
concesiones antes y después; captura de tráfico de al menos un equipo para los
tiempos; planilla con un resultado por equipo.
No se evalúa la navegación a Internet (depende del enlace UNSAAC, R-02).

**5. Costo asociado: fuente y supuesto pendiente**

| Partida (`7.costos.tex:16-21`) | Relación con RF-01 | Fuente | Supuesto pendiente |
| --- | --- | --- | --- |
| 5. Servicios, S/ 3,500 | Incluye la configuración lógica, mezclada con la instalación física | pendiente (`7.costos.tex:29`) | Separar horas de VLAN/DHCP de las de instalación física |
| 1. Switches Catalyst ×4, S/ 13,600 | Solo si el DHCP corre en ellos | pendiente | Definir si el DHCP va en los switches nuevos o en el equipo de distribución existente; si va en el existente, RF-01 casi no cuesta hardware |
| 3. Licencias, S/ 2,500 | Indirecta | pendiente | Confirmar si son suscripciones con renovación anual (afecta el «sin costos recurrentes» de `7.costos.tex:34`) |

---

## Ficha 2 — RF-02 Desempeño de la red inalámbrica interna

**1. Requisito original y necesidad a la que responde**

- Original (V1): «la red Wi-Fi en los 4 laboratorios críticos debe superar los
  anchos de banda actuales de 0.14 Mbps, permitiendo la ejecución fluida de
  entornos como Google Colab y carga de archivos a Drive» (`5.alcance.tex:59`).
- Necesidad: que una clase pueda usar Colab, Classroom y Drive por Wi-Fi sin que
  la conexión detenga la actividad (CD4, lentitud reportada; perfil de usuarios
  en `5.alcance.tex:14`).
- Fallas detectadas:
  - «superar 0.14 Mbps» no es una meta: 0.15 Mbps ya la cumpliría, y 0.14 es
    una sola medición sin fecha;
  - «fluida» no es medible;
  - mide el acceso a Internet, que depende del enlace de la UNSAAC, excluido del
    alcance (`5.alcance.tex:33`);
  - no separa la red interna (WLAN + switch) de la salida al exterior;
  - no fija condiciones de la prueba: hora, cantidad de usuarios, dispositivo;
  - a diferencia de RF-01, aquí **sí** están identificados los laboratorios
    (309–312, `4.alternativas.tex:7`).

**2. Evidencia: fuente, fecha y límite**

| Evidencia | Fuente | Fecha | Límite |
| --- | --- | --- | --- |
| Figura 1, Wi-Fi 0.14 Mbps de bajada y 0.00 de subida | `8.anexos.tex:5`, citada en `4.alternativas.tex:7` | no aparece | Una sola prueba, un solo equipo; sin laboratorio, hora ni usuarios; la captura muestra un operador móvil, hay que verificar que sea la red institucional |
| Figura 2, cableado 8.63 Mbps (punto del docente) | `8.anexos.tex:7` | no aparece | Es un contraste, no una línea base; mide salida a Internet, no la red interna |
| Perfil de usuarios y aforo (24 alumnos, punta 09–11 y 16–18) | `5.alcance.tex:13-14` | — | Declarado por el equipo; no hay conteo de sesiones simultáneas |

**3. Redacción mejorada (sin umbrales inventados)**

> En los laboratorios 309–312, la red inalámbrica interna deberá entregar a cada
> usuario asociado, con los dispositivos del laboratorio conectados
> simultáneamente en hora punta, una velocidad de bajada, una de subida y una
> latencia no peores que los mínimos que se fijen con la línea base interna
> medida en la Fase 1. La medición de la salida a Internet se registra por
> separado y no forma parte de la aceptación.

Pendientes: confirmar en la Fase 1 que 309–312 son los laboratorios con lentitud
crítica y fijar los mínimos de bajada, subida y latencia.

**4. Prueba o criterio de aceptación**

En cada laboratorio, en hora punta y en hora valle, con N dispositivos
conectados a la vez:

1. prueba interna contra un servidor dentro de la misma VLAN (bajada, subida,
   latencia y pérdida): se acepta si cumple los mínimos fijados en la Fase 1;
2. prueba de sesión real (abrir un cuaderno de Colab y subir un archivo a
   Drive) registrada como observación;
3. se registran fecha, hora, laboratorio, cantidad de dispositivos y modelo de
   equipo.

Si la prueba interna cumple y la de Internet no, el problema está en el enlace
de la UNSAAC (R-02) y RF-02 no falla.

**5. Costo asociado: fuente y supuesto pendiente**

| Partida | Relación | Fuente | Supuesto pendiente |
| --- | --- | --- | --- |
| 2. Access Point Aruba AP-505 ×4, S/ 4,000 | 1 por laboratorio crítico | pendiente | Si la densidad exige 2 por laboratorio, la partida se duplica |
| 1. Switches Catalyst ×4, S/ 13,600 | Sostienen la WLAN de los 4 laboratorios | pendiente | Confirmar que atienden los 4 críticos y no otros ambientes |
| 4. Materiales Cat 6, S/ 1,800 | Cableado de los AP | pendiente | — |
| 5. Servicios, S/ 3,500 | Instalación y configuración | pendiente | — |

Supuesto de fondo: que la lentitud sea de la red local y no del enlace. Si es
del enlace, comprar equipos no la resuelve (R-02, `7.costos.tex:52`).

---

## Ficha 3 — RF-03 Acceso a servicios locales desde las VLAN

**1. Requisito original y necesidad a la que responde**

- Original (V1): «la segmentación de red no debe impedir que los estudiantes de
  EPIIS accedan a los servidores locales requeridos para cursos de
  especialidad» (`5.alcance.tex:63`), repetido como RNF-04 en `:76`.
- Necesidad: que los estudiantes de Informática y Sistemas sigan llegando a
  nube, desarrollo, bases de datos y servidores locales de su malla
  (`5.alcance.tex:14`).
- Fallas detectadas:
  - está redactado en negativo («no debe impedir»): describe una condición de la
    solución, no una capacidad del servicio;
  - no dice desde qué VLAN, hacia qué servidores, con qué protocolo ni puerto;
  - no existe inventario de servidores locales ni estado inicial que comparar;
  - el riesgo R-05 (`7.costos.tex:55`) reconoce la pérdida de visibilidad, pero
    no hay medición previa;
  - RNF-04 (`:76`) es el mismo requisito escrito dos veces.

**2. Evidencia: fuente, fecha y límite**

| Evidencia | Fuente | Fecha | Límite |
| --- | --- | --- | --- |
| Necesidad de acceso a servidores locales de especialidad | `5.alcance.tex:14` (declaración del equipo) | — | No hay inventario de servidores, ni lista de servicios por curso, ni prueba de acceso |
| Riesgo R-05 de pérdida de visibilidad | `7.costos.tex:55` | — | Es un riesgo anticipado, no una observación |

**3. Redacción mejorada**

> Desde cada VLAN de laboratorio intervenida, un equipo deberá alcanzar los
> servicios locales registrados en el inventario de la Fase 1 —servicio, equipo,
> protocolo y puerto— en el mismo estado en que se encuentren antes de la
> intervención: un servicio accesible antes seguirá siendo accesible después, y
> uno inaccesible antes no empeorará.

Pendientes: inventario de servidores y servicios locales, con su estado inicial
medido en la Fase 1.

**4. Prueba o criterio de aceptación**

Matriz servicio × VLAN, ejecutada desde un equipo por laboratorio: ping y
conexión al puerto correspondiente (SSH 22, HTTP/HTTPS, base de datos) antes y
después de la segmentación, con fecha, hora y responsable. Se acepta si ninguna
celda pasa de accesible a inaccesible.

**5. Costo asociado: fuente y supuesto pendiente**

Sin hardware propio. Las horas de configuración de ACL y ruteo inter-VLAN caen
dentro de la partida 5 (Servicios, S/ 3,500), que no tiene fuente ni fecha
(`7.costos.tex:29`). Supuesto pendiente: cuantizar esas horas aparte.

---

## Ficha 4 — RNF-01 Continuidad del servicio y ventanas de intervención

**1. Requisito original y necesidad a la que responde**

- Original (V1): «las intervenciones físicas y los reinicios de red se ejecutan
  fuera del horario de clases pico (después de las 20:00 horas o fines de
  semana), para no interrumpir el servicio» (`5.alcance.tex:73`).
- Necesidad: que las clases no se detengan por una intervención del proyecto
  (misma finalidad que la sección 1: continuidad del acceso).
- Fallas detectadas:
  - el título promete disponibilidad y el texto solo fija una ventana horaria:
    no hay indicador de disponibilidad;
  - «después de las 20:00» y «fines de semana» son valores sin fuente: no se
    verificó si hay clases nocturnas, acceso al pabellón ni vigilancia;
  - no dice quién autoriza la ventana ni con cuánta antelación se avisa;
  - no fija duración máxima de la interrupción;
  - el mismo supuesto aparece como riesgo R-04 (`7.costos.tex:54`) sin medición
    de ocupación nocturna.

**2. Evidencia: fuente, fecha y límite**

| Evidencia | Fuente | Fecha | Límite |
| --- | --- | --- | --- |
| Ocupación del 50 % al 70 % fuera de punta | `5.alcance.tex:13` | — | Declarada por el equipo; no hay aforo medido ni horario de clases |
| Riesgo R-04 (reinicios en horario de clase) | `7.costos.tex:54` | — | Riesgo anticipado, no incidente registrado |

**3. Redacción mejorada**

> Ninguna intervención que interrumpa el servicio se ejecutará en las franjas de
> uso pleno declaradas (09:00–11:00 y 16:00–18:00) ni durante clases en curso.
> Cada ventana deberá estar autorizada por escrito por la instancia competente,
> comunicada a los usuarios con antelación y con una duración máxima fijada en
> el cronograma de la Fase 3. La disponibilidad objetivo del servicio se fija
> con la línea base de la Fase 1.

Pendientes: horario real de uso nocturno y fin de semana, instancia que autoriza
y duración máxima admisible por ventana.

**4. Prueba o criterio de aceptación**

Registro de ventanas (fecha, hora de inicio y fin, autorización, servicios
afectados) contrastado con el horario de clases. Se acepta si ninguna ventana
cae en las franjas declaradas y el 100 % tiene autorización documentada.
Verificación por inspección documental, no por prueba de carga.

**5. Costo asociado: fuente y supuesto pendiente**

Sin partida propia. Un recargo por trabajo nocturno o de fin de semana caería en
la partida 5 (S/ 3,500), sin fuente. Supuesto pendiente: preguntar al proveedor
si cobra recargo fuera de horario.

---

## Ficha 5 — RNF-02 Capacidad y concurrencia

**1. Requisito original y necesidad a la que responde**

- Original (V1): «la solución debe soportar 24 usuarios concurrentes por aula al
  100 % de ocupación en horas pico» (`5.alcance.tex:74`).
- Necesidad: que la red sostenga el aula llena en hora punta (CD4, CI4 en H;
  aforo y franjas en `5.alcance.tex:13`).
- Fallas detectadas:
  - el 24 sale del aforo de alumnos (`5.alcance.tex:13`), no de un inventario de
    equipos ni de una medición de concurrencia;
  - «soportar» no dice qué se mide: asociaciones, rendimiento por usuario,
    concesiones DHCP o desconexiones;
  - no fija la métrica ni la condición de la prueba;
  - duplica parcialmente RF-01 y RF-02 sin criterio propio.

**2. Evidencia: fuente, fecha y límite**

| Evidencia | Fuente | Fecha | Límite |
| --- | --- | --- | --- |
| Aforo de 24 alumnos y ocupación 50–70 % | `5.alcance.tex:13` | — | Declarado; no hay conteo de equipos ni de sesiones simultáneas |
| Indicador de tiempo de conexión a Internet | `3.objetivos.tex:22` | — | Reconoce que la meta se define después del diagnóstico |

**3. Redacción mejorada**

> En cada laboratorio intervenido, la solución deberá sostener N dispositivos
> conectados simultáneamente sin que se deje de cumplir RF-01 y RF-02, donde N
> es la cantidad de equipos cableados y dispositivos inalámbricos registrada en
> el inventario de la Fase 1, y el aforo declarado de 24 alumnos por aula se usa
> solo como techo de referencia. La concurrencia efectiva se mide en la Fase 1.

Pendientes: N por laboratorio (inventario de equipos y puertos activos).

**4. Prueba o criterio de aceptación**

Prueba de carga con N dispositivos (o generador equivalente) en hora punta y en
hora valle, registrando asociaciones fallidas, desconexiones y concesiones DHCP.
Se acepta si con N simultáneos se cumplen los criterios de RF-01 y RF-02.

**5. Costo asociado: fuente y supuesto pendiente**

Es el requisito que dimensiona las partidas 1 (switches, S/ 13,600), 2 (AP,
S/ 4,000) y 4 (materiales, S/ 1,800), todas sin fuente ni fecha
(`7.costos.tex:29`). Supuesto pendiente: cuántos dispositivos por aula hay
realmente; si N supera las capacidades de la partida 2, el dimensionamiento
cambia.

---

## Pendientes consolidados (acción, responsable y plazo)

Responsables: A = Auccacusi, L = León, P = Prieto, S = Soporte EPIIS.

| Requisito | Pendiente | Acción | Resp. | Plazo |
| --- | --- | --- | --- | --- |
| RF-01 | Lista de laboratorios con falla | Probar con 3 equipos por laboratorio si reciben IP automática y anotar por aula | L | Fase 1, días 1–3 |
| RF-01 | Cantidad de equipos cableados | Contar equipos y puertos activos por laboratorio | P | Fase 1, días 1–3 |
| RF-01 | T_IP | Medir 5 veces por laboratorio el tiempo puerto activo → IP, en punta y valle | L | Fase 1, días 3–5 |
| RF-01 | Dónde corre el DHCP | Confirmar con Soporte si el equipo de distribución actual puede ser servidor DHCP | A | Fase 1, día 2 |
| RF-02 | Confirmar 309–312 como críticos y fijar mínimos | Prueba interna (`iperf3`) en cada laboratorio | L | Fase 1, días 3–5 |
| RF-03 | Inventario de servicios locales y estado inicial | Levantar lista de servidores, puertos y estado antes de intervenir | P | Fase 1 |
| RNF-01 | Horario nocturno, autorización y duración | Entrevista a Soporte y a la Dirección | A | Fase 1 |
| RNF-02 | N por laboratorio | Del inventario de equipos y puertos | P | Fase 1 |
| Todos | Cotizaciones con fuente y fecha | 2 cotizaciones con RUC y fecha, separando configuración lógica de instalación física | P | Fase 0, semana 1 |

## Lo que este replanteo no hace

- No convierte en hecho lo que sigue en estado D o H (`2.problema.tex:7`).
- No fija umbrales: los remite a la línea base de la Fase 1.
- No reemplaza la medición ni justifica compras por sí mismo.
