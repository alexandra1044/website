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

`\centering`   

`\includegraphics[width=1\linewidth]{path/to/image}` 

`\caption{Image Caption}` 

`\end{figure}` 


## Two Figures in Parallel


# Tables
Tables in LaTeX can be tricky.

# Bibtex
This is your best bet for writing a good bibliography.

# Codeblocks
You can use the lstlistings package to add code snippets to your paper. Add this to your preamble:

`\usepackage{listings}`

Then...

`\begin{lstlisting}`

`    ~your code here~`

`\end{lstlisting}`
