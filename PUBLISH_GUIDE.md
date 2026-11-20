# Antigravity / Codex向け: ROUTE SHIFT 3D公開手順

作業は**現在開いている3Dゲームのワークスペース**で行うこと。2D版の開発リポジトリや公開リポジトリは変更しないこと。

## 目的

3D版のソースコード・制作資料・秘密情報を公開せず、ブラウザで遊べるビルド成果物だけを `ysaki-dev/route-shift-3d-public` にデプロイする。

## 手順

1. 現在のワークスペースが3D版であることを `package.json`、エントリポイント、モデル素材、既存プレビューから検証。別フォルダを勝手に参照しない。
2. フレームワーク・ビルドコマンド・出力フォルダを特定し、GitHub Pages配下 `/route-shift-3d-public/` でアセットが解決できる設定にする。Viteなら原則 `base: '/route-shift-3d-public/'`。開発サーバーのローカル表示を損なわないようにする。
3. 依存関係インストール、ビルド、テストを実行。ビルドが成功したことと `index.html`、JS、CSS、GLB、テクスチャ、音声などの参照が有効なことを確認。
4. 公開対象ファイルを**許可リスト方式**で洗い出す。特に `.env`、APIキー、Git情報、TS/TSXソース、テスト、ソースマップ、機密資料、ローカルパスを公開しない。Web向けにビルドされたJavaScriptやモデルは閲覧者に取得可能と明記する。
5. 元の3Dソースをそのまま `git push` しない。**ビルド後の配信用フォルダの中身だけ**を `https://github.com/ysaki-dev/route-shift-3d-public` の `main` ルートに反映する。README.md、PUBLISH_GUIDE.md、.nojekyllは残す。既存の無関係なファイルや成果物を無断削除しない。
6. [Pages設定](https://github.com/ysaki-dev/route-shift-3d-public/settings/pages) は `Deploy from a branch → main / (root)`。設定UIが人間の操作を必要とするなら、その1操作だけ明示する。
7. [Actions](https://github.com/ysaki-dev/route-shift-3d-public/actions) でデプロイを確認し、`https://ysaki-dev.github.io/route-shift-3d-public/` で3D画面表示、モデル読込、操作、CPU対戦、ストーリーブック、音声、ブラウザConsoleの404をチェックする。

## 禁止事項

- Private開発リポジトリをPublicへ変更しない。
- 2D版のGitHub Pagesサイトを上書きしない。
- 3Dソース全体、開発Git履歴、機密情報をPublicにpushしない。
- GitHubのブランチを `push --force` で上書きしない。
- 公開できていない段階で公開済みと報告しない。

## 最終報告

ビルド・テストの結果、公開に含めたファイルと除外したファイル、commit SHA、Pagesのデプロイ成否、実際のアクセス確認、残る人間側の操作だけを報告する。
