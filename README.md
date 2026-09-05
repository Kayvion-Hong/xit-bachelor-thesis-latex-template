# 厦门工学院本科毕业论文（设计）LaTeX 模板

这是一套面向厦门工学院本科生的毕业论文（设计）LaTeX 模板，包含封面、声明页、中英文摘要、目录、正文、参考文献、总结、谢辞和附录。模板将论文内容与排版设置分开，日常写作主要修改文字、图片和文献，不需要逐页调整字号、标题编号和目录。

仓库提供两个压缩包：`厦门工学院毕业设计论文模板.zip` 是用于正式写作的空白模板，保留了占位文字、中文注释和常用写法；`厦门工学院AI示范论文.zip` 是教学示例，以“基于 STM32 的智能照明系统设计”为题，演示一篇论文如何组织章节、插入图表和引用文献。第一次使用时，可以先查看示例版的 `preview.pdf`，再对照源文件了解写法，正式论文则从空白模板开始。

示例版中的课题内容、图片、参数和测试结果用于排版教学，不应当作为真实研究成果提交。模板是非官方项目，排版参考了往届论文，正式提交前仍需核对所在学院、专业和指导教师当年的要求。

## 下载模板，完成第一次编译

LaTeX 的使用方式与直接在页面上排版有所不同：你在 `.tex` 文件中写入正文，用命令标明标题、图片、公式等内容，再通过“编译”生成 PDF。源文件是可以继续修改的论文，PDF 是排版后的成品。第一次使用时，先不必理解所有命令，完成一次“修改文字—编译—查看 PDF”的过程即可。

不准备安装本地环境的同学，可以使用 Overleaf 在线编辑。下面先按这种方式介绍；已经配置好本地 LaTeX 环境的同学，可以直接使用后面的本地编译说明。

在 GitHub 仓库页面点击 `Code`，选择 `Download ZIP`，下载后先解压。若解压出来的文件夹中仍有两个论文 ZIP，说明下载的是整个仓库，而不是可以直接编译的单个论文项目。此时应当选择里面的 `厦门工学院毕业设计论文模板.zip`，不要把同时装着两套模板的外层压缩包直接上传到 Overleaf。

登录 Overleaf，在项目列表中选择 `New Project`（新建项目），再选择 `Upload Project`（上传项目），上传空白模板 ZIP。Overleaf 会解压其中的文件并创建项目。上传完成后，左侧文件区应当能看到 `main.tex`、`xitthesis.cls`、`ref.bib` 和 `chap`、`figures` 等文件夹，而不是只有两个尚未解压的 ZIP。具体操作可参照 [Overleaf 的项目上传说明][overleaf-upload]。

接下来打开项目设置。新版界面可通过齿轮按钮或 `File > Settings` 进入，在编译设置中将 `Compiler` 设为 **XeLaTeX**，将 `Main document` 设为 **main.tex**；旧版界面通常从 `Menu` 中进入相应设置。主文件设置的位置也可参照 [Overleaf 的说明][overleaf-main]。本模板明确要求使用 XeLaTeX，不要选择 pdfLaTeX，也不要把某一章的文件设为主文件。

回到编辑区，点击 `Recompile`（重新编译）。完成后，右侧应当显示生成的论文。此时封面中的“请输入姓名”和正文中的“这里填写……”都是模板保留的占位内容，后续需要替换。空白模板没有启用正文中的示例引用，因此参考文献列表暂时为空，并不一定表示编译出了问题。

建议先只修改 `main.tex` 中的姓名，重新编译，确认右侧封面同步变化，再开始替换整篇论文。这样可以先确认上传、主文件和编译器设置没有问题。压缩包自带的 `preview.pdf` 和 `main.pdf` 是已有的预览文件，不会因为你修改源文件而自动变成新版本；检查修改结果时，应当查看本次编译生成的 PDF。

## 认识项目文件，填写封面和摘要

单个论文项目中的主要文件如下。这里的目录从解压后的论文项目开始，不是最外层仓库目录。

