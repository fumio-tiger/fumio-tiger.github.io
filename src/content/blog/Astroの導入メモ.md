---
title: 'Astroでブログを作ってみる（導入メモ）'
description: 'Astroでブログを作ってみる（導入メモ）'
pubDate: '2026/2/14'
tags: ['Astro']
---

Astroを使ってブログを作ってみようと思い、導入手順をメモとして置いときます

## 環境作成について

当初は、試験的な利用ということで devcontainer を使って環境を構築しようと思ってたんですが、
実際に確認してみると、Astroはフレームワークとしてインストールされるだけなので、すでにプロジェクトに隔離されており普通に作成すればよかった感じです。

そのため、今回は devcontainer は使用せず、通常のローカル環境でプロジェクトを作成しました

## プロジェクト作成

プロジェクト作成はめっちゃ簡単で、以下のコマンドを実行するだけで、セットアップが開始されます。

```bash
npm create astro@latest
```

コマンドを実行すると、対話形式でいくつか質問されるので、表示される選択肢に従って進めていくだけで初期プロジェクトが作成できます。

特に難しい設定はなくぽちぽち選択する程度で完了です。

![](/images/astro-sample.gif)

## GitHub Pages でサイトを公開する

作成した Astro のサイトは、GitHub Pages で公開することができそうなので、公式ドキュメントの手順を参照しながら設定します

[AstroサイトをGitHub Pagesにデプロイする | Docs](https://docs.astro.build/ja/guides/deploy/github/)

手順的には

1. GitHubのリモートリポジトリを `<owner_name>.github.io` にして作成する
1. Astroの公式サイトで提供されているGitHub Actionsのコードをそのまま利用する
	- `.github/workflows/deploy.yml`として追加
1. Astroの `astro.config.mjs`にある`site`のURLを変更する

な感じで完了です。

あとはmainブランチにpushするか、mergeするだけでサイトが公開されます。
