## 1. スキーマ変更

- [x] 1.1 `src/content.config.ts` の blog スキーマに `tags: z.array(z.string())` を追加する（必須フィールド）
- [x] 1.2 `src/content/blog/Astroの導入メモ.md` のフロントマターに `tags` を追加する

## 2. 記事詳細ページへのタグ表示

- [x] 2.1 `src/layouts/BlogPost.astro` の Props 型に `tags` を追加する
- [x] 2.2 タイトルブロック内（`<hr />` 直前）にタグ一覧を表示する
- [x] 2.3 各タグに `/tags/<tag-name>/` へのリンクを付ける
- [x] 2.4 タグ表示のスタイルを追加する

## 3. 記事一覧ページへのタグ表示

- [x] 3.1 `src/pages/index.astro` の記事リスト内にタグを表示する

## 4. タグ別一覧ページの作成

- [x] 4.1 `src/pages/tags/[tag].astro` を新規作成する
- [x] 4.2 `getStaticPaths` で全タグのパスを生成する
- [x] 4.3 対象タグを持つ記事を日付降順で表示する

## 5. 動作確認

- [x] 5.1 `npm run build` がエラーなく完了することを確認する
- [x] 5.2 タグなし記事（既存の `Astroの導入メモ.md`）が正常に表示されることを確認する