```text
main.tex                      论文主文件：基本信息、关键词、全文加载顺序
xitthesis.cls                 模板样式：封面、字体、页边距、标题、页眉页脚
ref.bib                       参考文献数据库
chap/
    abstract.tex              中英文摘要
    chapter1.tex              第 1 章
    chapter2.tex              第 2 章
    chapter3.tex              第 3 章
    chapter4.tex              第 4 章
    chapter5.tex              第 5 章
    conclusion.tex            总结
    acknowledgements.tex      谢辞
    appendixA.tex             第一个附录
    appendixB.tex             第二个附录
figures/
    logo.png                  封面使用的学校标识
fonts/
    README.md                 字体配置说明
LATEX_OVERLEAF_GUIDE.md        进一步的使用教程
FORMAT_CHANGELOG.md           版式调整记录
copy_windows_fonts.ps1        Windows 字体复制脚本
Makefile                      本地编译和清理辅助文件的命令
preview.pdf                   模板预览
main.pdf                      随包提供的编译结果
```

日常写作主要围绕 `main.tex`、`chap/`、`figures/` 和 `ref.bib` 进行。`main.tex` 决定论文使用哪些内容，`chap/` 保存各部分正文，`figures/` 保存图片，`ref.bib` 保存文献信息。`xitthesis.cls` 则负责这些内容如何排版。除非确实需要根据学校要求调整版式，否则先保留样式文件，不要在其中寻找并替换自己的姓名或论文正文。

先打开 `main.tex`，找到“论文基本信息”这一段。下面用一组示例说明填写位置，题目、个人信息和日期都需要换成自己的实际内容。

```tex
\XITSchool{厦门工学院}
\XITThesisName{本科毕业论文（设计）}
\XITTitle{基于 STM32 的智能照明系统设计}
\XITEnglishTitle{Design of an STM32-Based Intelligent Lighting System}
\XITAuthor{张三}
\XITStudentID{2022110001}
\XITMajor{电子信息工程}
\XITGrade{2022 级}
\XITSupervisor{李老师}
\XITDate{2026 年 5 月}
\XITChineseKeywords{智能照明；STM32；传感器；嵌入式系统}
\XITEnglishKeywords{intelligent lighting; STM32; sensor; embedded system}
```

修改时保留反斜杠、命令名称和成对的大括号，只替换 `{}` 里的文字。例如填写姓名时，将 `\XITAuthor{请输入姓名}` 改为 `\XITAuthor{你的姓名}`，而不是删除整条命令后单独写一个姓名。`\XITGrade` 填写的是年级，不要误填成毕业年份；封面日期按实际提交要求填写。

学校标识由 `\XITLogo{figures/logo.png}` 加载，一般不需要修改。确需替换时，把新的图片放进 `figures/`，再修改这条命令中的路径。不要直接删除 `logo.png` 而保留原路径，否则模板可能无法按预期显示标识。

接着打开 `chap/abstract.tex`，替换中文摘要和英文摘要环境中的占位文字：

```tex
\begin{cnabstract}
这里填写自己的中文摘要，说明研究问题、采用的方法、主要结果和结论。
正式写作时应当使用实际研究内容，而不是保留这段提示。
\end{cnabstract}

\begin{enabstract}
Replace this paragraph with the English abstract of your thesis.
\end{enabstract}
```

`\begin{cnabstract}` 和 `\end{cnabstract}` 是中文摘要的起止标记，英文摘要同理。保留这些标记，在它们之间写摘要即可，不需要再手动添加“摘要”“Abstract”标题，也不要重复输入论文题目。

关键词仍在 `main.tex` 中修改，不是在 `abstract.tex` 中另起一行手写。模板会自动把中英文关键词放在对应摘要后面。中文关键词用中文分号分隔，英文关键词用英文分号分隔，并检查两种语言的内容是否对应。

## 编写正文，调整章节结构

正文按章保存在 `chap/` 中。打开 `chap/chapter1.tex`，将章标题和占位文字替换成自己的内容。下面的例子展示了标题之间的层级关系，可以作为第一章的写法参考，但论文的实际结构应当根据课题和指导教师的要求安排。

```tex
\chapter{绪论}

\section{研究背景与意义}
这里写研究背景。

这里另起一段，说明研究问题和开展这项工作的意义。

\section{相关研究}

\subsection{国内研究}
这里介绍与课题相关的国内研究。

\subsection{国外研究}
这里介绍与课题相关的国外研究。

\section{本文主要工作}
这里说明论文完成了哪些工作，以及后续章节如何安排。
```

