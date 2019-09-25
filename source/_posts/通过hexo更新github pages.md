---
title: 通过hexo更新github pages
---
### 文件生成及编辑

``` bash
$ hexo new "文章标题"
```

通过该命令行，可以在 “博客所在路径\source_posts\”下生成一个md文件，文件名称为上面命令行所输入的文章标题 

由于生成的是markdown格式的文件，所以建议使用一个markdown编写完成后，复制粘贴到该md文件中。  

### 文件发布

编辑完成后，在命令行输入

``` bash
$ hexo generate
```

文章就会发布到本地，然后通过

``` bash
$ hexo server
```
将文件变化发布到本地环境，此时可以通过访问localhost:4000，查看自己博客相关变化

### 同步到GitHub

``` bash
$ hexo deploy
```