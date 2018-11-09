# 挑战TJS

> [Readme English Version](https://github.com/lchloride/TJS_challenge/blob/master/readme.md)

本项目为TJS系列教程“TJSに挑戦”(挑战TJS)的相关脚本。TJS教程(日语)的原始链接为[TJSに挑戦](http://tjs2.info/index.html)。


## TJS是什么？

TJS是Text adventure game JavaScript(文字冒险游戏JavaScript)的缩写。通常上，TJS指的是TJS2(第二版本)，也被用于吉里吉里游戏引擎。换句话说，**TJS是一种用于冒险游戏和视觉小说开发的脚本语言**。官方的TJS引擎/解释器被称为吉里吉里2(kirikiri2, krkr)。krkr只能在Windows系统中运行，使用C++开发。另外，还有一款使用Java开发的兼容多种操作系统的解释器，它被称为Habakiri(羽々斬)。

TJS设计上基于ECMAScript3，这意味着它大多数的语法和JavaScript是相似的。因此，对于有经验的JS程序员，TJS并不会很困难。

## 如何运行TJS脚本

两种方法：官方krkr引擎 或 Habakiri——Java版TJS解释器。

### 官方krkr引擎(需要Windows)

首先，我们需要下载kirikiri2的最新版本。链接是[kr2_232r2.zip (吉里吉里2 SDK ダウンロード)](https://krkrz.github.io/download/kr2_232r2.zip)。

第二，解压压缩包到合适的位置。下面的图片展示了krkr引擎的结构。

![Krkr engine structure](https://chenghongli.com/zh/wp-content/uploads/sites/3/2018/11/TJS000201-copy.png)

Kag3文件夹提供了脚本的模板，kirikiri2文件夹则是krkr引擎的主要部分。

第三，为你的项目创建一个文件夹，名字任意。(测试环境下简短的名字更好吧。)然后将`kirikiri2/krkr.eXe`复制到项目的根目录下。同时，将你的游戏数据文件夹(通常叫`data`)也复制到项目根目录下。

最后，如果游戏数据文件夹叫做`data`，你可以通过双击`krkr.eXe`直接运行游戏。否则，你需要将游戏数据文件夹拖放到`krkr.eXe`上。

如果你只是想测试一下运行环境，在复制`krkr.eXe`之后，你可以在项目根目录上创建一个名为`data`的文件夹，并且在内部创建一个名为`startup.tjs` 的文本文件。(推荐使用记事本编辑。)在`startup.tjs` 写入如下代码。

```javascript=
System.inform("挑战TJS!");
```

使用ANSI编码保存`startup.tjs`，然后运行项目跟目录下的`krkr.eXe`。如果你看到一个消息框，内部写着“挑战TJS!”，那说明你成功了。祝贺！

请注意，krkr压缩包中的全部文件都是使用SHIFT-JIS(MS932)进行编码的。因此，如果你没有在日语Windows下打开，你很可能在脚本中会看到一些奇怪的符号。**如果你使用记事本编辑，一定要保存为ANSI编码。如果你使用诸如UltraEdit、Sublime Text等其他文本编辑器，一定将脚本保存为当前系统的字符集(符号页)。例如，对于日语Windows，需要保存成SHIFT-JIS编码；对于简体中文Windows，你要保存成GBK编码；对于繁体中文Windows，你需要保存成BIG5编码；对于英语Windows，你需要保存成Western(ISO-8859-1)编码。UTF-8和unicode都是不支持的。**

### Habakiri——Java版TJS解释器。

首先，从[habakiri/habakiri](https://github.com/habakiri/habakiri)下载源代码。

第二，使用IDE打开项目，如IntellJ IDEA。将`andriod/src`目录取消标记为Java源代码。否则在便以项目时会遇到错误。

第三，将你的游戏数据放在Habakiri项目的根目录，与`core`, `desktop`, `andriod` 和 `JOrbis` 目录同级。注意这个文件夹必需叫做`data`。

第四，如果你希望在多数的Unix/Linux系统上运行，打开`core/src/jp/kirikiri/tvp2/base/Storage.java`，修改第480行的`encodeType`。

```java=
// encodeType = "MS932";
encodeType = "UTF-8";
```

最后，运行`desktop/src/jp/kirikiri/tvp2env/Main.java`。 游戏即可运行。

如果你只是想测试一下运行环境，你可以在Habakiri项目根目录上创建一个名为`data`的文件夹，并且在内部创建一个名为`startup.tjs` 的文本文件。在`startup.tjs` 写入如下代码。

```javascript=
System.inform("挑战TJS!");
```

使用**UTF-8编码**保存`startup.tjs`，然后运行`desktop/src/jp/kirikiri/tvp2env/Main.java`。如果你看到一个消息框，内部写着“挑战TJS!”，那说明你成功了。祝贺！

此方法使用的是在大多数系统上通用的UTF-8编码。如果你使用的是Windows上的记事本，请务必保存为Utf-8编码(非默认编码)。

## 翻译+实现进度

第0章: 介绍

- [x] [挑战TJS section 0.2：写脚本之前的准备](https://chenghongli.com/zh/tech/tjs-challenge-0-2-prepare-to-write-a-script/)

第1章: TJS基础

- [x] [挑战TJS Section1.1：脚本的写法](https://chenghongli.com/zh/tech/js-challenge-1-1-write-scripts/)
- [x] [挑战TJS Section1.2：方法的使用](https://chenghongli.com/zh/tech/tjs-challenge-1-2-use-methods/)

第2章: 类

第3章: 基础类

第4章: KAG插件

第5章: 系统按钮

第6章: 可点击地图

第7章: 分支选项

第8章: 可拖动图层

第9章: 图层类的方法

第10章: 消息历史

第11章: 下载数据

## 教程的翻译

我现在在进行教程的简体中文翻译。已经翻译的文章可以通过[挑战TJS – CitrusLeaf](https://chenghongli.com/zh/tag/tjs-challenge/)查看。

## Kirikiri2, KAG, TJS和KirikiriZ的关系

Kirikiri2与KirikiriZ是两个krkr引擎的两个分支。两者基本相同(准确说KirikiriZ是从Kirikiri2处fork过来的)。KirikiriZ现在仍然在开发和维护中，而Kirikiri2现已不再维护。KirikiriZ在Kirikiri2的基础上修复了一些bug并且提升了最高分辨率支持到1920\*1080.对于新作游戏的开发，建议使用KirikiriZ。

TJS是能够在Kirikiri2、KirikiriZ上运行的脚本语言。它是我们在教程中所要学习的内容。

KAG是一种游戏定义脚本。它实现机制基于TJS并且在解析的时候会翻译为TJS。KAG提供了相对简单的语法，可以方便不熟悉TJS和JavaScript的开发者使用。在实际开发中，通常以KAG为主，TJS为辅的开发模式。游戏场景设定使用KAG完成，特殊的运行机制和操作使用TJS定义。

## 一些使用Krkr系引擎开发的游戏

- Fate/stay night 
- 魔法使の夜
- 千恋\*万花
- 9-nine-ここのつここのかここのいろ

