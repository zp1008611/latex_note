
reference：https://zhuanlan.zhihu.com/p/166523064
# 1 texlive卸载
1. 找到`texlive\2019\tlpkg\installer`下的`uninst.bat`文件并点击运行。

2. 删除环境变量
![在这里插入图片描述](https://img-blog.csdnimg.cn/37a3ac7afc4a42b5be6ad7dcd6aaeadb.png)

# 2 texlive安装

1. 打开[https://tug.org/texlive/acquire-iso.html](https://tug.org/texlive/acquire-iso.html)
2. 点击![在这里插入图片描述](https://img-blog.csdnimg.cn/938a45ed49b1420aa7a770115e8ebf6e.png)
3. 下载iso文件![在这里插入图片描述](https://img-blog.csdnimg.cn/e4169d19cc0e4e70950f1c228213e107.png)
# 3 vscode 安装
# 4 latex插件 latex workshop
1. 在vscode 拓展应用`install` latex workshop

2. 设置json文件：vscode `setting`选项，点击右上角的`open settings(JSON)`
![在这里插入图片描述](https://img-blog.csdnimg.cn/d415bd37b83a42b1a1ee2c4046482317.png)
3. 在json文件加入一下代码：

```bash
{
    "latex-workshop.latex.autoBuild.run": "never",
    "latex-workshop.showContextMenu": true,
    "latex-workshop.intellisense.package.enabled": true,
    "latex-workshop.message.error.show": false,
    "latex-workshop.message.warning.show": false,
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOCFILE%"
            ]
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOCFILE%"
            ]
        },
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
                "%DOCFILE%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "XeLaTeX",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "PDFLaTeX",
            "tools": [
                "pdflatex"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
        {
            "name": "LaTeXmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "xelatex -> bibtex -> xelatex*2",
            "tools": [
                "xelatex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        },
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        },
    ],
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
    ],
    "latex-workshop.latex.autoClean.run": "onFailed",
    "latex-workshop.latex.recipe.default": "lastUsed",
    "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click"
}
```
# 验证
1. 在overleaf上下载一个latex项目
2. 解压后，用vscode打开整个项目文件夹
3. 通过以下步骤进行文件编译：`打开tex文件`-->`点击左侧应用选项`-->`点击recipe编译(笔者一般用xelatex)`-->`若出现√则表示编译成功，出现×则表示编译失败`-->`编译成功后删除临时文件`
![在这里插入图片描述](https://img-blog.csdnimg.cn/f00083944cc34df9878e741ac3ab39e8.png)

