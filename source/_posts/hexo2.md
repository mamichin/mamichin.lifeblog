---
title: HexoでGithubにブログを作る2　GitHubにデプロイする編
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

もう１年前の事でしょうか。google Homeアプリ作ってみようと勉強会に参加したときに「デプロイ」という言葉を初めて知りました。グーグル先生に「デプロイとは」と入れて調べたところ、「展開」という意味だそうな。。え？リリースとかじゃダメ？なんか微妙にちょっと違うだけじゃない？なんか、「ホットケーキ」を「パンケーキ」と呼ぶようになったのと同じ感覚。。

まぁいいんですけど～。

## 前提
[HexoでGithubにブログを作る1　ローカルでHexoのWebページ準備編](https://hexo.io/docs/)済み

## GitHubにリポジトリ作成し、ソースコミット
GitHubにブログ用のリポジトリ(mamichin/mamichin.lifeblog)を作ります。
以下を実施して、gitにソースをmasterにコミットします。
``` bash
git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/mamichin/mamichin.lifeblog.git
git push -u origin master
```
pusu時にGithubのアカウント名やパスワードが聞かれた場合があります。

## config.ymlのDeployment書き換え

mamichin.blog直下にある_config.ymlファイルの以下を書き換えます。
``` yml
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: https://mamichin.github.io/mamichin.blog
root: /mamichin.blog/

# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/mamichin/mamichin.lifeblog.git
  branch: master
```

## git デプロイ
Hexoの git デプロイプラグインをインストールします。
``` bash
npm install hexo-deployer-git --save
```

公開用ファイルを作成(generate)し、デプロイ(deploy)します。
``` bash
hexo generate
hexo deploy
```
まとめてできます
``` bash
hexo deploy -g
```

## git デプロイでエラー
こんなエラーが出ました。
``` bash
Host key verification failed.
fatal: Could not read from remote repository.
```
こちらのサイトを参考に設定して解決です。
[gitHubでssh接続する手順~公開鍵・秘密鍵の生成から~](https://qiita.com/shizuma/items/2b2f873a0034839e47ce)

## git デプロイでエラー
https://mamichin.github.io/mamichin.blog
