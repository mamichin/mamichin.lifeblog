---
title: HexoでGithubにブログを作る1　ローカルでHexoのWebページ準備編
date: 2018-12-02 17:25:35
category:
  - [Hexo]
  - [GitHub]
tags:
  - Hexo
  - GitHub
  - ブログ
  - 静的ウェブサイト
---
[Hexo](https://hexo.io/)を使ってGithub Pagesにブログを公開します。

GitHub Pages:http://mamichin.github.io
ブログ公開場所：https://github.com/mamichin/mamichin.lifeblog


静的WebページはHugoを使っていた事がありますが、今回Hexoを試してみる事にしました。静的Webページはすぐに出来る！！というイメージがなぜか自分の中に勝手にあって、手を出してみるものの、結局テーマ選択に迷い、カスタマイズに苦しみ、結構時間かかります。私、何がしたいのかな。。

WordPressはテーマが半端なく沢山あり、人気テーマを使うと断然そっちの方が速く終わる気がします。いや、でも勉強も兼ねて行きます。


## 前提
Gitインストール済み
Node.jsインストール済み

## Hexoインストール
[Hexo](https://hexo.io/docs/)を参考にインストールします。

``` bash
$ npm install -g hexo-cli
```

## Hexoセットアップ
新規ブログを作成します。
mamichin.lifeblogは適切な名前に変更します。
``` bash
$ hexo init mamichin.lifeblog
$ cd mamichin.lifeblog
$ npm install
```

## ローカルで確認
以下コマンドでローカルで作成したブログを確認します。
``` bash
$ hexo server
```
ローカルに Hexoサーバーが立ち上がって、 http://localhost:4000/ で見られるようになります。

## テーマの設定
Hexoのページにテーマがあるのでそこから好みのものを選んでテーマ設定をします。
[Hexoテーマ](https://hexo.io/themes/)から[light](https://github.com/hexojs/hexo-theme-light)を選択した場合は以下コマンドでcloneを作成します。

``` bash
$ git clone https://github.com/hexojs/hexo-theme-light.git theme/light
```
インストール完了後、mamichin.lifeblogは適切な名前に変更しますblogの_config.ymlにある
themeの箇所をlightに書き換えます。

``` yml
theme: light
```

http://localhost:4000/ を見たら更新されていると思います。ここで一旦終わります。
