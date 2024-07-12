---
author: "Alexandra Cooper"
title: "LaTeX Hacks"
date: "2024-07-10"
draft: false
description: "Guide to basic use of LaTeX for Computer Science papers"
tags: [
    "LaTeX",
    "Typesetting"
]
---

# Recommended Editors

1. Overleaf - online editor, free and paid plans. Good for collaborative work or if you are working from multiple devices. If you are a student, some universities will have paid plans available for free for students - so check with your course provider. 
2. TexStudio - local editor, free. Clear interface and will install missing packages for you (if you give it permission).

# Figures

## Float Package
Using the float package will cause the image to be rendered in the same place on the PDF as in the code. Add this to the preamble:

`\usepackage{float}`

Then...

`\begin{figure}[H]`   

&nbsp;`\centering`   

&nbsp; &nbsp;`\includegraphics[width=1\linewidth]{path/to/image}` 

&nbsp;`\caption{Image Caption}` 

`\end{figure}` 

&nbsp;

## Two Figures (or More!) in Parallel

`\begin{figure}` 

&nbsp;`\centering` 

&nbsp;&nbsp;`\begin{subfigure}[b]{0.3\textwidth}` 

&nbsp;&nbsp;&nbsp;`\includegraphics[scale=0.2]{image}` 

&nbsp;&nbsp;&nbsp;`\caption{Text A}` 

&nbsp;&nbsp;&nbsp;`\label{fig:desc}` 

&nbsp;&nbsp;`\end{subfigure} %` 

&nbsp;&nbsp;`\begin{subfigure}[b]{0.3\textwidth}` 

&nbsp;&nbsp;&nbsp;`\includegraphics[scale=0.2]{image}` 

&nbsp;&nbsp;&nbsp;`\caption{Text B}` 

&nbsp;&nbsp;&nbsp;`\label{fig:desc}` 

&nbsp;&nbsp;` \end{subfigure} %` 

&nbsp;`\\` 

&nbsp;&nbsp;`\begin{subfigure}[b]{0.3\textwidth}` 

&nbsp;&nbsp;&nbsp;`\includegraphics[scale=0.2]{image}` 

&nbsp;&nbsp;&nbsp;`\caption{Text C}` 

&nbsp;&nbsp;&nbsp;`\label{fig:desc}` 

&nbsp;&nbsp;`\end{subfigure} %` 

&nbsp;&nbsp;`\begin{subfigure}[b]{0.3\textwidth}` 

&nbsp;&nbsp;&nbsp;`\includegraphics[scale=0.2]{image}` 

&nbsp;&nbsp;&nbsp;`\caption{Text D}` 

&nbsp;&nbsp;&nbsp;`\label{fig:desc}` 

&nbsp;&nbsp;`\end{subfigure} %` 

`\end{figure}` 


# Tables
Tables in LaTeX can be tricky. 

You can use the tabular package.

`\begin{center}`

`\begin{tabular}{|l | l | l | l | l |}`

`\hline`

`one & two & three & four & five \\`

`\hline`

`\end{center}`

This will create a centered table with five cells. Duplicate the `hline` for more rows.

# Bibtex
This is your best friend for writing a good bibliography.

This guide is excellent:

https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex


# Codeblocks
You can use the lstlistings package to add code snippets to your paper. Add this to your preamble:

`\usepackage{listings}`

Then...

`\begin{lstlisting}`

`    ~your code here~`

`\end{lstlisting}`
