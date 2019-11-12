---
title: "[QtCreator]Linux上でC,C++の実行環境を構築してみた"
summary: "QtCreatorでC++を実行"
date: 2019-09-20T18:02:05+09:00
tags: ["environment", "c++", "linux"]
header:
  image: "https://fugublog.netlify.com/technology/images/qt_img.png"
---
<br>

コーディングの練習や競技プログラミングなどで、ちょっとしたコードを動かしたい人。
こういう方を対象にc,cppファイルを実行できるまでの手順を簡単にまとめました。  
<br>
OSはArchLinuxです。また、統合開発環境のQtCreatorを使用します。
[Qt(キュート）](https://ja.wikipedia.org/wiki/Qt)とは、アプリ開発をするためのツールの一つです。  
Qtホームページ >> [https://www.qt.io](https://www.qt.io)  

<br>
```
目次  
1. qtcreatorのインストール  
2. プロジェクトの作成  
3. ビルド・実行
```
  
<br><br>
***
### 1.qtcreatorのインストール  
<br>
<code>$ sudo pacman -Sy qtcreator</code>  

ArchでないLinuxディストリビューション（Ubuntuとか）をお使いの方は
"OS名 qtcreator install" などで検索をかけて読み替えてください(人∀・)  
<br>
[パッケージ情報](https://www.archlinux.org/packages/extra/x86_64/qtcreator/)を見ると依存関係としてqt5,clang(コンパイラ),gdb(デバッガ)などがあります。
これらは必須ですので入らなかったら適宜インストール。
<br><br>
***

### 2.プロジェクトの作成  
<br>
アプリケーション一覧から**qtcreator**を選択↓
![右クリックでお気に入りに追加しておくと便利](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-19 23-36-12.png)
<br>
ホーム画面から**新しいプロジェクト**を選択↓
![新しいプロジェクト](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-05-39.png)
<br>
**アプリケーション**の**Qt Widgets Application**を選択↓
![Qt Widgets Application](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-05-39.png)
<br>
プロジェクト名を適当につける↓
![MyDebugProject](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-07-35.png)
<br>
そのまま**次へ**を押す↓
![qmake](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-07-43.png)
<br>
そのまま**次へ**を押す↓
![詳細](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-07-52.png)
<br>
上のバーに**デスクトップ**と入力↓
![キットの選択](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-08-02.png)
<br>
そのまま**次へ**を押す↓
![概要](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-08-07.png)
<br>
するとmain.cppが立ち上がります

<br><br>
***
### 3.ビルド・実行  
<br>
## qtcreator側の設定の確認  
<br>
ツールバーの**ツール**から**オプション**を選択↓
![ツール](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 14-05-08.png)
<br>
**Kits**を選択し**コンパイラ**タブを開きます
ここで、コンパイラが自動検出されていることを確認してください。
されてなかったら**手動**に**usr/bin/clang**などのパスを指定。↓
![コンパイラ](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 14-05-41.png)
<br>
**デバッグ**タブを開く
ここで、デバッガが自動検出されていることを確認してください。
されてなかったら**手動**に**usr/bin/gdb**などのパスを指定。↓
![デバッガ](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 14-05-45.png)
<br>
## includeディレクトリの追加  
<br>
C/C++上の様々なキーワードを扱うためにincludeディレクトリ、ファイルを作成します。
できる人はunixコマンドで操作してください。
<br><br><br>
ファイルアプリでプロジェクトフォルダを開く→右クリックで"include"ディレクトリを作成↓
![プロジェクトフォルダ](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-31-05.png)
<br>
includeディレクトリに入り"bits"ディレクトリを作成↓
![bits](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 13-44-48.png)
<br>
テキストエディタを開き、次のコードをコピペする↓

```
#include <iostream> // cout, endl, cin  
#include <string> // string, to_string, stoi  
#include <vector> // vector  
#include <algorithm> // min, max, swap, sort, reverse, lower_bound, upper_bound  
#include <utility> // pair, make_pair  
#include <tuple> // tuple, make_tuple  
#include <cstdint> // int64_t, int*_t  
#include <cstdio> // printf  
#include <map> // map  
#include <queue> // queue, priority_queue  
#include <set> // set  
#include <stack> // stack  
#include <deque> // deque  
#include <unordered_map> // unordered_map  
#include <unordered_set> // unordered_set  
#include <bitset> // bitset  
```
<br>
ファイル名を"stdc++.h"とし、bitsディレクトリの中に保存します。
<br><br>
## 実行  
<br>
簡単なコードを実行してみます。main.cppを次のコードに置き換えてください。

```
#include <bits/stdc++.h>  
using namespace std;

int main(){

    cout << "Type name: ";
    string s;cin >> s;

    cout << "Hello, " << s << "!" << endl;

    return 0;

}
```
<br>
  
左下にある緑矢印のアイコンをクリック↓
![実行](https://fugublog.netlify.com/technology/images/Screenshot from 2019-09-20 16-02-40.png)
<br>
スタブが呼び出されたら成功です。お疲れ様でした（*^_^*）
<br>
