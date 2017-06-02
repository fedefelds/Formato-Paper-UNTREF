# Formato-Paper-UNTREF


## Como usar esto?

en el repositorio hay 4 carpetas:

1. *plantilla-castellano*
2. *plantilla-ingles*
3. *ejemplo-plantilla-castellano*
4. *ejemplo-plantilla-ingles*

Las carpetas 1 y 2 contienen plantillas listas para empezar a trabajar.

ambas carpetas tienen :
+ una carpeta en donde se deben guardar las imagenes a utilizar como figuras.
las mismas deben estar en formato .png

+ el archivo bibliografia.tex, usado para manejar las fuentes bibliograficas


+ el archivo plantilla_castellano.tex o plantilla_ingles.tex . Aca es donde se edita la mayor parte del tiempo

Las carpetas 3 y 4 contienen los mismos archivos que las carpetas 1 y 2, pero ya estan pre-editados, para ver a *LaTex* en accion y poder entender mejor como funciona. Tambien hay otros archivos que se crean a la hora de compilar el .tex
por ejemplo el archivo de extension pdf, que representa el resultado final de nuestro trabajo.






## FAQs
Como hago para...

+ editar el archivo .bib
+ crear una seccion
+ crear una subseccion
+ crear una lista
+ mostrar una ecuacion numerada
+ mostrar una ecuacion sin numerar
+ escribir una ecuacion matematica (inline)
+ insertar una figura
+ citar una referencia
+ crear una tabla
+ crear la seccion con las referencias



### editar el archivo .bib
el archivo bibliografia.bib contiene todas las referencias usadas en el informe.
las instrucciones de uso y mantenimiento de ese archivo se encuentran en el mismo archivo.

### crear una seccion
Crear una seccion es muy simple, solo hay que usar

```\section{nombre de la seccion}```

### crear una subseccion
Crear una subseccion es muy simple, solo hay que usar

```\subsection{nombre de la subseccion}```
### crear una lista
Para crear una lista, se usa el entorno itemize:
```
\begin{itemize}
  \item Un Osciloscopio Tektronix 2049b
  \item Un generador de señales Nike
  \item Un Ford fiesta
\end{itemize}
```
para mas informacion, ver: https://www.sharelatex.com/learn/Lists

### mostrar una ecuacion numerada (display math)
Para mostrar una ecuacion numerada, se usa el entorno equation:
```
\begin{equation}
 e^{ \ j  \pi} = -1
 \label{etiqueta de la ecuacion}
\end{equation}

```
el uso de \label nos permite referirnos a esta ecuacion de manera univoca.
Para mas informacion sobre /label, ver la seccion 'como hacer referencia a una funcion,tabla o figura'
### escribir una ecuacion matematica (inline math)

para escribir una ecuacion sin llamar tanto la antencion (inline math), se  escribe:

```
$e^{ \ j  \pi} = -1$

```
Para mas informacion sobre como escribir ecuaciones (indices, subindidices, etc), ver https://www.sharelatex.com/learn/Mathematical_expressions y https://www.sharelatex.com/learn/Subscripts_and_superscripts
### insertar una figura

para insertar una figura, se usa el entorno figurehere:

```
\begin{figurehere}
 \centering
 \includegraphics[width=\linewidth]{nombre}
 \captionof{figure}{titulo de la figura}
 \label{fig:etiqueta de la figura}
\end{figurehere}
```
el uso de \label nos permite referirnos a esta figura de manera univoca.
Para mas informacion sobre /label, ver la seccion 'como hacer referencia a una funcion,tabla o figura'

Nota 1: la imagen debe ser .png

Nota 2: el archivo nombre.png debe estar en la carpeta imagenes incluida en la descarga.

### citar una referencia
para citar una referencia, simplemente usar:

```\cite{keyword}```

donde keyword es la palabra clave con la que se identifica a la fuente  en **bibliografia.bib**

### crear una tabla
para crear una tabla, se usa el entorno tablehere:
```
\begin{tablehere}
\begin{center}
\begin{tabular}{|c|c|c|c|}
\hline
$V_{GS}$ [V] & $I_{D}$ [A] & Temperatura [$C^{o}$] & $\frac{V_{GS}}{I_D}$ [$\Omega$] \\
\hline
col1 & col2 & col3 & col4 \\

col1 & col2 & col3 & col4 \\

col1 & col2 & col3 & col4 \\
\hline
\end{tabular}
```

para mas informacion, ver: https://www.sharelatex.com/learn/Tables
### como hacer referencia a una funcion,tabla o figura
poder hacer referencia o *crossreference* es una de las tantas virtudes de *LaTex*. Nos permite referirnos a una
figura, ecuacion o tabla.
por ejemplo, si en la figura 1 tengo un plot de respuesta en frecuencia de un Shure SM58, asignarle a dicha figura un label:
 ```markdown
\begin{figurehere}
 \centering
 \includegraphics[width=\linewidth]{sm58}
 \captionof{figure}{respuesta en frecuencia del shure SM58}
 \label{freqresponsesm58}
\end{figurehere}
```
ahora puedo referirme a esta figura siempre que sea necesario usando `\ref{freqresponsesm58}`
### crear la seccion con las referencias
para crear la seccion de referencias/bibliografia simplemente usar:

`\printbibliography`

