# Entrevista y validación técnica — Ing. Ademir Portillo

Instrumento para llevar impreso. Se entrega al entrevistado para que lo lea,
marque y firme. Curso IF483BIN · EPIIS–UNSAAC · Equipo: Auccacusi, León, Prieto.

**Qué resuelve**: hoy la única evidencia del diagnóstico sobre DHCP es una
declaración atribuida al Ing. Portillo sin fecha ni registro (`2.problema.tex:40`,
E3). Este documento es el registro: con fecha, nombre y firma, E3 deja de estar
«pendiente» y pasa a ser fuente citable en el informe.

**Regla**: si una pregunta no se puede responder, se marca *No responde* o
*No sé*. No se completa con suposiciones del equipo.

## Datos de la diligencia

| Campo | Valor |
| --- | --- |
| Fecha | ____ / ____ / 2026  |
| Hora de inicio / fin | ____ : ____ — ____ : ____ |
| Lugar | ______________________________ |
| Entrevistado | Ing. Ademir Portillo |
| Cargo / área | ______________________________ |
| Entrevistadores | Auccacusi · León · Prieto |
| Quién registra | ______________________________ |

**Uso de la información.** Lo registrado aquí se usa únicamente para el informe
del curso. Se entrega copia al entrevistado. Puede marcar
cualquier pregunta como *No responde* o pedir que se retire.

## Bloque A · Validación de las afirmaciones que ya figuran en el informe

Marcar una opción por fila. «Corrección» es para matizar o negar.

| # | Afirmación que hoy figura en el informe | Sí | No | Parcial | No sé | Corrección / matiz |
| --- | --- | --- | --- | --- | --- | --- |
| A1 | En laboratorios de la EPIIS se requiere configurar la IP manualmente | ☐ | ☐ | ☐ | ☐ | |
| A2 | Esa configuración manual se debe a que el DHCP no entrega dirección | ☐ | ☐ | ☐ | ☐ | |
| A3 | Aplica a unos 8 laboratorios del pabellón | ☐ | ☐ | ☐ | ☐ | |
| A4 | La configuración manual es una **política** del laboratorio (control de acceso o asignación fija), no una falla | ☐ | ☐ | ☐ | ☐ | |
| A5 | La lentitud crítica se concentra en los laboratorios 309–312 | ☐ | ☐ | ☐ | ☐ | |
| A6 | En algunas aulas no aparece la señal Wi-Fi | ☐ | ☐ | ☐ | ☐ | |
| A7 | Los cortes de conexión son frecuentes durante las clases | ☐ | ☐ | ☐ | ☐ | |
| A8 | Cualquier cambio en VLAN o DHCP debe coordinarse antes con Soporte EPIIS | ☐ | ☐ | ☐ | ☐ | |

**A3.a ¿En qué laboratorios?** Marcar los que correspondan (lista del informe,
`2.problema.tex:52`):

☐ 111 · ☐ 207 · ☐ 208 · ☐ 301 · ☐ 302 · ☐ 303 · ☐ 304 · ☐ 305 · ☐ 306 ·
☐ 309 · ☐ 310 · ☐ 311 · ☐ 312 · ☐ 419
☐ otros: ______________________________

## Bloque B · Operación actual de la red

1. ¿Quién administra la red del pabellón y desde qué área? ¿Desde cuándo?
   R:
2. ¿Existe un servidor DHCP? ¿En qué equipo corre: servidor dedicado, router o
   switch de capa 3? Marca y modelo.
   R:
3. ¿Cuántos rangos de direcciones hay y cuántas direcciones por rango? ¿Se ha
   agotado alguno? ¿Qué tiempo de concesión (*lease*) se usa?
   R:
4. ¿Hoy existen VLAN por laboratorio, o una sola red plana?
   R:
5. ¿Los puertos de usuario tienen PortFast habilitado? ¿Se usa STP en esos
   puertos?
   R:
6. ¿Cuántos equipos cableados tiene cada laboratorio y cuántos puertos están
   activos? ¿Existe un inventario?
   R:
7. ¿Quién configura la IP manual: el docente, soporte o el propio alumno? ¿Hay
   un instructivo escrito?
   R:
8. ¿Desde cuándo se hace así y por qué motivo se empezó?
   R:
9. En los laboratorios 309–312: ¿cuántos puntos de acceso hay, de qué modelo y
   dónde están ubicados? ¿La lentitud se nota también entre dos equipos del mismo
   laboratorio, sin salir a Internet?
   R:
10. ¿Qué ancho de banda tiene el enlace del pabellón, con qué proveedor, y quién
    lo gestiona?
    R:

## Bloque C · Evidencia que puede entregar o autorizar

| Documento o dato | Disponible | Formato | Fecha | ¿Cómo se comparte? |
| --- | --- | --- | --- | --- |
| Mapa de red o planos del pabellón | ☐ sí ☐ no | | | |
| Configuración de DHCP y VLAN (puede ser sanitizada) | ☐ sí ☐ no | | | |
| Tabla de concesiones de direcciones | ☐ sí ☐ no | | | |
| Inventario de equipos y puertos por laboratorio | ☐ sí ☐ no | | | |
| Tickets, actas o registros de incidentes de red | ☐ sí ☐ no | | | |
| Pruebas de velocidad previas hechas por soporte | ☐ sí ☐ no | | | |
| Contrato u orden de servicio del enlace | ☐ sí ☐ no | | | |
| Horario de uso de laboratorios en el semestre | ☐ sí ☐ no | | | |

Observaciones:

## Bloque D · Restricciones, ventanas y autorizaciones

1. ¿En qué horario el pabellón queda sin clases?
   R:
2. ¿Se puede acceder a los laboratorios después de las 20:00 o en fin de semana?
   ¿Con qué autorización?
   R:
3. ¿Quién autoriza una intervención en la red? ¿Con cuánta antelación se le
   debe pedir?
   R:
4. ¿Qué duración máxima de interrupción es aceptable sin afectar una clase?
   R:
5. ¿El proveedor o el personal de soporte cobra recargo por trabajo nocturno o
   de fin de semana?
   R:

## Bloque E · Compromisos y cierre

| Compromiso | Sí / No / condicionado | Detalle o condición | Fecha |
| --- | --- | --- | --- |
| Autoriza el acceso de lectura a la configuración de DHCP y VLAN | | | |
| Facilita el inventario de equipos y puertos | | | |
| Permite participar en la prueba de asignación de IP en hora punta | | | |
| Revisa el acta antes de que se cite en el informe | | | |

¿A quién más hay que consultar? (nombre, cargo, motivo)

1.
2.

Próxima reunión propuesta: ____ / ____ / 2026 · Tema: ______________________

**Conformidad del entrevistado.** Declaro que lo registrado corresponde a lo que
respondí y que las correcciones anotadas son mías.

Nombre: ___________________________ Firma: ___________________________
Fecha y hora: ____ / ____ / 2026 · ____ : ____

## Registro posterior (lo completa el equipo, no el entrevistado)

| Campo | Valor |
| --- | --- |
| Transcripción | ______________________________ |
| Dónde se archiva | ______________________________ |
| Afirmaciones que cambian de estado en el informe | E3 pasa de «fecha pendiente» a fuente fechada (`2.problema.tex:40`) · estado de CI2 (`2.problema.tex:89`) · alcance de RF-01 (`5.alcance.tex:55`) |
| Pendientes que quedan, con responsable y plazo | ______________________________ |
