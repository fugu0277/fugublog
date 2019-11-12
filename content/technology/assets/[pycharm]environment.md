---
title: "[Pycharm]Python3の環境構築をしてみた"
summary: Pythonで開発をするための準備
date: 2019-09-21T19:41:26+09:00
draft: false
tags: ["environment", "python", "linux"]
header:
  image: "https://fugublog.netlify.com/technology/images/pycharm_img.png"
---
<br>
Pythonで開発することになったけど環境構築を済ませていない。。  
こういう方を対象に環境構築する手順を簡単に説明します。  
OSはWindows, Mac, Linux/Unixに対応。
<br><br>
統合開発環境(IDE)は[Pycharm](https://ja.wikipedia.org/wiki/PyCharm)を使います。  
イケてるUIに加え、Pythonのライブラリを簡単に入手できるのが特徴。  
<br>
Pycharmホームページ >> [https://www.jetbrains.com/pycharm/](https://www.jetbrains.com/pycharm/)  
<br><br>
```
目次  
1. Python3のインストール  
2. Pycharmインストール  
3. PycharmでPython3を使えるようにする  
+ Tips. ライブラリのインストール 
```
 
<br><br>
***
### 1.Python3インストール  
<br>
## Windows, Macの場合    
<br>
[ダウンロードページ](https://www.python.org/downloads/)からインストーラーを実行
（**Looking for Python with a different OS? Python for Windows, Linux/UNIX, Mac OS X, Other**から自分のOSのリンクに飛ぶ）↓
![installerをクリック](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-21 22-06-53.png)  
<br>
## Linuxの場合  
<br>
Python3は**python**パッケージから最新版を持ってこれる(ディストリビューションによっては **python3**)  
※ArchLinuxの場合
```
$ sudo pacman -S python
```
<br>
***
### 2.Pycharmインストール  
<br>
[ダウンロードページ](https://www.jetbrains.com/pycharm/download/#section=windows)から環境を選びファイルをダウンロード　※画像はLinuxの場合↓
![JetBrainDownloadPage](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-21 22-56-14.png)

(.exeや.dmgだとそのままPycharmを起動できる。)  
<br>
## Linuxの場合  
<br>
圧縮ファイルを解凍する↓
![ここで展開するをクリック](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-21 22-13-45.png)
<br>
Pycharmを起動します(移動先は解凍したディレクトリの中）
```
$ cd Downloads/pycharm-community-2019.2.1/bin
$ bash pycharm.sh
```
<br>
***
### 3.PycharmでPython3を使えるようにする  
<br>
スタート画面の**Configure**から**Settings**をクリック↓
![Start>Configure>Settings](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-22 00-00-41.png)  
<br>
ツールバーの**Project Interpreter**を選択.↓
右上の歯車アイコンから**Show All**をクリックし、インストールしたPython3を選択。↓
![SetPython](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-21 23-18-16.png)  
<br>
これでPythonを実行できます。  お疲れ様でした（*^_^*）  
<br><br>
***
### Tips.ライブラリのインストール  
<br>
開発においてPythonを使う最大の理由は、ライブラリ（Pythonを拡張するファイル群）が豊富なことだと思います。
Pycharmではライブラリを簡単に導入できます。  

**Project Interpreter**画面の歯車アイコンの下にある**+ボタン**をクリック。
検索バーに入力できるようになるので、入手したいライブラリ名を入力。
最後に、**Install Package**をクリック。  
<br><br>
***
## 参照  

"Pycharmのインストール方法".GAMMASOFT.
https://gammasoft.jp/python/pycharm-install-on-windows/, （参照 2019-09-22）  
<br>
