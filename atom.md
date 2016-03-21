# Atom editor
### Install in ubuntu 
```
$ sudo apt-get install build-essential git libgnome-keyring-dev fakeroot
$ sudo add-apt-repository ppa:webupd8team/atom
$ sudo apt-get update
$ sudo apt-get install atom
```

### `Configure` 安装第三方包

 * `activate-power-mode`：动感插件 `atl + ctrl + o` :打开插件
 * `vim-mode`：vim模式
 * `ex-mode`：实现`:w`功能
 * `monokai`：高亮显示
 * `atom-ternjs`：JavaScript 自动补全
 * `autoprefixer`：给 CSS 添加适当的前缀
 * `color-picker`：选颜色
 * `emmet`：写 HTML 的神器
 * `atom-beautify`：美化代码，空格啊什么什么的
 * `autoclose-html`：HTML自动补全
 

### 自动换行

> Preference -> Settings -> 选中Soft Wrap 和 下面的选项.
 

### 删除`MAC`系统中的`ATOM`
```
 $ sudo rm -rf ~/.atom
 $ sudo rm -rf /usr/local/bin/atom
 $ sudo rm -rf /usr/local/bin/apm
 $ sudo rm -rf /Applications/Atom.app
 $ sudo rm -rf ~/Library/Preferences/com.github.atom.plist
 $ sudo rm -rf ~/Library/Application Support/com.github.atom.ShipIt
 $ sudo rm -rf ~/Library/Application Support/Atom
 $ sudo rm -rf ~/Library/Saved Application State/com.github.atom.savedState
 $ sudo rm -rf ~/Library/Caches/com.github.atom
 $ sudo rm -rf ~/Library/Caches/Atom
```
