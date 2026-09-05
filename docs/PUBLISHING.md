# 将这份图文 README 放到 GitHub

这份文件包用于更新仓库首页文档，不是一次已经完成的线上提交。发布前建议先保留原 README，便于对照或恢复。

## 放置位置

将文件包中的 `README.md` 放到仓库根目录，同时上传 `docs/` 文件夹，保持它们的相对位置。两套原始模板 ZIP 已从提供的材料中原样保留，未修改其中的内容。若仓库已经存在同名且内容相同的 ZIP，无需重复覆盖；若仓库中已有更新版本，请保留新版本，并相应核对 README 的写法。

目标结构如下，省略了 `docs/images/` 中的部分图片名称：

```text
仓库根目录/
    README.md
    厦门工学院毕业设计论文模板.zip
    厦门工学院AI示范论文.zip
    docs/
        images/
            01-template-preview.png
            02-first-compile.png
            ...
            11-appendix-code.png
        examples/
            README.md
            quickstart-demo.zip
            quickstart-demo.pdf
        IMAGE_SOURCES.md
        PUBLISHING.md
```

README 使用的是仓库内相对图片路径，例如：

```markdown
![封面填写位置](docs/images/03-cover-fields.png)
```

不能只复制 README 而漏掉图片，也不能把 `docs/` 上传成一个尚未解压的 `docs.zip`。只有真实存在于相对路径上的图片文件，才能正常显示。GitHub 的处理方式见[官方 README 相对链接说明](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)。

## 通过网页上传

进入目标仓库，打开 `Add file` 菜单，选择 `Upload files`，上传需要更新的文件及文件夹。仓库有分支保护或团队审核要求时，按仓库现有流程创建分支和 Pull Request；不必为了这次文档更新去改变保护设置。操作入口可参照[GitHub 官方上传文件说明](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)。

提交后打开仓库首页，检查图片是否显示，再点击两套模板和练习项目的下载链接。若图片不显示，先检查 `docs/` 是否与 README 同级、文件名大小写是否一致，以及是否误把整个文件包又套了一层文件夹。

`README-preview.html` 是本地预览页，不影响 GitHub 渲染。它可以留作检查，也可以不提交到仓库；README 本身不依赖这个 HTML 文件。不要把提供者机器上的本地路径、聊天附件链接或临时图床地址替换进 README。

## 本次未做的改动

没有修改原两套论文 ZIP 中的样式、正文和预览，没有代替维护者选择新的开源许可证，也没有把字体文件加入仓库。若现有仓库已经有许可证或贡献指南，请保留原文件，按实际内容与本页说明衔接。

这份文档按“仓库根目录放两套 ZIP”的材料组织方式编写。仓库以后若改为直接存放 `.tex` 源码，需同步调整下载段落和文件链接，不能原样沿用“双 ZIP”上传说明。