`\chapter` 表示章，`\section` 表示章下面的节，`\subsection` 表示更下一层的小节。模板会自动生成“第 1 章”“1.1”“1.2.1”等编号，并将相应标题写入目录。因此，标题中只写标题文字，不要写成 `\section{1.1 研究背景与意义}`，否则容易重复编号。

普通正文直接输入中文即可，不需要每句话都加命令。**段落之间空一行**，模板会处理首行缩进；在源文件中只按一次回车，通常仍然属于同一段。不要用连续空格制造缩进，也不要在每段结尾添加 `\\`。这个命令表示强制换行，不等同于正常分段。

你会在模板中看到很多以 `%` 开头的中文说明。这些是注释，不会出现在 PDF 中。半角 `%` 会让该行后面的内容不参与排版，所以正文需要写百分比时，应当写成 `10\%`。普通正文里的下划线、与号和井号也需要分别写成 `\_`、`\&`、`\#`。例如：

```tex
采样频率设置为 \SI{10}{\hertz}。
误差控制目标为 5\%。
程序中的变量名为 sensor\_value。
```

这几个字符经常出现在从网页或其他文档复制来的内容里。粘贴后若出现报错，应当先检查它们，而不是修改整个模板。命令中的反斜杠、大括号和方括号也要使用英文半角字符。另外，从本 README 复制代码时，只复制代码块内部的内容，不要把代码块外面的三个反引号或 `tex` 字样一并粘贴到论文文件中。

章节是否出现在论文里，由 `main.tex` 中的加载命令决定：

```tex
\include{chap/chapter1}
\include{chap/chapter2}
\include{chap/chapter3}
\include{chap/chapter4}
\include{chap/chapter5}
\include{chap/conclusion}
```

如果论文只需要四章，把第五章对应的入口改为 `% \include{chap/chapter5}` 即可。文件可以暂时保留，但不会进入最终论文。需要第六章时，在 `chap/` 中新建 `chapter6.tex`，写入 `\chapter{补充实验与分析}` 这样的章标题和正文，再在总结之前加入 `\include{chap/chapter6}`。仅仅新建文件而不添加入口，不会让它自动出现在论文中。

编号取决于章节实际加载的顺序，不是文件名中的数字。整章之间自动换页也是模板的正常行为，不需要用空行将标题推到下一页。新建章节文件时，只写章标题和正文，不要再次复制 `\documentclass`、`\begin{document}` 或 `\end{document}`；这些整篇文档的结构已经由 `main.tex` 提供。

## 插入图片、表格、公式和代码

空白模板在 `chapter2.tex` 和 `chapter5.tex` 中保留了相关示例，有些示例被 `%` 注释掉了。使用时既要去掉示例代码前的注释符号，也要替换其中的图片路径、标题和内容。下面的代码应当放在需要出现图表或公式的正文位置，不是放到 `xitthesis.cls` 中。

### 图片与交叉引用

先准备自己的图片，并上传到 `figures/` 文件夹。假设图片名为 `system.png`，实际路径就是 `figures/system.png`。这个文件需要自行提供，不能只复制下面的代码而不上传图片。文件名建议使用简短的英文、数字和下划线，路径中的拼写、大小写及扩展名都与实际文件保持一致。

```tex
系统总体结构如图~\ref{fig:system} 所示。

\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.75\textwidth]{figures/system.png}
    \caption{系统总体结构}
    \label{fig:system}
\end{figure}
```

`\includegraphics` 负责加载图片，`width=0.75\textwidth` 表示将宽度设为正文区域宽度的 75%。图片太小可以适当增大这个数值，太大则减小。一般只指定宽度，让高度随比例变化，避免同时固定宽高后把图片拉伸变形。`\centering` 让图片居中，`\caption` 设置图题，图的编号由模板生成。

`\label{fig:system}` 是这张图的内部标签，正文用 `\ref{fig:system}` 读取编号。标签应当放在 `\caption` 后面，并且每张图使用不同的标签。这里的 `~` 是不换行空格，用来避免“图”和编号被拆到两行。后续即使调整图片顺序，也只需要重新编译，不必逐处修改正文中的图号。

`[htbp]` 表示允许 LaTeX 尝试在当前位置、页顶、页底或单独的浮动页排放图片，并不是要求图片固定在代码所在的位置。因此图片移动到下一页不一定是错误。先确认图片大小合适、正文引用清楚，再检查最终版面，不要为了固定位置插入大量空行。流程图、结构图等尽量使用清晰的原始导出文件，不要把模糊截图放大后作为最终插图。

