# README

### 资源
> 整理一些平时用到的一些库，或者常用的网站和小工具。写一些简单的博文

### gitbook地址
https://wylibra.github.io/gitbook

### 编译书籍
```
node -v
nvm use 8
gitbook serve
```

### 部署书籍
master 分支添加内容之后，使用`gitbook build`编译文件，然后提交代码到远程master分支；

删除远程和本地的 gh-pages 分支；
```
git checkout --orphan gh-pages
删除_book之外的文件
cp -r _book/* .
$ git add .
$ git commit -m "Publish book"
```

