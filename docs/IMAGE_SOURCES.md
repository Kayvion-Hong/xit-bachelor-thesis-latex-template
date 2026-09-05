# README 配图来源

所有图片保存在 `docs/images/`，README 通过相对路径引用。图片是论文 PDF 的裁切、标注和代码对照，不是学校官方宣传物料，也不表示平台或学校对模板作出认证。

## 原始材料

原材料为提供的 `厦门工学院毕业 设计论文模板(1).zip`，其中包含 `厦门工学院毕业设计论文模板.zip` 和 `厦门工学院AI示范论文.zip`。本次没有修改这两份内部压缩包的字节内容。

`01-template-preview.png` 展示空白模板随附 `main.pdf` 的第 1 页，以及 AI 示例随附 `main.pdf` 的第 3、5 页。AI 示例中的内容仅用于排版教学。

`02-first-compile.png` 的文件清单来自空白模板 ZIP，右侧使用空白模板随附 `main.pdf` 的封面局部。图中的 Compiler 和 Main document 是应当检查的设置值，整张图不是 Overleaf 界面截图。真实界面位置以 README 链接的官方说明为准。

## 配图练习项目

`03-cover-fields.png` 至 `11-appendix-code.png` 的 PDF 局部来自 [quickstart-demo.pdf](examples/quickstart-demo.pdf)，完整源码见 [quickstart-demo.zip](examples/quickstart-demo.zip)。使用了空白模板原有的 `xitthesis.cls` 与学校标识。对应页码按 PDF 文件中的物理页序计数，不是纸面显示的页码。

| 配图 | PDF 页序 | 内容 |
| --- | --- | --- |
| 03-cover-fields.png | 1 | 封面题目与个人信息 |
| 04-abstract-keywords.png | 3 | 中文摘要、题目与关键词 |
| 05-headings-paragraphs.png | 6 | 章、节、小节以及段落 |
| 06-contents.png | 5 | 自动生成的目录 |
| 07-figure-reference.png | 7 | 已有图片、图题与正文引用 |
| 08-three-line-table.png | 8 | 三线表 |
| 09-equations-units.png | 9 | 公式编号、引用与单位 |
| 10-bibliography.png | 10、12 | 正文引用和文末参考文献 |
| 11-appendix-code.png | 14 | 附录标题、程序代码与引用 |

代码面板为教学节选，必要时简化正文或调整源文件中的换行，PDF 面板没有重绘论文正文或伪造排版结果。标注框与编号仅用于 README 说明，不属于最终论文页面。

使用的字体来自本次编译环境可用的回退配置。图像中渲染的文字不等于向仓库分发字体文件，文件包不包含 `.ttf`、`.ttc`、`.otf` 或其他字体二进制文件。

练习中的姓名、学号、题目、文献和说明文字均为教学占位内容。表格不包含真实实验数据，代码没有通过 LaTeX 执行。`demo-reference` 是虚构文献条目，不能用于正式研究。

## 操作说明来源

界面操作主要依据 GitHub 与 Overleaf 官方文档，相关链接就近放在 README 中。检查日期为 2026-09-05；界面和菜单可能随版本变化，遇到不同入口时应核对设置名称，不要将配图当作软件界面的逐像素复刻。