### 三线表

表格直接在正文中编写，不需要先制作截图。下面是一张三列表格，内容仅用于说明写法，应替换为自己的真实记录。

```tex
测试项目见表~\ref{tab:test-items}。

\begin{table}[htbp]
    \centering
    \caption{测试项目与记录内容}
    \label{tab:test-items}
    \begin{tabular}{ccc}
        \toprule
        测试项目 & 记录内容 & 说明 \\
        \midrule
        光照检测 & 传感器读数 & 填写实际记录 \\
        控制响应 & 响应时间 & 填写实际记录 \\
        通信测试 & 接收情况 & 填写实际记录 \\
        \bottomrule
    \end{tabular}
\end{table}
```

`{ccc}` 表示有三列，并且每列居中；`l` 和 `r` 则分别表示左对齐、右对齐。每一行用 `&` 分隔单元格，用 `\\` 结束，所以三列表格中通常每行有两个 `&`。增加一列时，需要同时修改列定义和每行内容，不能只往某一行多写一个单元格。

`\toprule`、`\midrule` 和 `\bottomrule` 分别生成表格顶部、表头下方和底部的横线。模板已经加载了需要的 `booktabs` 宏包，不需要再次加载。表题放在表格上方，表格标签同样放在 `\caption` 后面。遇到长文字导致表格过宽时，优先精简内容，或将对应列改为 `p{6cm}` 这样的固定宽度列，让单元格可以换行，并根据整张表的宽度调整数值，不要直接把整张表缩到难以阅读。

### 公式与单位

写在句子中的短公式，可以用 `\(` 和 `\)` 包起来；需要单独成行并编号的公式，则使用 `equation` 环境。

```tex
电功率可以表示为 \(P = UI\)。

\begin{equation}
    P = UI
    \label{eq:power}
\end{equation}

式~\eqref{eq:power} 中，\(P\) 为功率，\(U\) 为电压，\(I\) 为电流。
```

`\eqref` 会读取公式编号并带上括号，因此不要再在它外面手工添加一组括号。公式中的上标用 `^`，下标用 `_`，分式用 `\frac{分子}{分母}`；上标或下标包含多个字符时，要用大括号括起来，例如 `x_{max}`。公式环境中不要通过空行分段，也不需要再套一层 `\(...\)`。

模板已加载 `siunitx`，数字和单位可以按下面的方式书写。这些数值只用于演示格式，不代表实际系统参数。

```tex
工作电压为 \SI{3.3}{\volt}。
测量长度为 \SI{10}{\milli\metre}。
环境温度为 \SI{25}{\degreeCelsius}。
```

### 程序代码

模板使用 `listings` 排版代码。将程序放在 `lstlisting` 环境中即可保留代码结构，不需要给每行添加 LaTeX 换行命令。

```tex
\begin{lstlisting}[language=Python,caption={平均值计算示例},label={code:average}]
def average(values: list[float]) -> float:
    if not values:
        raise ValueError("values must not be empty")
    return sum(values) / len(values)
\end{lstlisting}

代码~\ref{code:average} 展示了平均值的计算方法。
```

`language=Python` 指定语言，C 语言代码可以改为 `language=C`；`caption` 是代码标题，`label` 用于正文引用。这个环境只负责排版，不会替你运行程序或检查结果。正文通常保留与论证有关的关键片段，较长的完整实现可以放到附录，避免大段代码打断正文阅读。

## 添加和引用参考文献

参考文献涉及两个位置：`ref.bib` 保存每一篇资料的作者、题目、年份等信息，正文中的 `\cite{...}` 说明具体引用了哪篇资料。只把文献信息写进 `ref.bib`，并不等于已经在论文里引用了它。

先打开 `ref.bib`，在已有内容后添加文献条目。下面是一条期刊论文的格式示例，所有字段都需要根据真实文献填写，示例本身不是可用于论文的参考资料。

```bibtex
@article{example-article,
  author  = {作者甲 and 作者乙},
  title   = {这里填写真实论文题目},
  journal = {这里填写期刊名称},
  year    = {2026},
  volume  = {10},
  number  = {2},
  pages   = {1--8}
}
```

