# mkdocs
mkdocs
# 教你上传本地代码到github
http://blog.csdn.net/hanhailong726188/article/details/46738929
# *如何用命令将本地项目上传到git
https://www.cnblogs.com/eedc/p/6168430.html
# MkDocs项目文档生成器(一)
# http://www.iconmoon.com/index.html
# https://craigsworks.com/
# https://www.npmjs.com/package/github-calendar
# https://github.com/makeusabrew
# 安装说明
* chocolatey  #chocolateygui
* Python
* pip
* mkdocs
# chocolatey 使用说明
1. search：会搜索出所有包含关键字的软件包，比如关键字为python，就会输入与之相关的各种软件包
    choco search 关键字
2. install：安装软件
    choco install 软件包名称
3. update：更新软件
    choco upgrade 软件包名称
4. uninstall：卸载软件
    choco uninstall 软件包名称
# pip 升级
  `python -m pip install --upgrade pip`
  `pip install mkdcos`
  
# git使用
## Git global setup
```
git config --global user.name "minyi"
git config --global user.email "minyi@cargocn.com"
```
## Create a new repository
```
  git clone https://minyi@git.cargocn.cn/document/cargocn-cloud-doc.git
  cd cargocn-cloud-doc
  touch README.md
  git add README.md
  git commit -m "add README"
  git push -u origin master
```

## Existing folder
```
  cd existing_folder
  git init
  git remote add origin https://minyi@git.cargocn.cn/document/cargocn-cloud-doc.git
  git add .
  git commit
  git push -u origin master
```

## Existing Git repository
```
  cd existing_repo
  git remote add origin https://minyi@git.cargocn.cn/document/cargocn-cloud-doc.git
  git push -u origin --all
  git push -u origin --tags
```