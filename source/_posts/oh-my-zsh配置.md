---
title: oh-my-zsh配置
date: 2017-07-16 12:38:08
tags:
- Linux
- Bash
---
## oh-my-zsh是做什么的
开源的zsh配置工具，它的主题和插件系统可以为zsh扩展外观和很多有用的功能，官方是这样介绍的：
> Oh-My-Zsh is an open source, community-driven framework for managing your ZSH configuration. It comes bundled with a ton of helpful functions, helpers, plugins, themes, and a few things that make you shout...

Ubuntu默认的终端样式，用了很久，其实也不差

![默认bash](https://raw.githubusercontent.com/huberyhe/image-bed/bed/markdown/__4d0a62f32693fce8073b7c93e96f2b38.png)
但是用上oh-my-zsh后，更加美观且实用

![使用oh-my-zsh](https://raw.githubusercontent.com/huberyhe/image-bed/bed/markdown/__bf450d643afe100fd78284730e7a9a70.png)

## 安装zsh
1.安装zsh：`sudo apt install zsh`
2.确认安装：`zsh --version`
3.设置为默认shell：`sudo chsh www -s $(which zsh)`
4.注销重新登陆
## 安装和配置oh-my-zsh
默认的zsh很简陋，就不截图了
1.安装：`sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
2.设置主题为`agnoster`: vim ~/.zshrc
```
ZSH_THEME="agnoster"
```
3.默认用户下隐藏`user@hostname`: vim ~/.zshrc
```
export DEFAULT_USER="www"
```
## 安装字体支持
此时终端是这样的，因为字体不支持，显示很奇怪

![缺少字体](https://raw.githubusercontent.com/huberyhe/image-bed/bed/markdown/__0dd472584cdf1188281f743d2ff14949.png)
`angoster`这个主题需要`Powerline-patched font`这个字体才能正常
1.安装

```
# clone
git clone https://github.com/powerline/fonts.git
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```
2.设置终端字体
打开`Edit->Profiles->Default->Edit->Font`， 选择`Ubuntu Mono derivative Powerline`

至此完成了最简单的配置，感受飞起的命令行吧！

## 加速，解决卡慢问题

由于获取仓库信息比较耗时，解决方法：

1、设置不读取文件变化信息

```bash
git config --add oh-my-zsh.hide-dirty 1
```

2、设置不读取任何git信息

```bash
git config --add oh-my-zsh.hide-status 1
```



>参考：
>[oh-my-zsh](http://ohmyz.sh/)
>[Themes](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)
>[agnoster.zsh-theme](https://github.com/agnoster/agnoster-zsh-theme)
>[Powerline fonts](https://github.com/powerline/fonts)
>[Ubuntu 下安装oh-my-zsh](http://www.jianshu.com/p/9a5c4cb0452d)
