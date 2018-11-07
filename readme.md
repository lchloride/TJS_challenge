# TJS challenge

This project contains the scripts for TJS tutorial series called TJSに挑戦(Challenge TJS). The original tutorials are written in Japanese whose link is [TJSに挑戦](http://tjs2.info/index.html).

## What is TJS?

TJS is the abbreviation of Text adventure game JavaScript. Usually, TJS stands for TJS2, which is used in KiriKiri game engine. In other words, **TJS is a kind of script designed for development of adventure games and visual novels.** The official engine/interpreter of TJS is called kirikiri2(吉里吉里2, krkr). This one can be run on Windows system only. However, there is another interpreter in Java called Habakiri(羽々斬) which can be used on non-Windows system like Linux.

TJS is designed based on ECMAScript 3, which means most of grammars are really similar to JavaScript. Thus, TJS does not seem to be hard for experienced JS coder. 

## How to run TJS script?

Two methods: official Kirikiri engine OR Habakiri--TJS interpreter in Java.

### Official Kirikiri engine(Windows needed)

Firstly, we need to download the latest version of kirikiri2. The link is [kr2_232r2.zip (吉里吉里2 SDK ダウンロード)](https://krkrz.github.io/download/kr2_232r2.zip). 

Secondly, decompress zip file to wherever you like. The following image shows the structure of Kirikiri engine.

![Krkr engine structure](https://chenghongli.com/zh/wp-content/uploads/sites/3/2018/11/TJS000201-copy.png)

Kag3 folder provides some templates of scripts, while kirikiri2 folder is the main part of krkr engine.

Thirdly, create a folder for your project with any name, then copy `kirikiri2/krkr.eXe` to the root of project. Also, copy the folder of your game data(usually called `data`) to the root of project. 

Last, if game data folder is called `data`, you can run it simply by double click on `krkr.eXe`. Otherwise, you need to drag and drop data folder on the `krkr.eXe`.

If you are testing the runnning environment, you can create a new folder called `data` in the project folder, and a new text file called `startup.tjs` in `data` folder.(Editing with Notepad is recommended.) Write the following codes in `startup.tjs` .

```javascript=
System.inform("Challenge TJS!");
```

Save `startup.tjs` in **ANSI encoding** and run `krkr.eXe` in the root of project.If you see a message box with content "Challenge TJS!", you've done that! Congratulations! 

Please note that all codes in this zip file encode in SHIFT-JIS(MS932). Thus you may see some strange symbols in the scripts if you do not open it under Windows in Japanese. **If you edit script using notepad, you have to save the file with ANSI encoding. If you are using other text editor like UltraEdit, Sublime Text, you have to save the file with encoding of the system, which is called code page of the system. For instance, for Japanese, you need to save it in SHIFT-JIS encoding; for Simplified Chinese, you need to save it in GBK encoding; for Traditional Chinese, you need to save it in BIG5 encoding; for English, you need to save it in Western encoding(such as ISO-8859-1). UTF-8 and unicode cannot be used here.**

### Habakiri--interpreter in Java

Firstly, download the source code from [habakiri/habakiri](https://github.com/habakiri/habakiri).

Secondly, open the projet in a IDE like IntellJ IDEA. Mark directory of `andriod` not as Java source codes, otherwise you will encounter errors when compiling the project. 

Thirdly, put your game data in the root of Habakiri project where you can find `core`, `desktop`, `andriod` and `JOrbis` directories. Note that this folder has to be called `data`.

Fourthly, open `core/src/jp/kirikiri/tvp2/base/Storage.java`, change the codes at line 480 if you want to run it on most of Unix/Linux system.

```java=
// encodeType = "MS932";
encodeType = "UTF-8";
```

Last, run `desktop/src/jp/kirikiri/tvp2env/Main.java`. Your game should be executed.

If you are testing the runnning environment, you can create a new folder called `data` in the project folder, and a new text file called `startup.tjs` in `data` folder.(Editing with Notepad is recommended.) Write the following codes in `startup.tjs` .

```javascript=
System.inform("Challenge TJS!");
```

Save `startup.tjs` in **UTF-8 encoding**(by default) and run `desktop/src/jp/kirikiri/tvp2env/Main.java` in the project. If you see a message box with content "Challenge TJS!", you've done that! Congratulations!

This approach uses scripts in UTF-8 encoding which are popular among all platforms. If you are using notepad on Windows, please make sure that you save it using UTF-8 encoding.

## Progress

Chapter 0: Introduction

- [x] Section 0.2: Prepare to write a script

Chapter 1: Basics of TJS

Chapter 2: Class

Chapter 3: Native Classes

Chapter 4: KAG Plug-in

Chapter 5: System Button

Chapter 6: Clickable Map

Chapter 7: Options

Chapter 8: Draggable Layer

Chapter 9: Methods of the Layer class

Chapter 10: Message History

Chapter 11: Downloading Data

## Translation of tutorials

Currently, I am processing the translations of these tutorials into Simplified Chinese. Here is the link of translations: [挑战TJS – CitrusLeaf](https://chenghongli.com/zh/tag/tjs-challenge/).

## Relations among Kirikiri2, KAG, TJS, KirikiriZ

Kirikiri2 and KirikiriZ are two branches of game engine for adventure games and visual novels. They are really similar to each other but KirikiriZ is being developed and maintained currently while Kirikiri2 is not.

TJS is a kind of script which can be run on Kirikiri2/KirikiriZ. This is what we learn in these tutorials/

KAG is a kind of game defintion script. It is based on TJS and would translated to TJS at parsing. KAG provided a relatively simple grammar which can be used by developers who are not familar with TJS or JavaScipt.

## Some well-known games made by Kirikiri series engine

- Fate/stay night 
- 魔法使の夜
- 千恋\*万花
- 9-nine-ここのつここのかここのいろ

