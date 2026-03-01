---
title: 'Pythonのローカル開発環境-2026'
description: 'Pythonのローカル開発環境-2026'
pubDate: '2026/3/1'
tags: ['Python', 'ローカル開発環境']
---

## これは

Pythonの環境を作成する時にこうする、というルールを記載しておく

## 利用するツールと目的

こういう目的でツールをそれぞれ使うようにする

- 仮想環境の作成
	- uv
- Pythonのバージョン管理
	- pyenv

`uv`でディレクトリごと仮想環境として作成し、その中で使用するPythonのバージョンを`pyenv`で行うイメージ

## コマンドの流れ

ここでは実行すコマンドをそのままの流れで書いておく
途中でPythonのバージョンなどは適宜確認しながら行えばいい

```zsh
# uvでプロジェクト作成
$ uv init <DirectoryName>

# ディレクトリに移動
$ cd <DirectoryName>

# インストールしたいPythonのバージョンをpyenvでインストールする
$ pyenv install <PythonVersion>

# ディレクトリ配下で利用するPythonのバージョンを指定する
$ pyenv local <PythonVersion>

# uvで仮想環境を作成する
$ uv venv

# 仮想環境をactivateする
$ source .venv/bin/activate
```

## パッケージのインストール

`uv add <package_name>`でインストールすればいい





