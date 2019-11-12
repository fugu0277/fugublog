---
title: "[Git・GitHubとは？]システムの概要と使い方"
summary: GitHubを使いこなすのはエンジニアの必須スキルです。この記事ではGit・GitHubについてわかりやすく解説します。
date: 2019-10-07T19:41:26+09:00
draft: false
tags: ["git", "github", "setup"]
header:
  image: "https://fugublog.netlify.com/technology/images/git_github_image.png"
---
<br>

エンジニアの方なら誰もが耳にするであろうGit（ギット）・GitHub（ギットハブ）。
これらは開発プロジェクトで使われるソースコードの管理システムです。
<br>
概要と開発プロジェクトでの使い方を解説します。
OSはWindows,Mac,Linux系OSに対応。 

<br>
```
目次  
1. Gitとは？  
2. GitHubとは？
3. GitHubのアカウントを作る
4. Gitのインストール
5. unixコマンドについて
6. Gitの使い方（基本）
7. Gitの使い方（ブランチ）
8. 開発プロジェクトでの使い方
```
<br> 
***
### 1.Gitとは？
<br>
一言でいうと**ソースファイルのバージョン管理システム**です。  
<br>
バージョンをコミットという単位で積み上げていくことで、  <br>
・どのようにそのソフトウェアが作られていったか  <br>
・いつの時点からバグが入り込んだか  
<br>
みたいなものをわかりやすくしてくれる。
<br>
<br>
***
### 2.GitHubとは?
<br>
Gitの仕組みを利用した、**ネット上でソースファイルを管理できるウェブサービス**のこと。  
<br>
## Gitを使いたい最大の理由
<br>
GitHub社のサービスを使うことで、クラウド上にソースコードを入れて、絶えず同期させながらコードを書くことができる。  
<br>
<br>
***
### 3.GitHubのアカウントを作る
<br>
GitHubのサインインページから、画面の指示に従って登録。  
sign in page >> https://github.com/join
<br>
<br>
***
### 4.Gitのインストール
<br>
## Mac,Linux系OSの場合は、すでにGitが入っている場合があります
<br>
ターミナル上で  
<code> $ git --version </code>  
を打って確認しましょう。
<br>
<br>
## インストール
<br>
インストーラをダウンロードします。  
Gitインストールページ >> https://git-scm.com  
<br>
左下の**Dawnloads**をクリックするとMac,Windows,Linuxなどのダウンロードボタンが表示されます。
ダウンロードしたら、インストーラをダブルクリックして起動させます。  
<br>
**Next >**を押し続けると**install**ボタンが現れます。
(Windowsの場合、GitBashというソフトウェアも入る。）
<br>
<br>
***
### 5.Unixコマンドについて
<br>
Unixコマンドという決まった単語を打ち込むと、ファイルやディレクトリの操作、Gitの操作などができます。
Mac/Linuxではターミナル（端末）、WindowsではGitBashというソフトウェアを開いてコマンドを打ちます。
<br><br>
## 覚えてほしいコマンド一覧
<br>
```
- ls: 今いるディレクトリのファイルを一覧表示
- cd: 別のディレクトリに移動（「cd ./Desktop」というような感じで)
- nano: エディタを起動して、ファイルを編集（「nano hello-world.py」というような感じで）
- start: Windowsのアプリケーションを開く（「start ./Documents」で、エクスプローラーをでDocumentsフォルダを開く）
```
<br><br>
***
### 6.Gitの使い方（基本）
<br>
基本的に以下を覚えればOK  
<br>
```
git clone <URL>
　　・GitHub上のリポジトリ（リモートリポジトリ）をローカルに持ってくる
git add -A
    ・編集されたファイルをステージというところに上げる（Gitで使います宣言)
git commit -m "メッセージ"
    ・ステージに上がったファイルをコミットし、一つのバージョンを作る。
    ・メッセージにはそのコミットの変更内容、理由などを書く（後で分かりやすいように）
git push
    ・ローカルのリポジトリをリモートのリポジトリに反映させる
    ・コミットしただけではGitHub上のリポジトリには反映されない
git config
    ・設定を変更
```
<br>
***
### 7.Gitの使い方（ブランチ）
<br>
Gitはブランチというものがあり、並行作業を行うときに使います
<br>
```
git checkout -b <ブランチ名>
    ・今のバージョンから派生して、ブランチを作る
git push -u origin HEAD
    ・ブランチを新しく作ったときは、GitHubのリポジトリを使うことが登録されないので、このコマンドで登録する必要がある。
```
<br>
***
### 8.開発プロジェクトでの使い方
<br>
GitHubを用いたチーム開発に参加すると仮定し、GitHubにコードを反映するまでの手順を紹介します。
<br><br>
## リポジトリをクローン
<br>
```
$ cd ./Desktop
$ git clone https://github.com/<hogehoge>/<プロジェクト名>
$ cd ./<プロジェクト名>
```
<br>
2行目はプロジェクトのURLを打ってください。**https://github.com/以降は異なります。**  
これでデスクトップに<プロジェクト名>フォルダができ、リポジトリの中身が入ります。
<br><br>
## ブランチを作成
<br>
```
$ git checkout -b <ブランチの名前> 
```
<br>
これでブランチが作成され、同時にブランチに入ります。
<br><br>
## 変更を加える
<br>
cloneしたリポジトリに変更を加えます。  
ファイル・フォルダの追加削除、コードの追加削除　など  
<br>
## コミット・プッシュ
<br>
```
$ git config --global user.email <GitHubに登録したメールアドレス>
$ git config --global user.name <GitHubのユーザーネーム>
$ git add -A
$ git commit -m "<コメント>"
$ git push -u origin HEAD
```
git pushでGitHubのIDとパスワードを求められるので、入力。  
![ID,パスワード入力](https://fugublog.netlify.com/technology/images/Screenshot from 2019-10-07 22-58-20.png)
<br>
これで、GitHubに変更内容（ブランチの作成も含む）が反映されます。
<br><br>
## プルリクエスト
<br>
プルリクエストは変更箇所を他の開発者に通知する機能です。  
GitHubのリポジトリのページに戻ります。  
**Pull Request**→**New pull request**→**compare**を先程作成したブランチに設定します。  
<br>
↓のようになったら成功です。
![プルリクエスト成功](https://fugublog.netlify.com/technology/images/Screenshot from 2019-10-07 22-58-27.png)
<br>
***
## 参照
"はじめてでもOK！Gitをインストールする方法【初心者向け】".TECHACADEMY magazine.    
https://techacademy.jp/magazine/5304, （参照 2019-10-07）
<br>
