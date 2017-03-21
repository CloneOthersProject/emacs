# emacs 最佳实践
 很喜欢在cli中使用Emacs, 下面是使用过程中的一些实践记录下。

## 使用magit-git的工作方式
 magit可以和emacs非常好的结和，可以在编码过程中非常方便地add-commit-push, 也是一个重量级插件,需要一定的适应成本。
 本配置文件中配置了几个快捷键
 
*  C-c g s  :相当于在当前git项目里 git status。实际上执行后会打开一个新的buffer进入magit-mode , 在此mode中可以进行各种action，详情看magit-popup文档. 一般我都会在此进行add-commit,reset操作
*  C-c g p u: 当前分支: git push
*  C-c g p l: 当前分支: git pull

## helm-dash
  遇到问题时需要查询标准文档，我们需要一个能够快速离线查询文档的工具。helm-dash就是看文档用的
  
  文档流地址到这个项目中去找: https://github.com/Kapeli/feeds
  
  下载好后，使用`M-x helm-dash-install-docset-from-file`安装docset到~/.docsets中

  在本配置文件中配置了下面两个快捷键

* C-c C-v a 将磁盘中的docsets设为活动的，意思是搜索的时候讲会去搜索这个docset
* C-c C-v q 从活动的docsets中查询一个api
  
## 项目内导航
 项目内导航是以git项目作为一个项目基础，使用`projectile`这个插件可以自动识别这个项目。自动以git项目为搜索基准和自动匹配.gitignore的rule,使用起来很方便，例如搜索文件，全文搜搜(依赖ag命令,需要`brew install ag` or `sudo apt-get install ag`)等功能.

* C-c p f  项目内搜索文件,模糊识别
* C-c p s s 项目内全文搜索s

