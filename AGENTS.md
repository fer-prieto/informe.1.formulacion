# Informe: Mejora en la conectividad de red, EPIIS UNSAAC

Repositorio del informe de **Formulación de Proyectos de TI (IF483BIN)** para la
Escuela Profesional de Ingeniería Informática y de Sistemas (EPIIS), UNSAAC.
El documento se escribe en LaTeX sobre el *Template Informe* de Pablo Pizarro R.
(MIT), recortado a lo que el informe realmente usa.

- Documento maestro: `main.tex`
- Contenido: `src/main/sections/*.tex`
- Núcleo del template: `src/` (no se edita salvo `src/config.tex`)

## Compilación

```bash
make                # compila main.tex -> main.pdf (3 pasadas pdflatex + bibtex)
make compile FILE=x.tex   # compila otro archivo con el mismo pipeline
make clean          # borra aux_outputs/
make cleanall       # borra aux_outputs/ y los .pdf
```

Los auxiliares van a `aux_outputs/`; el PDF final se copia a la raíz. Requiere
`pdflatex` y `bibtex` (TeX Live). `main.pdf` y `aux_outputs/` están ignorados por git.

## Estructura

```text
main.tex                      Metadatos (título, autores, curso, logos) y orden del documento
Makefile                      Pipeline de compilación
library.bib                   Fuentes bibliográficas del informe
natnumurl.bst                 Estilo bibtex numerado con URL (el que usa el documento)
data-adicional/               Borradores de la V2 (ver su propio AGENTS.md)
img/                          Imágenes (defaultimagefolder del template)
  figura1-conexion-inalambrica.png
  figura2-conexion-cableada.png
  logos/info_negro.pdf        Logo de la carrera
  logos/unsaac_negro.pdf      Logo de la universidad
src/
  main/template.tex           Cadena de carga del template: no editar
  main/main.tex               Orden de las secciones y \bibliography
  main/sections/1..8.*.tex    Contenido real del informe (aquí se escribe)
  config.tex                  Configuración del documento (secciones comentadas abajo)
  defs.tex                    Colores y viñetas internas del template
  env/imports.tex             Paquetes LaTeX usados
  env/environments.tex        Entornos públicos (images, appendixd, sourcecode, etc.)
  cmd/core.tex                Utilidades internas (mensajes, chequeos, márgenes)
  cmd/math.tex                Atajos matemáticos y entornos de teoremas
  cmd/equation.tex            Inserción de ecuaciones numeradas con leyenda
  cmd/image.tex               Inserción de imágenes (todas las variantes)
  cmd/title.tex               Títulos, capítulos, header-footer
  cmd/other.tex               Utilidades (páginas vacías, citas, colores de tabla, etc.)
  cmd/column.tex              Columnas y multicol
  style/code.tex              Estilos de código fuente y código inline
  style/other.tex             Estilos misceláneos (enumeración griega)
  cfg/init.tex                Inicialización del documento
  cfg/page.tex                Márgenes, header y footer
  cfg/final.tex               Ajustes finales
  page/portrait.tex           Estilos de portada (21 estilos)
  page/portrait_config.tex    Configuración de la portada elegida
  page/index.tex              Índice y listas de objetos
LICENSE                       Licencia MIT del template original
```

## Dónde se escribe

1. `main.tex`: datos del documento (`\documenttitle`, `\documentauthor`,
   `\universitydepartmentimage`, `\authortable`, ...).
2. `src/main/main.tex`: orden de las secciones y `\nocite{}` para forzar
   referencias.
3. `src/main/sections/N.nombre.tex`: contenido. Cada archivo abre con un
   comentario `% SECCIÓN N: ...` y usa `\section`, `\subsection`.
4. `library.bib`: nuevas referencias; se citan con `\cite{clave}`.
5. `img/`: imágenes nuevas; se referencian por nombre sin la carpeta.
6. `data-adicional/`: borradores de la V2 — requisitos replanteados, plan de
   involucramiento, instrumento de entrevista y trazabilidad. No se enlaza desde
   `main.tex`; su propio `AGENTS.md` explica qué es y en qué se basa.

## Configuración (`src/config.tex`)

Un `\def` por opción, agrupados por bloque y con el rango de valores al final de
la línea. No se deben cambiar nombres. Bloques:

- General (`\documentfontsize`, `\fontdocument`, `\pointdecimal`, `\showlinenumbers`)
- Portada y header-footer (`\portraitstyle`, `\hfstyle`, `\hfwidth*`)
- Caption (márgenes, numeración, posición, fuente)
- Índice (`\indexstyle`, `\indexdepth`, `\showindexofcontents`)
- Anexos, citas y referencias (`\stylecitereferences{natbib}`, `\natbibrefstyle{natnumurl}`)
- Objetos (imágenes, ecuaciones, footnotes, listas, código fuente, tablas)
- Títulos (tamaños, espaciados, separadores, formatos de numeración)
- Colores (`\linkcolor`, `\urlcolor`, `\sourcecodebgcolor`, ...)
- Márgenes de página (`\pagemargintop`, `\pagemarginleft`, ...)
- Metadatos del PDF (`\cfgpdf*`)
- Nombres de objetos (`\nameltfigure{Figura}`, `\namereferences{Referencias}`, ...)

