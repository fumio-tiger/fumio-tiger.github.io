# Change: ブログ記事へのタグ付与と表示機能の追加

## Why

現在、ブログ記事にはカテゴリ・タグの概念がなく、記事の分類や関連記事の発見が難しい。
タグを導入することで、読者が関心のあるトピックの記事を素早く見つけられるようにする。

## What Changes

- `src/content.config.ts`: コンテンツスキーマに `tags` フィールド（**必須**、文字列配列）を追加
- `src/layouts/BlogPost.astro`: 記事詳細ページのタイトル下にタグを表示
- `src/pages/index.astro`: 記事一覧の各エントリにタグを表示
- `src/pages/tags/[tag].astro`: タグ別記事一覧ページを新規作成（`/tags/<tag-name>/`）

## Impact

- Affected specs: blog-tagging（新規）
- Affected code:
  - `src/content.config.ts` — スキーマ変更（**BREAKING**: `tags` は必須フィールド）
  - `src/content/blog/Astroの導入メモ.md` — `tags` フィールドを追加（既存記事の修正）
  - `src/layouts/BlogPost.astro` — タグ表示 UI 追加
  - `src/pages/index.astro` — タグ表示 UI 追加
  - `src/pages/tags/[tag].astro` — 新規ファイル
