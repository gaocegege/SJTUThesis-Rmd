# 上海交通大学论文 bookdown 模板

## 一、引言

这是根据当前最新 SJTUThesis.cls，草草做的一个模板。其中图片，代码，公式等等大量问题尚未解决。但是能够编译成功了。

## 二、制作说明

本书采用 [bookdown](https://github.com/rstudio/bookdown) 制作，但是 [bookdown](https://github.com/rstudio/bookdown) 不是那么容易使用的，入手麻烦。下面说说我在深度 15.4.1 下的制作过程。

### 1、安装 R 语言

当前 （2017.08.26） 深度Linux 操作系统的 R 语言的版本，还是能够编译的。参考[R官网](https://cran.r-project.org/bin/linux/debian/#debian-sid-unstable)。

```bash
$ sudo apt-get install r-base r-base-dev
```

### 2、安装 RStudio 编译器

当前深度的版本貌似不够 1.0.0 之上，不可以直接命令行安装。参考[RStudio官网](https://www.rstudio.com/products/rstudio/download/)，下载相关软件安装。如果后续深度更新了版本，可以采用如下命令安装。

```bash
$ sudo apt-get install rstudio
```

请确保当前 `rstudio` 的版本高于 1.0.0。

### 3、安装 texlive 软件

同样的问题，深度仓库的软件版本貌似太低，不能成功编译。推荐[texlive官网](http://tug.org/texlive/)下载最新的 texlive 安装。如果后面深度更新了版本，可以试试

```bash
$ sudo apt-get install texlive-full
```

### 4、安装 pandoc 软件

这个系统自带的版本就可以了。

```bash
$ sudo apt-get install pandoc
```

### 5、下载本文件

下载后解压缩。

### 6、编译的动作

打开 RStudio 软件，在弹出的界面，左上角点击 File->Open Project，找到第 5 步下载的解压文件夹，选中 *./deepin-bible.Rproj* 文件，打开即可。

在左下区域，有 Console 窗体，用于输入 R 语言的命令，可以试着逐步输入如下命令。

```R
install.packages('devtools')
install.packages('bookdown', dependencies = TRUE)
```

上面是不管三七二十一，我把用到用不到的依赖全给安装了。如果遇到缺乏啥包，就需要安装这些包了，比如缺乏 `rmini` 包，感谢 [yihui](https://github.com/yihui/r-ninja/issues/24) 的建议，如下安装了。

```R
devtools::install_github('yihui/rmini')
```

上述没有啥问题的话，就可以点击右上角靠下的一栏，有个 `Build` 格，会出现 `Build Book` 等按钮。点击 `Build Book` 就会生成 PDF 书籍了，位于 *./_book/deepin-bible.pdf*。

## 三、格式与规范

暂且定下这么一个规范。每篇文章分为四部分。

- 第一部分介绍理论和现实状况；
- 第二部分介绍图形界面怎么操作；
- 第三部分介绍终端怎么实现；
- 第四部分延伸阅读或者总结。

整本书的框架，暂且模仿《Linux Bible》分为六部分。

- Linux 操作系统和深度桌面系统的介绍
- 简单入门
- 管理员手册
- 服务器用户
- 网站安全
- 附录 关于怎么编辑本书，以及本书相关的一些操作

编写规范。

- 图片命名不含中文，因为生成的适合无法识别中文。

## 四、下一步打算

改进模板，生成更好的书籍。本书可能更多的内容是在手机上完成。采用**讯飞语音输入法**完成文字草稿输入，然后调整代码。更多的内容可能来自深度维基百科，把维基百科的内容整理过来。

本书源码存在两个位置：

+ https://gitee.com/bubifengyun/SJTUThesis-Rmd
+ https://github.com/bubifengyun/SJTUThesis-Rmd

保持同步更新。由于 github 提供了手机客户端，我可以在手机上给该项目添加 issue ，所以大部分内容会以草稿的形式存在于 github 的 issues 中，每周会更新一下页面。

通过添加如下命令

```bash
$ git remote add github https://github.com/bubifengyun/SJTUThesis-Rmd
$ git remote add gitee https://gitee.com/bubifengyun/SJTUThesis-Rmd
```

我可以采用如下命令更新

```bash
$ git push github master
$ git push gitee master
```

接下来需要做的事情：
+ 对第一、二章的内容，酝酿。
+ 考虑改进写作模板。
+ 找个小伙伴，进行教学，书写。

## 五、致谢

- @yihui ,在其 https://github.com/yihui/bookdown-chinese 基础上修改完善的。
- @deepin 操作系统
- 上海交大原LaTeX模板的所有撰写者和改进者

有兴趣的同学，欢迎在 issue 上发表建议，或者直接推送。谢谢。

## 六、版权

本书是采用合作编写的方式，版权见条款。
本书采用的 [bookdown](https://github.com/rstudio/bookdown) 编写的。相关编码的所有权归相应的作者，谢谢。

## 七、下载本书

源码里有PDF文件。