`@article` 表示期刊论文，`example-article` 是文献键，也就是这条记录的唯一名称。文献键不需要与论文题目相同，但不能和其他条目重复，建议使用英文字母、数字和连字符。`author` 中的多个作者用 `and` 分隔，不要直接用中文顿号替代。每个字段按 `字段名 = {内容}` 填写，相邻字段之间保留英文逗号。

写正文时，在需要引用的位置加入同一个文献键：

```tex
关于该方法的具体讨论，见文献\cite{example-article}。
```

此处的文献键必须与 `ref.bib` 中完全一致。不要手动写 `[1]`，也不要把已经排好版的一整段参考文献文字直接粘进 `ref.bib`。多条文献可以写成 `\cite{文献键一,文献键二}`，前提是两条记录都已存在。数据库或文献管理工具导出的 BibTeX 条目也可以作为录入起点，但作者、题名、卷期、页码和年份仍需要逐项核对。

书籍、会议论文、学位论文和网页资料需要使用相应的条目类型，不能全部套用期刊论文的字段。空白模板在 `ref.bib` 的注释中列出了常见类型。它原有的 `sample-reference` 也是占位示例，正式使用时应当替换，并删除正文中遗留的示例引用。

本模板已经在 `main.tex` 中配置了 `biblatex`，使用 `backend=biber` 和 `style=gb7714-2015`，由 Biber 处理文献数据，并按所选样式排版。这是当前模板的配置，不代表无需核对学校当年的文献格式要求。不要为了引用一篇新文献，再从其他教程复制一套 BibTeX、`natbib` 或手工参考文献环境进来，混用不同方案容易造成冲突。有关这套工作方式，可参照 [Overleaf 的 biblatex 使用说明][overleaf-biblatex]。

参考文献由 `\XITPrintBibliography` 输出，当前位于“总结”和“谢辞”之间，并加入目录。一般只需要维护 `ref.bib` 和正文引用，不需要手工编辑最后生成的参考文献页面。`main.tex` 中还保留了被注释的 `% \nocite{*}`，取消注释会列出数据库里的全部条目；它适合检查条目排版，不应当用来代替正文中实际需要的引用。

在 Overleaf 中使用这套配置时，通常由平台的编译流程处理文献。若正文出现文献键而不是编号，或文末列表为空，应先核对文献键、条目格式和编译日志，而不是一直点击重新编译。本地编译则需要明确执行后文给出的 Biber 命令。

## 完成总结、谢辞和附录

正文写完后，打开 `chap/conclusion.tex`，保留文件中的 `\XITConclusion`，在它下面填写总结。这个命令已经负责生成标题和目录条目，不需要再添加 `\chapter{总结}`。总结应当回到论文实际完成的工作和得到的结果，也可以说明尚未解决的问题，不要直接保留模板提示。

谢辞在 `chap/acknowledgements.tex` 中填写，保留开头的 `\XITAcknowledgement`，只替换正文。模板当前使用的标题是“谢辞”；所在学院有不同规定时，再统一调整，而不是在正文中额外手写一个“致谢”标题。

附录可以放较长的源代码、调查问卷、原始记录或补充推导。打开 `chap/appendixA.tex`，按下面的形式填写：

```tex
\XITAppendix{系统关键源代码}

这里填写附录内容，也可以插入代码、图片或表格。
```

模板会自动生成“附录一 系统关键源代码”，并加入目录，不需要把“附录一”再写进大括号。第二个附录在 `chap/appendixB.tex` 中使用相同命令，序号会继续递增。这里使用的是模板自己的附录命令，不需要额外添加其他教程中的 `\appendix`。

只需要一个附录时，注释掉 `main.tex` 中第二个附录的入口；没有附录时，两行都注释掉：

```tex
% \include{chap/appendixA}
% \include{chap/appendixB}
```

只删除附录文件里的文字而保留标题和入口，仍可能生成一个空附录。修改全文结构时，应当同时检查正文文件和 `main.tex` 中的加载关系。

## 字体与版式说明

模板的字体配置优先使用项目 `fonts/` 目录中的宋体、黑体等字体文件，也提供 Windows 系统字体路径和替代字体配置。未提供对应微软字体时，回退配置使用 FandolSong、FandolHei 和 Liberation Serif 等字体。回退配置可以用于继续编辑和检查论文结构，但不代表字形与宋体、黑体、Times New Roman 完全一致。

