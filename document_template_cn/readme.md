# 运行报错解决方法总结

## 1 编码报错
中文要保存成GBK编码

## 2 编译报错
### 2.1 安装Ctex2.9.2

Reference
- https://blog.csdn.net/weixin_39059031/article/details/102978653

1）进入https://mirrors.tuna.tsinghua.edu.cn/ctex/legacy/2.9/，下载 `CTeX_2.9.2.167_Full.exe`，然后安装

2）安装完毕之后，使用编译链
![alt text](pic\compile.png)

### 2.2 安装CJK（这个方法行不通）

Reference：
- https://blog.csdn.net/m15279530607_163/article/details/129781296
- https://www.cnblogs.com/dyllove98/archive/2005/11/04/2462113.html

1）首先，我们要知道Texlive当前用户文件夹`$TEXMFHOME`所在地路径，可以用如下命令在cmd中搜索

```bash
kpsewhich -expand-var '$TEXMFHOME'
```
![alt text](pic\texmf_path.png)

但其实顺着这个路径去找，会发现一开始并没有这个文件夹，所以此时需要我们去自己创建, 后面Tex编译的时候就会顺着之前系统配置好的路径依次寻找相关字体.

2）下载 `CJK`

- https://www.nongnu.org/cjk/

![alt text](pic\cjk_download.png)

3）在上述新建的 `texmf` 文件夹中新建以下两个文件

```bash
texmf/tex/latex/CJK
texmf/fonts/truetype/chinese
```

4）解压CJK安装包，然后将解压文件夹中的 `texinput` 内的文件拷贝到我们刚创建的 `texmf/tex/latex/CJK` 下

需要安装一个程序，找不到这个程序，这个方法行不通了.