## Referencia de funciones

Los argumentos entre corchetes son opcionales. `#1` es siempre el primero.

### Imágenes

Se pasan por nombre; la extensión es opcional y la ruta es relativa a `img/`.

| Comando | Firma |
| --- | --- |
| `\insertimage` | `\insertimage[label]{archivo}{parámetros}{leyenda}` |
| `\insertimageboxed` | `\insertimageboxed[label]{archivo}{parámetros}{grosor línea}{leyenda}` |
| `\insertimagelink` | `\insertimagelink[label]{archivo}{parámetros}{url}{leyenda}` |
| `\insertimageleft` / `\insertimageleftp` | `\insertimageleft[label]{archivo}{ancho en linewidth}{leyenda}` |
| `\insertimageright` / `\insertimagerightp` | `\insertimageright[label]{archivo}{ancho en linewidth}{leyenda}` |
| `\insertimageleftline` / `\insertimagerightline` | igual + `{grosor línea}` antes de la leyenda |
| `\inserttableimage` | `\inserttableimage{archivo}{parámetros}` (dentro de tabular) |
| `\insertanimatedimage` | `\insertanimatedimage[label]{archivo}{parámetros}{frames}{fps}{leyenda}` |

Parámetros típicos: `scale=0.8`, `width=8cm`, `height=5cm`. Variables de margen:
`\setnextimagevmargin{cm}`, `\imagesnewline`, `\imageshspace{cm}`,
`\imagesvspace{cm}`, `\imagescontinuenumbering`.

**Imágenes múltiples:** entorno `images` con `\addimage{archivo}{parámetros}{leyenda}`
(o `\addimageboxed{archivo}{parámetros}{grosor}{leyenda}`):

```latex
\begin{images}[\label{img:grupo}]{Descripción del grupo}
	\addimage{figura1}{width=0.45\linewidth}{Izquierda}
	\addimage{figura2}{width=0.45\linewidth}{Derecha}
\end{images}
```

### Ecuaciones

| Comando | Firma |
| --- | --- |
| `\insertequation` | `\insertequation[label]{ecuación}` |
| `\insertequationcaptioned` | `\insertequationcaptioned[label]{ecuación}{leyenda}` |
| `\insertequationleft` / `\insertequationright` | `[label]{ecuación}` |
| `\insertalign` / `\insertaligned` | `\insertalign[label]{bloque}` |
| `\insertgather` / `\insertgathered` | `\insertgather[label]{bloque}` |
| variantes `...anum` | sin numeración |
| variantes `...captioned` | `[label]{bloque}{leyenda}` |

`equation`/`equationindex` (entorno) insertan la ecuación en el índice de
ecuaciones con su leyenda. `\restartequation` reinicia la numeración.

### Código fuente

```latex
\begin{sourcecode}[\label{cod:x}]{python}{Leyenda}
print("hola")
\end{sourcecode}

\importsourcecode[\label{cod:y}]{c}{ruta/archivo.c}{Leyenda}  % con parámetros: ...sourcecodep
```

- `\inlinesourcecode{estilo}{código}` y `\inlinesourcecodeboxed[color]{estilo}{código}`
- `\coderef{label}` / `\codeeqref{label}` para referenciar
- Estilos disponibles: `abap, ada, assemblerx64, assemblerx86, awk, bash, basic, c,
  caml, cmake, cobol, cpp, csharp, css, csv, cuda, dart, docker, elisp, elixir,
  erlang, fortran, fsharp, glsl, gnuplot, go, haskell, html, ini, java, javascript,
  json, julia, kotlin, latex, lisp, llvm, lua, make, maple, mathematica, matlab,
  mercury, modula2, objectivec, octave, opencl, opensees, pascal, perl, php,
  plaintext, postscript, powershell, prolog, promela, pseudocode, pseudocodecolor,
  python, qsharp, r, racket, reil, ruby, rust, scala, scheme, scilab, simula,
  sparql, sql, swift, tcl, vbscript, verilog, vhdl, xml`
- Un estilo desconocido detiene la compilación con el listado completo.

### Columnas y multicol

```latex
\createtwocolumn[alto]{0.5}{0.45}{0}{Columna izq.}{Columna der.}
\createhalfcolumn[alto]{Izquierda}{Derecha}
\createthreecolumn{0.32}{0.32}{0.32}{0}{0}{Izq.}{Centro}{Der.}
\createthirdcolumn{Izquierda}{Centro}{Derecha}
```

Firmas completas: `\createtwocolumn[alto]{izq}{der}{separación cm}{contenido izq}{contenido der}`
y `\createthreecolumn[alto]{izq}{centro}{der}{sep 1-2}{sep 2-3}{...}`.
`\createtwocolumncfg` / `\createthreecolumncfg` fijan alineación y posición
vertical; `\resettwocolumncfg` / `\resetthreecolumncfg` los restauran.

