## 基础

[入门参考](https://liam.page/2014/09/08/latex-introduction/)

- TeX 的源代码是后缀为 `.tex` 的纯文本文件。
- 最流行的两个 TeX 发行（TeX Live 和 MiKTeX）。
- TeX 发行自带的编辑器为`TeXworks `。
- 排版工具（pdfTeX, pdfLaTeX, XeTeX, XeLaTeX 等）
- 控制序列（或称命令/标记）：反斜杠开头。反斜杠进行转义。
- 百分号 `%` 作为注释标记。
- 两个控制序列`\begin`、`\end`以及他们中间的内容被称为「环境」；`\end{document}` 之后插入任何内容都是无效的。
- `{article}` 代表这个控制序列有一个必要的参数，部分控制序列还有被方括号 `[]` 包括的可选参数。
- `\documentclass{article}` 和 `\begin{document}`之间的区域导言区：对整篇文档进行设置的区域
- 宏包，就是一系列控制序列的合集。`\usepackage{}`调用宏包。

```latex
\documentclass[UTF8]{ctexart}
\title{你好，world!}  %导言区
\date{\today}
\begin{document} 
\maketitle  %环境
你好，world!
\end{document}
```



## PGF/Ti*k*Z

portable graphics format，提供了一些画（矢量）图的基本命令集。画图的一般框架如下

```latex
\documentclass{standalone}
\usepackage{tikz}
\usetikzlibrary{arrows, patterns}
\begin{document}

%第一种使用方式
\begin{tikzpicture}[<options>]
    <tikz commands>
\end{tikzpicture}

%第二种使用方式
\tikz[<options>]{<tikz commands>}

\end{document}
```

+ Ti*k*Z中的每条命令用 **分号** 作为结束符。

```latex
\tikz \draw (0, 0) -- (1, 1) -- (1, 0); %用 -- 来连接各个点，组成折线段。
\tikz \draw (0, 0) circle (2); %以(0,0)为圆心，2为半径画圆。
\tikz \draw (0, 0) node[circle, draw] {};
\begin{tikzpicture} [ 
    place/.style={circle, draw=blue!50, fill=blue!20, thick, minimum size=6mm},
    transition/.style={rectangle, draw=black!75, fill=black!20, thick, minimum size=6mm},
    red place/.style={place, draw=red!50, fill=red!20}
] %设置宏，预先定义格式
    \node[place] at (0,0) {};
    \node at (1,0) [transition] {};
    \node[red place] at (2,0) {};
\end{tikzpicture}
```

