# CLAUDE.md

このファイルは Claude Code (AI アシスタント) 向けのプロジェクト情報です。

## CRITICAL: 作業開始前の必須手順

**ファイルを編集する前に、必ず以下を実行すること。これは絶対に省略してはならない。**

1. `git branch` または `git status` で現在のブランチを確認する
2. `main` ブランチにいる場合は、**必ず**作業用ブランチを作成してから編集を始める

```bash
git checkout -b feature/作業内容  # 新機能・変更
git checkout -b fix/バグ内容      # バグ修正
```

- `main` ブランチへの直接コミットは禁止
- ブランチ名は変更内容が分かる名前にすること

## プロジェクト概要

Astro フレームワークを使ったブログサイト。MDX による記事執筆、RSS フィード、サイトマップ生成に対応しています。

## 開発コマンド

```bash
npm run dev      # 開発サーバー起動 (localhost:4321)
npm run build    # 本番ビルド
npm run preview  # ビルド結果のプレビュー
```

## プロジェクト構成

```
src/
  assets/          # 画像等の静的アセット
  components/      # 再利用可能な Astro コンポーネント
    BaseHead.astro      # <head> タグ内のメタ情報
    Header.astro        # サイトヘッダー
    HeaderLink.astro    # ヘッダーのナビゲーションリンク
    Footer.astro        # サイトフッター
    FormattedDate.astro # 日付フォーマット表示
  content/
    blog/          # ブログ記事 (.md / .mdx)
  layouts/         # ページレイアウト
  pages/           # ルーティング対応ページ
    index.astro         # トップページ
    about.astro         # About ページ
    blog/               # ブログ一覧・詳細ページ
    rss.xml.js          # RSS フィード
  styles/
    global.css     # グローバルスタイル
  consts.ts        # サイト名・説明などの定数
  content.config.ts # コンテンツコレクション定義
public/            # 静的ファイル (favicon 等)
astro.config.mjs   # Astro 設定
tsconfig.json      # TypeScript 設定
```

## 主要な設定・定数

- サイトURL: `astro.config.mjs` の `site` フィールド
- サイトタイトル・説明: `src/consts.ts`
- コンテンツスキーマ: `src/content.config.ts`

## 使用インテグレーション

- `@astrojs/mdx` — MDX サポート
- `@astrojs/sitemap` — サイトマップ自動生成
- `@astrojs/rss` — RSS フィード生成
- `sharp` — 画像最適化

## 記事の追加方法

`src/content/blog/` に `.md` または `.mdx` ファイルを追加します。
フロントマターの必須フィールドは `src/content.config.ts` のスキーマを参照してください。


## 注意事項

- TypeScript を使用しているため、型エラーに注意すること
- コンテンツコレクションのスキーマ変更時は既存記事との整合性を確認すること
