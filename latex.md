## 基础

[入门参考](https://liam.page/2014/09/08/latex-introduction/)、书籍参考：《LaTeX入门 刘海洋》

- TeX 的源代码是后缀为 `.tex` 的纯文本文件。
- 最流行的两个 TeX 发行（TeX Live 和 MiKTeX）。
- TeX 发行自带的编辑器为`TeXworks `。
- 排版工具（pdfTeX, pdfLaTeX, XeTeX, XeLaTeX 等）
- **控制序列**（或称命令/标记）：反斜杠开头。反斜杠进行转义。
- 百分号 `%` 作为**注释标记**。
- 两个控制序列`\begin`、`\end`以及他们中间的内容被称为「**环境**」；`\end{document}` 之后插入任何内容都是无效的。
- `{article}` 代表这个控制序列有一个必要的参数，部分控制序列还有被方括号 `[]` 包括的可选参数。
- `\documentclass{article}` 和 `\begin{document}`之间的区域**导言区**：对整篇文档进行设置的区域
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

portable graphics format，提供了一些画（矢量）图的基本命令集。画图的**一般框架**如下

```latex
\documentclass{standalone}   %绘制某个单独的图片
\usepackage{tikz}
\usetikzlibrary{arrows, patterns}
\begin{document}

%第一种，环境式
\begin{tikzpicture}[<options>]
    <tikz commands>
\end{tikzpicture}

%第二种，命令式
\tikz[<options>]{<tikz commands>}

\end{document}
```

> + Ti*k*Z中的每条命令用 **分号** 作为结束符。
> + **\coordinate**坐标：`\coordinate (A) at (0,0);`、或者`\path (1,1) coordinate (A);`
> + **\path**画路径，线，最基本的命令，\draw相当于\path[draw]。
> + **\draw**命令，画东西，
>   + [可选项]：各种形状的箭头：->、->>、->|等，thick、thin等参数。
>   + 用 `-- `来连接两个点。
>   + 圆：圆心坐标和半径。`\draw (0,0) circle (1);` 
>   + 椭圆：中心点和长短轴。`\draw (0,0) ellipse (1 and 0.5);`
>   + 弧：起始点，开始角度：结束角度：半径。`\draw[color=red] (1,0) arc (0:45:1);`
>   + 矩形：左下角和右上角坐标，`draw[color=red] (-1,-1) rectangle (1,1);`
> + **\shade**命令：`\shade[ball color=red] (1,2) circle (1);` 。
> + `\node`命令：
>

## 绘图样例

### 流程图

```latex
\documentclass{article}

\usepackage[latin1]{inputenc}
\usepackage{tikz}
\usetikzlibrary{shapes,arrows}
\begin{document}
\pagestyle{empty}

% Define block styles
\tikzstyle{decision} = [diamond, draw, fill=blue!20, 
    text width=4.5em, text badly centered, node distance=3cm, inner sep=0pt]
\tikzstyle{block} = [rectangle, draw, fill=blue!20, 
    text width=5em, text centered, rounded corners, minimum height=4em]
\tikzstyle{line} = [draw, -latex']
\tikzstyle{cloud} = [draw, ellipse,fill=red!20, node distance=3cm,
    minimum height=2em]
    
\begin{tikzpicture}[node distance = 2cm, auto]
    % Place nodes
    \node [block] (init) {initialize model};
    \node [cloud, left of=init] (expert) {expert};
    \node [cloud, right of=init] (system) {system};
    \node [block, below of=init] (identify) {identify candidate models};
    \node [block, below of=identify] (evaluate) {evaluate candidate models};
    \node [block, left of=evaluate, node distance=3cm] (update) {update model};
    \node [decision, below of=evaluate] (decide) {is best candidate better?};
    \node [block, below of=decide, node distance=3cm] (stop) {stop};
    % Draw edges
    \path [line] (init) -- (identify);
    \path [line] (identify) -- (evaluate);
    \path [line] (evaluate) -- (decide);
    \path [line] (decide) -| node [near start] {yes} (update);
    \path [line] (update) |- (identify);
    \path [line] (decide) -- node {no}(stop);
    \path [line,dashed] (expert) -- (init);
    \path [line,dashed] (system) -- (init);
    \path [line,dashed] (system) |- (evaluate);
\end{tikzpicture}


\end{document}
```

