# 📚 TexBook: LaTeX Book Template

Welcome to TexBook, your very own LaTeX book template! This guide will help you set up your book project so you can visualize the look of your book as you're writing it, with a live preview as a PDF. Let's get started!


### 🔍 Explanation of Folders and Files

- `chapters/`: This folder contains separate `.tex` files for each chapter of your book.
- `figures/`: Place your images here.
- `main.tex`: The main file that compiles your book.
- `preamble.tex`: Contains all the LaTeX packages and configurations.


### 🔍 Explanation of Folders and Files

- `chapters/`: This folder contains separate `.tex` files for each chapter of your book.
- `figures/`: Place your images here.
- `main.tex`: The main file that compiles your book.
- `preamble.tex`: Contains all the LaTeX packages and configurations to set up the book styles.

## 📝 Writing Your Book

### 1. `main.tex`

This is the main file where you compile your book. It includes the preamble and each chapter file.

```latex
\documentclass[12pt,oneside]{book}

\input{preamble}

\begin{document}

\frontmatter
\title{Title of the Book}
\author{Author of the Book}
\date{\today}
\maketitle

\mainmatter
\include{chapters/chapter1}
\include{chapters/chapter2}

\end{document}
```

### 2. `preamble.tex`

This file contains your LaTeX package imports and configurations.
```latex
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[spanish]{babel}
\usepackage{graphicx}
\usepackage{amsmath, amssymb}
\usepackage{geometry}
\geometry{a5paper, inner=30mm, outer=25mm, top=25mm, bottom=30mm}

\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhf{}
\fancyhead[LE,RO]{\thepage}
\fancyhead[LO,RE]{\leftmark}
\renewcommand{\headrulewidth}{0.5pt}

\usepackage{hyperref}
\hypersetup{
    colorlinks=true,
    linkcolor=blue,
    filecolor=magenta,      
    urlcolor=cyan,
}

% Configuración adicional para narrativa
\usepackage{setspace}
\setstretch{1.2} % Espaciado entre líneas ligeramente mayor

% Sin numeración de capítulos en la primera página del capítulo
\usepackage{titlesec}
\titleformat{\chapter}[display]
  {\normalfont\Huge\bfseries}{\chaptertitlename\ \thechapter}{20pt}{\Huge}
\titlespacing*{\chapter}{0pt}{50pt}{40pt}
```

### 3. `chapterX.tex`

```latex
\chapter{The Beginning}
In a village of La Mancha, the name of which I have no desire to call to mind, there lived not long since one of those gentlemen that keep a lance in the lance-rack, an old buckler, a lean hack, and a greyhound for coursing.
```
## 📝 Adding chapters

- Create a new chapter file in the `chapters/` folder, e.g., `chapter3.tex`.
- Write your chapter content in the new file.
- Include the new chapter in `main.tex`:
```latex
  \include{chapters/chapter3}
```
