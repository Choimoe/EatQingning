<p align="center">
  <a href="https://choimoe.github.io/games/EatQingning/index.html"><img src="https://github.com/Choimoe/EatQingning/blob/main/static/image/ClickBefore7.png?raw=true" width="100" height="100" alt="EatKano"></a>
</p>
<div align="center">

# EatQingning

* _ Qingning Challenge _ *

</div>


## Introduction
A web game: EatKano


[摸鱼的qiqi](https://space.bilibili.com/3461573737712484)
|
[origin repo](https://github.com/arcxingye/EatKano)
|
[Github Pages](https://choimoe.github.io/games/EatQingning/index.html)

## Usage

Note: if you just want to play it, go to [online version](https://xingye.me/game/eatkano/index.php). Here is how to create your own version.

### Github Pages

If you want to play, just click on `Github Pages` above. Here is the tutorial for modifying (static webpage):

1. `fork` this repository or [origin repo](https://github.com/arcxingye/EatKano).

2. Modify the code. Here are some examples that can be modified:

   - `./index.html`: The main page, where options can be modified. For example, if this project has added three modes, corresponding dropdown options need to be added here.
   - `./static/index.js`: Game code, where game mechanics can be modified, such as creating the method `nextKeyGen()` in this project to control key generation, adding `_gameHealth` determination, etc.
   - `./static/index.css`: Game interface style, where the appearance can be modified. For example, in this project, the `.t*` block corresponding to `ClickBefore` can be modified to achieve loading of multiple images.
   - `./static/image`: Image directory.
   - `./static/i18n`: A multilingual module where you can modify UI text for different language backgrounds.

3. Once modified, it can be used directly.

   Note that if running locally, the cross domain template may not be found `./static/i18n/*.json`，You can create a local server for access through `Python`'s built-in command `python -m http.server [port_id]`.
   
## Others

Please star us~

Welcome to pull request!