字体不同可能影响一行能放多少字、段落如何换行，进而影响分页。因此，最终字体应当在定稿检查之前确定，不要在已经逐页检查完论文之后才更换整套字体。具体加载规则位于 `xitthesis.cls`，项目内的 `fonts/README.md` 也有说明。

仓库没有附带微软字体文件。需要使用时，应当自行确认拥有相应的使用权限；只有在授权允许的范围内，才将字体用于本地环境或上传到在线平台。私人项目也不等于自动获得上传或再分发字体的许可，相关原则可参照 [Overleaf 的字体使用说明][overleaf-fonts]。

项目提供了 `copy_windows_fonts.ps1`。Windows 用户可以先阅读脚本，然后在项目目录的 PowerShell 中执行 `.\copy_windows_fonts.ps1`。脚本会尝试从本机 Windows 字体目录复制已有字体到项目的 `fonts/` 中，并输出复制结果。脚本不会下载字体，也不会补齐本机原本没有的文件。

主要涉及 `simsun.ttc`、`simhei.ttf`，以及 Times New Roman 的 `times.ttf`、`timesbd.ttf`、`timesi.ttf`、`timesbi.ttf`。脚本还会尝试复制仿宋和楷体。若系统阻止执行脚本，可以在确认权限后手工复制所需文件，不必为了使用模板关闭系统范围的脚本限制。字体文件名和目录应与模板配置保持一致，缺少配套字形文件时也可能出现字体报错。

这些字体不要随论文源码提交到公开 GitHub 仓库。模板代码、个人论文内容和字体文件应当分开管理，分享论文项目之前，也应检查其中是否包含学号、签名或其他不适合公开的内容。

页边距、标题字号、页眉页脚和图表编号主要由 `xitthesis.cls` 统一控制，调整记录见 `FORMAT_CHANGELOG.md`。需要适配学校新要求时，先备份原项目，再修改对应设置，不要通过给每个标题单独加字号命令来弥补样式差异。

## 在自己的电脑上编译

只使用 Overleaf 的同学可以跳过这一节。本地编译需要先安装 LaTeX 发行版，而不只是安装一个文本编辑器。可以使用 TeX Live，macOS 用户也可以使用 MacTeX。环境中需要能调用 `xelatex` 和 `biber`，并具备模板所用的宏包与字体。

将完整项目解压到电脑上，在包含 `main.tex` 的目录中打开终端。Windows 可以在资源管理器中打开这个文件夹后启动终端；使用命令切换目录时，路径带空格需要加英文双引号。确认当前位置正确后，依次执行：

```bash
xelatex main.tex
biber main
xelatex main.tex
xelatex main.tex
```

第一遍 XeLaTeX 处理正文并生成辅助信息，Biber 根据引用读取 `ref.bib`，后两遍 XeLaTeX 再将文献、目录和交叉引用信息写回 PDF。`biber main` 处理的是当前论文的编译任务，不是让你输入 `biber ref.bib`。全部完成后，生成的文件为项目目录中的 `main.pdf`。

如果某一步出现阻断编译的错误，应先解决该错误，再继续后面的命令。终端提示找不到 `xelatex` 或 `biber` 时，检查发行版安装和命令路径；提示缺少 `.sty` 文件时，检查宏包是否安装。若提示缺少 `Liberation Serif`、`Noto Sans Mono` 等字体，则需要处理具体字体依赖，不能仅靠更换文本编辑器解决。

项目的 `Makefile` 已经写好了上述编译顺序。在安装了 `make` 的兼容环境中，可以执行 `make` 完成编译，执行 `make clean` 清理辅助文件。清理规则使用了 `rm` 命令，Windows 原生命令行不一定具备相同环境；不熟悉这些工具时，直接执行上面的四条编译命令即可。

本地编辑时请将 `.tex` 和 `.bib` 保存为 UTF-8 编码。编辑器名称不决定编译方式，即使使用同一个编辑器，也要确认实际运行的是 XeLaTeX 和 Biber，而不是其他默认方案。

## 编译出错时，先检查什么

修改较多内容后再集中编译，很难判断是哪一处造成了问题。更稳妥的习惯是每完成一小段文字、一个表格或一组引用就编译一次。出现错误时，先查看日志中最早出现的实质错误，再检查提示文件附近刚修改的内容；后面的大量错误可能只是同一个问题引起的连锁反应。

