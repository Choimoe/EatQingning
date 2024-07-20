<p align="center">
  <a href="https://choimoe.github.io/games/EatQingning/index.html"><img src="https://github.com/Choimoe/EatQingning/blob/main/static/image/ClickBefore7.png?raw=true" width="100" height="100" alt="EatKano"></a>
</p>
<div align="center">


# EatQingning

*_ 青柠娘挑战 _*

</div>


## 简介

本小游戏为 [小游戏：吃掉小鹿乃](https://choimoe.github.io/games/EatQingning/index.html) 的魔改版本，更换了青柠娘的图标，加入了三个新的4K键形模式~

[English](README_EN.md)
|
[摸鱼的qiqi](https://space.bilibili.com/3461573737712484)
|
[原作者仓库](https://github.com/arcxingye/EatKano)
|
[Github Pages](https://choimoe.github.io/games/EatQingning/index.html)



## 使用方法

如果想要游玩直接点击上面的 `Github Pages` 就好啦，下面是修改教程（静态网页）：

1. `fork` 本仓库或 [源仓库](https://github.com/arcxingye/EatKano)。

2. 修改代码，下面是一些可供修改的例子：

   - `./index.html`：主页面，可以在这里修改选项，例如本项目加入了三个模式，需要在这里加入对应的下拉栏选项。

      ```html
      <li><a class="dropdown-item" onclick="changeMode(MODE_STAIR)" data-i18n="stair">STAIR-I18N</a></li>
      <li><a class="dropdown-item" onclick="changeMode(MODE_MINI)" data-i18n="minijack">MINIJACK-I18N</a></li>
      <li><a class="dropdown-item" onclick="changeMode(MODE_LONG)" data-i18n="longjack">LONGJACK-I18N</a></li>
      ```

   - `./static/index.js`：游戏代码，可以在这里修改游戏机制，例如本项目创建方法 `nextKeyGen()` 来控制键型的生成、添加 `_gameHealth` 的判定等。
      ```js
       function nextKeyGen(test) {
           if (test === 1) { _jackked = 0; return _lastKey; }
           if (mode === MODE_STAIR) {
               if (Math.random() < _changeDirProb[_nextKeyDir === 1 ? 0 : 1][_lastKey]) _nextKeyDir = -_nextKeyDir;
               _newKey = (_lastKey + _nextKeyDir + 4) % 4;
               _lastKey = _newKey;
               return _newKey;
           }
           if (mode === MODE_MINI) {
               if (_jackked == 1) { _jackked = 0; return _lastKey; }
               _lastKey = (_lastKey + 1 + Math.floor(Math.random() * 1000) % 3) % 4;
               _jackked = 1;
               return _lastKey;
           }
           if (mode === MODE_LONG) return _lastKey;
           _lastKey = Math.floor(Math.random() * 1000) % 4;
           _jackked = 1;
           return _lastKey;
       }
      ```
      
   - `./static/index.css`：游戏界面样式，可以在这里修改外观，例如本项目修改 `ClickBefore` 对应的 `.t*` 块来实现多图片的加载。

   - `./static/image`：图片目录。

   - `./static/i18n`：多语言模块，可以在这里修改不同语言背景下的 ui 文字。

     ```json
       "stair": "楼梯模式",
       "minijack": "子弹模式",
       "longjack": "纵连模式",
     ```

3. 修改完就可以直接使用了。

   注意在本地运行的话可能因为跨域范文找不到 `./static/i18n/*.json`，可以通过 `python` 内置的 `python -m http.server [port_id]` 来创建本地服务器进行访问。

## 其它事项

点下star吧~ 欢迎pr代码
