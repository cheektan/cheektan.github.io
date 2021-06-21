---
layout: 'n'
title: LaTeX Learning Chapter-One
date: 2021-06-15 19:34:38
tags: [VSCode,LaTeX]
index_img: /img/posts/latex.png
categories: [学习,LaTeX]
---
# LaTex排版系统学习
>终于还是开始折腾LaTeX了，简单看了一些教程，理清安装部署脉络，前期工作还是很顺利的。虽然学校图书馆有提供LaTeX教学，但还是不如自己从零开始学的痛快。
><!-- more -->
>>总的来看LaTeX的学习不可能一篇post能讲完，先加个tag，后续边学边写吧！

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=1457707554&auto=1&height=66"></iframe>

## TeX Live安装
选择LaTex发行版TeX Live，是因为其对中文友好且网上教程详细，大佬推荐居多。因为VSCode编辑环境很喜欢，因此采用LaTeX和VSCode联动，实现文章和论文的撰写和排版功能。
>~~吐槽~~ 4个多G的iso镜像，在没勾前端的默认安装情况下硬是装了半小时，LaTeX排版系统的强大不言而喻了。_逃~_

[TeX、LaTeX、TeXLive、TeXstudio区别](https://blog.csdn.net/qq_39546004/article/details/104652095)

## VSCode部署
在TeX Live成功安装后，下载VSCode扩展LaTeX Workshop，在设置settings.json中添加配置：
<details>
<summary>点击显示代码行</summary>
```json
{
  // "LaTeX Workshop"
  "latex-workshop.latex.outDir": "%DIR%/build",
  "latex-workshop.latex.tools": [
    {
      // 编译工具和命令
      "name": "xelatex",
      "command": "xelatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "--output-directory=%OUTDIR%",
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
        "--output-directory=%OUTDIR%",
        "%DOCFILE%"
      ],
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": [
        "%OUTDIR%/%DOCFILE%"
      ],
      "env": {
        "TEXMFOUTPUT": "%OUTDIR%",
      }
    }
  ],
  "latex-workshop.latex.recipes": [
    {
      "name": "xelatex",
      "tools": [
        "xelatex"
      ]
    },
    {
      "name": "pdflatex",
      "tools": [
        "pdflatex"
      ]
    },
    {
      "name": "xe->bib->xe->xe",
      "tools": [
        "xelatex",
        "bibtex",
        "xelatex",
        "xelatex"
      ]
    },
    {
      "name": "pdf->bib->pdf->pdf",
      "tools": [
        "pdflatex",
        "bibtex",
        "pdflatex",
        "pdflatex"
      ]
    }
  ],
}
```
</details>

settings.json中的配置不同，编译出来的文件存储方式有差别，以上设置使得编译生成文件的另存新文件夹，资源管理器界面十分整洁；至于其他的优缺点暂时还未遇到。

{% note info %}
后续需从基础学起，虽可以套用模板，但今天试用发现模板在不同设备上还是存在一些问题，只有从底层基础学起才能真正的用好LaTeX。
{% endnote %}
## 论文模板练习
- Github[厦门大学研究生学位论文 LaTeX 模板](https://github.com/zoam/xmu-thesis-grd)
- 厦门大学经济学院官网[厦门大学研究生学位论文模板](https://soe.xmu.edu.cn/research/xzzq/2017-02-03-13127.html)