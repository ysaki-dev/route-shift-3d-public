# ROUTE SHIFT 3D — 公開配信リポジトリ

ROUTE SHIFT 3Dの**Webブラウザ向け配信ファイル専用**リポジトリです。

## Private / Public の分離

- 3D版の開発用ソース、Git履歴、テスト、制作資料、秘密情報は**ローカルの開発作業環境または別のPrivateリポジトリ**で管理します。
- このPublicリポジトリには、**公開を意図したビルド済みの静的Webファイルのみ**を配置します。
- ブラウザに配信する `index.html`、JavaScript、CSS、3Dモデル、テクスチャ、音声は、**閲覧者に取得・解析され得ます**。ビルド済みJavaScriptまで秘密にすることはできません。
- APIキー、`.env`、機密情報、ソースマップ、不要な開発資料を含めないでください。
- 既存の2D版 `checkpoint-strategy-game-public` とは独立して公開します。

## 公開予定URL

https://ysaki-dev.github.io/route-shift-3d-public/

> 現在の公開URLは、実際のゲームファイルが配置され、GitHub Pagesの設定・デプロイが完了するまで使用できません。

## 公開の流れ

1. Privateの3D開発環境で、使用中のビルドツールを確認する。
2. GitHub Pagesのサブパス `/route-shift-3d-public/` に対応させ、静的サイトとしてビルドする（Viteの場合は `base` の設定に注意）。
3. `dist/` 等の**ビルド成果物の内容のみ**をこのリポジトリのルートへ配置する。`index.html` がルート直下に必要。
4. [Settings → Pages](https://github.com/ysaki-dev/route-shift-3d-public/settings/pages) で `Deploy from a branch`、`main`、`/(root)` を選択して保存する。
5. [Actions](https://github.com/ysaki-dev/route-shift-3d-public/actions) で成功を確認し、別ブラウザで動作確認する。

**GitHub上のREADMEやこのリポジトリの内容だけでは、3Dゲーム本体をビルドできません。** ローカルの3Dプロジェクトのファイルが必要です。

## 関連リンク

- [GitHub Pages公式ガイド](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Vite公式の静的デプロイ](https://vite.dev/guide/static-deploy)
