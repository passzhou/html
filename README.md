# $\LaTeX$零基础入门[^1]

[texlive镜像下载地址](https:mirrors.aliyun.com/CTAN/systems/texlive/Images/)

查看$\LaTeX$教程：`texdoc lshort-zh`

## 常用宏包

### `graphics/graphicx`

**查看宏包文档**：`texdoc graphicx`

**指定图片路径**：`\graphicspath`
`\usepackage[option]{graphicx}%导入宏包`
`\includegraphics{图片名}%插入图片`[^2]


```latex
\documentclass{ctexart}
\usepackage{graphicx}

\begin{document}
%\begin{figure}[h]%figure环境可居中
\includegraphics[height = 5cm]{picture}%缩放图片至其高度为5cm
% \end{figure}
\end{document}
```

### `amsmath`

### `geometry`

## cls样式文件

```latex
\NeedsTeXFormat{LaTeX2e}%
\ProvidesClass{luwen}%提供名为luwen的文档类
\RequirePackage{amsmath}%用到的宏包
```




```latex
\documentclass{article}

\usepackage{}

\begin{}

\end{}
```

点乘($\cdot$)：`\cdot`
叉乘($\times$)：`\times`
除以($\div$)：`\div`
分数:`\frac{分子}{分母}`
范数:`\left\| \right\|`
三角函数:`\sin \cos \tan \arcsin`
希腊字母:`\alpha \beta \mu`
大写希腊字母:`\Theta`
大于等于:`\leq`
小于等于:`\geq`
属于:`\in`
子集:`\subset`
上标:`^`
下标:`_`
文本加粗:`\textbf{}`[^3]
文本斜体:`\textit{}`[^4]
罗马:`\textrm {}`
下划线:`\underline`
积分$\int_{0}^{x}dx$：`\int`
[其他](https://www.latexsymbols.cn/)

## 希腊字母

|   符号    |  LaTeX  |   大写    |  LaTeX  |
| :-------: | :-----: | :-------: | :-----: |
| $\theta$  | \theta  | $\Theta$  | \Theta  |
|  $\beta$  | \belta  |  $\Beta$  |  \Beta  |
| $\gamma$  | \gamma  | $\Gamma$  | \Gamma  |
| $\delta$  | \delta  | $\Delta$  | \Delta  |
|  $\zeta$  |  \zeta  |  $\Zeta$  |  \Zeta  |
|  $\eta$   |  \eta   |  $\Eta$   |  \Eta   |
| $\omega$  | \omega  | $\Omega$  | \Omega  |
| $\lambda$ | \lambda | $\Lambda$ | \Lambda |
|   $\mu$   |   \mu   |   $\Mu$   |   \Mu   |
| $\alpha$  | \alpha  | $\Alpha$  | \Alpha  |
|   $\pi$   |   \pi   |   $\Pi$   |   \Pi   |
| $\sigma$  | \sigma  | $\Sigma$  | \Sigma  |
|  $\tau$   |  \tau   |  $\Tau$   |  \Tau   |
|  $\psi$   |  \psi   |  $\Psi$   |  \Psi   |
|  $\phi$   |  \phi   | $\varphi$ | \varphi |

## 页面设置

```latex
\usepackage{geormetry}
```

## 自定义模板

新建`.cls`后缀文件

[参考链接](https://blog.csdn.net/weixin_43145361/article/details/88786014)

## 插入图片[^4]

```latex
\usepackage{graphicx}
includegraphics[width=0.3\textwidth]{pic_name}
```

## 文档结构

```latex
\documentclass[UTF8]{ctexart}
\usepackage{graphicx}
\title{基于RT-Thread的多功能气压计}
\author{fly}
\date{\today}
\begin{document}
\maketitle
\textbf{需要加租显示的字}

\end{document}
```

## 列表

### 无序列表

```latex
\begin{itemize}
\item 列表项1
\item 列表项2
\end{itemize}
```

### 有序列表

```lat
\begin{enumerate}
\item 列表项1
\item 列表项2
\end{enumerate}
```

## 公式

### 行内公式

```latex
$E=mc^2$
```

### 普通公式

```latex
\begin{equation}%equation会自动对公式编号
E=mc^2%单行公式
\end{equation}

或者使用displaymath环境简写
\[
E=mc^2
]\

$$f(x)=x^2+y^2$$%单行公式无编号
```

## 表格[^5]

```latex
\begin{tabular}{|c|c|c|}%|添加竖线
\hline
单元格1 & 单元格2 & 单元格3 \\%\hline添加横线
\hline
单元格4 & 单元格5 & 单元格6 \\
\hline
单元格7 & 单元格8 & 单元格9
\end{tabular}
%指定列宽度为1.5cm
\begin{tarbular}{ccc p{1.5cm}}
```

## 浮动体

## 参考文献

```latex
\usepackage{cite}

\begin{document}
RT-Thread\cite{}
\bibliographystyle{plain}
\bibliography{ckwx}%指定参考文献位置
\end{document}
```

## 图片

```latex
\begin{figure}
\centering%居中
\end{figure}
```

## 表格

```latex
\begin{table}

\end{table}
```

## 多行公式

```latex
\usepackage{amsmath}
\begin{align}%\usepackage{amsmath}
a&=b+c\\
&=d+e
\end{align}
```

## 指定中英文字体

```latex
\documentclass{article}
\usepackage{amsmath} % 数学公式包
\usepackage{xeCJK} % 中文支持包
\usepackage{fontspec} % 字体支持包
\usepackage{unicode-math} % Unicode数学字体支持包

% 设置英文字体和数学字体为Times New Roman
\setmainfont{Times New Roman}
\setmathfont{TeX Gyre Termes Math}

% 设置中文字体
\setCJKmainfont{SimSun} % 将SimSun替换为你想要的中文字体

\begin{document}

这是一个中文文本，使用的是宋体（SimSun）。

This is an English text, using Times New Roman.

\begin{equation}
E = mc^2
\end{equation}

这是一个包含公式的中文文本，公式使用Times New Roman字体： \(E = mc^2\)。

\end{document}

```



## 坐标轴绘图

```latex
\documentclass{article}
\usepackage{circuitikz}%tikz

\begin{document}
\begin{circuitikz}%tikzpicture
  % 坐标轴
  \draw[->] (-3,0) -- (3,0) node[right] {$t$};
  \draw[->] (0,-3) -- (0,3) node[above] {};
  
  % 分段线性信号
  \draw[line width=1.2pt] (-2,0) -- (-2,-1) --(-1,0) -- (-1,1);
  \draw[line width=1.2pt] (-1,1) -- (0,1) --(0,2) -- (1,2) -- (1,1) -- (2,0);
  % 添加刻度和标签
  \foreach \x in {-2,-1,1,2}
    \draw (\x,0.1) -- (\x,0) node[below] {$\x$};
  \foreach \y in {-2,-1,1,2}
    \draw (0.1,\y) -- (0,\y) node[left] {$\y$};
   \draw (0,0.1) -- (0,0) node[below right] {$0$};
\end{circuitikz}%tikzpicture
\end{document}
```

运行结果

![资源 1](C:\Users\fly☆飞\Pictures\markdown\资源 1.svg)

## 信号与系统常见图形绘制

### 时间域信号

```latex
\documentclass{standalone}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
    % Draw axes
    \draw[->] (-1,0) -- (5,0) node[right] {$t$};
    \draw[->] (0,-1) -- (0,3) node[above] {$x(t)$};
    
    % Draw signal
    \draw[thick,blue] (0,0) -- (0,2) -- (4,2) -- (4,0);
    
    % Add labels
    \node[below] at (0,0) {$0$};
    \node[below] at (4,0) {$T$};
    \node[left] at (0,2) {$A$};
\end{tikzpicture}
\end{document}

```


$$
\begin{align}
a &= b + c \notag\\
d &= e + f
\end{align}
$$

$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$

[LaTeX转word](https://blog.csdn.net/qq_42074210/article/details/136629726)

`pandoc main.tex --filter pandoc-crossref --citeproc --csl ieee.csl --bibliography=cite.bib -M reference-section-title=参考文献  -M autoEqnLabels -M tableEqns  -t docx+native_numbering --number-sections -o output.docx`

> –filter pandoc-crossref ：启用 Pandoc 的交叉引用过滤器pandoc-crossref，允许进行交叉引用、自动编号等操作。
> –citeproc：使用 Pandoc 的引用处理器，允许从BibTeX 数据库 (cite.bib) 中引用文献。
> –csl ieee.csl：指定引文样式 (CSL) 文件，这里使用 IEEE 格式 (ieee.csl) 来格式化文献引用。
> –bibliography=cite.bib：指定 BibTeX 数据库文件，其中包含了文献引用的信息。
> -M reference-section-title=参考文献：指定生成的文档中文献部分的标题为“参考文献”。
> -M autoEqnLabels：启用自动为公式添加标签。
> -M tableEqns：在表格中自动为方程添加标签。
> -t docx+native_numbering：指定输出格式为 docx，并启用本地编号（native numbering）。
> –number-sections：对文档的章节进行编号。
> -o output.docx：指定输出文件的名称为 output.docx。

## 命令窗口编译

`xelatex xx.tex`

注意[^!]

[环境变量修改教程](https://tieba.baidu.com/p/7453007153)

[^!]: 若系统用户存在中文，导致安装时报错须修改系统环境变量的TEMP为`%SystemRoot%\TEMP`
[^1]: [在线LaTeX公式编辑网址](https://latex.codecogs.com/eqneditor/editor.php)
[^2]: 图片名不能用中文
[^3]: bf:bold font
[^4]: it:italic
[^5]: pic_name:图片名
[^6]: c表示居中，三个代表列数