Entorno `multicol` (paquete `multicol`): `\newcolumn` salta de columna,
`\newpagemulticol` salta de página, `\insertimagemc[label]{archivo}{top|bottom}{leyenda}`
inserta una imagen a todo el ancho dentro del entorno.

### Títulos

- `\section{t}`, `\subsection{t}`, `\subsubsection{t}`, `\paragraph{t}` (tamaños y
  espaciados vienen de `src/config.tex`).
- `\sectionanum{t}`: título sin numerar; `\sectionanumnoi{t}`: sin numerar y sin indexar
  (equivalentes para `subsection`, `subsubsection`, `subsubsubsection`).
- `\newchapter{t}`: capítulo con formato de sección; `\disablechapter` / `\enablechapter`.
- `\changeheadertitle{t}` / `\clearheadertitle`: control del header.
- `\insertindextitle{t}` / `\insertindextitlepage{t}`: títulos del índice.
- `\createhiddensection[margen pt]{t}`: sección oculta que solo va al índice y header.

### Entornos y utilidades

| Elemento | Uso |
| --- | --- |
| `appendixd` | `\begin{appendixd} ... \end{appendixd}` para anexos (`\nameltappendixsection` los rotula) |
| `references` | Entorno de bibliografía manual (no se usa: se usa `\bibliography`) |
| `fontsizeblock[n]` | Bloque con tamaño de fuente distinto |
| `itemizebf` / `enumeratebf` | Listas con ítems en negrita |
| `\insertemptypage` / `\insertblankpage` | Página vacía sin/con numeración |
| `\quotes{t}`, `\quotesbf{t}`, `\quotesit{t}`, `\quotesttt{t}`, `\doublequotes{t}` | Comillas tipográficas |
| `\insertemail{e}` / `\insertphone{p}` | Contacto con enlace |
| `\scite{clave}` | Cita como superíndice |
| `\hreftext{url}` | URL con texto |
| `\newp` | Párrafo sin sangría |
| `\changepagesize[orientación]{ancho}{alto}` | Cambia tamaño de página |
| `\includefullhfpdf[params]{archivo}` / `\includehfpdf` | Inserta un PDF completo / a media página |
| `\settablerowcolors{n}` / `\switchtablerowcolors` / `\settablerowcolorslast{n}` | Filas de tabla coloreadas |
| `\enabletablerowcolor` / `\disabletablerowcolor` | Activa/desactiva el color de filas |
| `\settablecellpadding{h em}{v em}` / `\resettablecellpadding` | Padding de celdas |
| `\disablecaptionmargin` / `\resetcaptionmargin` | Márgenes de leyenda |
| `\itemresize{factor}{objeto}` | Redimensiona ítems |

Regla práctica: si un comando no está aquí, está documentado en el comentario
`%` inmediatamente encima de su definición en `src/cmd/`.

## Bibliografía

`\stylecitereferences{natbib}` + `\natbibrefstyle{natnumurl}` + `natnumurl.bst`
(citas numéricas con URL). `main.tex` es `article`, así que las secciones son
`\section`. `src/main/main.tex` termina con `\bibliography{library}`; las claves
de `library.bib` se citan con `\cite{}` y se fuerza su aparición con `\nocite{}`.

## Convenciones del repositorio

- Contenido en español, UTF-8. Nombres de sección: `N.nombre.tex`.
- Los archivos del template usan tabulaciones y `%` protectores al final de
  línea: al editarlos, mantener el estilo; el contenido propio puede usar espacios.
- Estructura de sección: `\section{...}` + comentario `% SECCIÓN N: ...` y
  `\subsection` con `% SUB-SECCIÓN` cuando aplique.
- No editar `src/main/template.tex` ni la cadena `src/cmd/`, `src/env/`,
  `src/page/`, `src/cfg/` salvo que se necesite cambiar el template.
- Comillas: usar `` `` '' `` o los comandos `\quotes*`; no usar `"`.
- Nunca commitear `main.pdf`, `aux_outputs/` ni el PDF intermedio.
- La redacción del informe es provisional: el texto debe distinguir lo
  declarado de lo verificado. No afirmar resultados no medidos.

## Alcance recortado del template

Este repositorio conserva solo lo necesario para este informe. Se eliminaron las
variantes del template para tesis, artículo, póster, presentación, reporte,
control y auxiliar, los archivos de prueba (`test/`), la distribución (`dist/`),
las plantillas de ejemplo (`templates/`), los logos e imágenes de ejemplo, los
estilos bibtex no usados, los scripts `compile_natnumurl.py` y
`check_configusage.py`, la CI de GitHub y los borradores en Markdown
(`base_base.md`, `original_viabilidad.md`).

Todo sigue en el historial de git (`git log --diff-filter=D -- <ruta>`). El
template original está en
<https://github.com/Template-Latex/Template-Informe> con manual en
<https://template-latex.github.io/informe>.

## Licencia

MIT, ver `LICENSE` (Pablo Pizarro R.).