看到 `This class requires XeLaTeX`，说明编译器选错了。看到 `File ... not found`，先看清缺少的文件名：若是 `xitthesis.cls` 或章节文件，检查项目是否上传完整、目录是否被移动；若是图片，检查文件是否真正上传以及路径是否对应。出现 `fontspec` 相关错误时，则根据日志中的具体字体名称检查字体配置。中文显示异常还需要核对源文件编码，不能把所有中文问题都归结为编译器。

看到 `Undefined control sequence`，通常需要检查是否拼错了命令，或复制了模板尚未加载的宏包命令。出现 `Missing $ inserted` 时，检查是否把需要放进数学环境的内容写在了普通正文中，尤其是未转义的下划线。出现环境不匹配的提示时，检查 `\begin{...}` 与 `\end{...}` 是否成对，以及大括号是否遗漏。不要一次性删除大段结构命令来“消除报错”。

图片、表格或公式的引用显示 `??` 时，先检查 `\label` 和 `\ref` 中的标签是否一致、是否重复，以及对应文件是否真的被加载。确认这些没有问题后，再重新编译以更新交叉引用。文献引用还需要检查 `ref.bib` 和 Biber，反复运行 XeLaTeX 并不能代替缺失的文献处理步骤。

目录或引用在源文件正确的情况下仍没有刷新，可以在 Overleaf 的重新编译菜单中使用 `Recompile from scratch`，清理生成文件后重新编译。它处理的是缓存和辅助文件问题，不会修复源代码里的拼写错误。操作含义可参照 [Overleaf 的缓存清理说明][overleaf-cache]。

如果编译成功但版面不理想，也应当区分情况。`Overfull \hbox` 常表示某一行超出了可用宽度，常见于长网址、过宽表格或不能换行的内容，应当结合 PDF 查看；图片移动位置则可能只是浮动排版的结果。封面题目过长时，先核对正式题目和学院要求，再处理封面布局，不要为了塞进一行擅自更改已经确定的论文题目，也不要堆空格强行对齐。

修改后 PDF 没有变化，还要检查当前看的是否是随包提供的旧 PDF、本次编译是否成功，以及修改文件在 `main.tex` 中的入口是否被注释。判断依据应是实际生成的内容，而不是编辑区中“文件已经保存”的提示。

## 导出、备份与提交

论文完成后，先重新编译，再逐页检查最终 PDF。重点核对封面信息和日期、中英文题目与关键词、目录页码、图表和公式引用、参考文献条目，以及总结、谢辞和附录的顺序。全文搜索“请输入”“这里填写”“示例”等占位内容，确认没有遗留教学文字、演示数据或无效引用。声明页的签名与日期也应按学校要求处理，模板生成了页面并不等于已经完成签署。

在 Overleaf 中，可以通过 PDF 预览区的下载按钮导出本次编译结果，也可以从 `File > Download` 中选择下载 PDF。还应下载一份项目源码 ZIP，保留 `.tex`、图片、文献和模板文件；具体入口见 [Overleaf 的项目下载说明][overleaf-download]。PDF 用于阅读和提交，源码用于后续修改，两者不能互相替代。

重要节点分别保存源码和 PDF，例如初稿、导师修改稿和最终提交稿，并让同一版本的两类文件能够对应起来。不要只保留最早下载的模板压缩包，也不要把公开仓库当成含个人信息论文的唯一备份位置。

需要更详细的写法时，可以继续阅读项目中的 `LATEX_OVERLEAF_GUIDE.md`。发现模板问题，可在仓库的 Issues 中说明使用的是空白版还是示例版、Overleaf 还是本地环境，并附上能复现问题的最小代码和日志中的首个关键错误。涉及格式要求的，附上对应的学校规范；涉及个人信息的，先做脱敏处理。熟悉 LaTeX 的同学也可以通过 Pull Request 提交修改。

[overleaf-upload]: https://www.overleaf.com/learn/how-to/Uploading_a_project
[overleaf-main]: https://docs.overleaf.com/getting-started/recompiling-your-project/the-main-document
[overleaf-biblatex]: https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex
[overleaf-fonts]: https://www.overleaf.com/learn/latex/XeLaTeX
[overleaf-cache]: https://docs.overleaf.com/troubleshooting-and-support/clearing-the-project-cache
[overleaf-download]: https://docs.overleaf.com/managing-projects-and-files/downloading-a-project
