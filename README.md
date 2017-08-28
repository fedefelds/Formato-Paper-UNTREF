# Formato-Paper-UNTREF


## Como usar esto?

en el repositorio hay 1 carpeta:

1. *ejemplo-plantilla-castellano*


Las carpeta 1 contiene un ejemplo pre-editado, para ver a *LaTex* en accion y poder entender mejor como funciona. Tambien hay otros archivos que se crean a la hora de compilar el .tex
por ejemplo el archivo de extension pdf, que representa el resultado final de nuestro trabajo.


dicha carpeta incluye :

+ una serie de archivos con extension .tex

+ el archivo bibliografia.bib, cuya tarea es alojar las fuentes bibliograficas.

+ una carpeta llamada 'imagenes' en donde se deben guardar las imagenes a utilizar como figuras.
las mismas deben estar en formato .png

+ un archivo .log




## FAQs
Como hago para...
+ que son los archivos .tex?
+ que es el archivo bibliografia.bib?
+ que es la carpeta imagenes?
+ que es el archivo .log?
+ como editar el archivo .bib
+ como creo una seccion?
+ como creo crear una subseccion?
+ como creo una lista?
+ como creo una ecuacion numerada?
+ como creo una ecuacion sin numerar?
+ como creo escribo una ecuacion matematica (inline)?
+ como creo una figura?
+ como cito una referencia?
+ como creo una tabla?
+ como creo la seccion con las referencias


### que son los archivos .tex?
Los archivos .tex son la base de nuestro trabajo. Estos archivos son los que vamos a pasar editando la mayoria del tiempo.
Seria algo parecido a el archivo .doc que usabamos con word. 
En esta plantilla tenemos varios archivos de extension tex. Los mas destacados son main.tex y preamble.tex
El primero es, como indica el nombre, el archivo principal. En main.tex incluimos todos los demas archivos .tex mediante 
el comando \input{}. Esto nos permite poder editar las distintas partes del documento por separado. Esto es muy util a la hora
de hacer trabajos medianos o grandes, ya que ayuda a mantener las cosas mas ordenadas. Cada vez que leamos una linea que diga "\input{algo}', es como si en esa linea esten escritos todos los contenidos de algo.tex . Asi vamos construyendo nuestros documentos de forma ordenada y prolija.

En cuanto a premable.tex, este archivo es el que permite que nuestro documento se vea tal como se ve. 
En el se detallan todos los paquetes de latex a usar y sus parametros. Se recomienda averiguar que 
paquetes son usados y como se usan para lograr un mejor entendimiento de como usar LaTeX.

los demas archivos .tex son fragmentos del documento que representan secciones del mismo. Por ejemplo, conclusion.tex
contiene la conclusion del trabajo y es incluido mediante \input{conclusion}


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
\caption{Variación de $\frac{V_{GS}}{I_D}$}
\label{Vgs}
\end{center}
\end{tablehere}
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
