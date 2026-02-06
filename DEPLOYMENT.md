# 🚀 デプロイメントガイド (Deployment Guide)

このドキュメントでは、WebAR名刺アプリケーションをCloudflare Pagesにデプロイする方法を説明します。

## 📋 前提条件

- GitHubアカウント
- Cloudflareアカウント（無料）

## ⚙️ Cloudflare Pagesの設定

### 1. Cloudflareダッシュボードにアクセス

1. [Cloudflare Dashboard](https://dash.cloudflare.com/) にログイン
2. 左サイドバーの「Workers & Pages」を選択
3. 「Create」→「Pages」→「Connect to Git」をクリック

### 2. GitHubリポジトリを接続

1. GitHubアカウントを連携
2. リポジトリ `WebAR` を選択
3. **Build settings** で以下を設定:
   - Framework preset: `None`
   - Build command: （空欄）
   - Build output directory: `/`
4. **Save and Deploy** をクリック

### 3. デプロイの確認

1. 数分待つ（初回は2〜5分かかる場合があります）
2. デプロイ完了後、URLが表示されます:
   ```
   Your site is live at https://webar-36q.pages.dev/
   ```
3. URLをクリックしてアプリケーションを確認

## 🔄 更新のデプロイ

コードを変更した後、Cloudflare Pagesは自動的に更新されます:

1. 変更をコミット: `git commit -m "Update business card info"`
2. GitHubにプッシュ: `git push origin main`
3. 数分待つ（通常1〜2分）
4. ブラウザでページをリロード（キャッシュクリアが必要な場合があります）

## 🎯 カスタムドメインの設定（オプション）

独自のドメイン（例: ar.example.com）を使用する場合:

1. Cloudflare Pagesのプロジェクト設定で「Custom domains」を選択
2. ドメインを入力して追加
3. Cloudflareでドメインを管理している場合は自動設定

## 📱 QRコードの更新

デプロイ後、正しいURLでQRコードを生成してください:

1. `marker-generator.html` をブラウザで開く
2. 「アプリケーションURL」に実際のURLを入力:
   ```
   https://webar-36q.pages.dev/
   ```
3. 「QRコード生成」をクリック
4. ダウンロードして名刺に印刷

## ✅ デプロイ確認チェックリスト

- [ ] Cloudflare Pagesのデプロイが成功している
- [ ] URLにアクセスできる
- [ ] スプラッシュ画面が表示される
- [ ] 「ARを開始」ボタンが機能する
- [ ] カメラ権限のリクエストが表示される（HTTPS経由）
- [ ] マーカーをカメラに向けるとAR情報が表示される

## �� トラブルシューティング

### "404 - File not found" エラー

- `main` ブランチが選択されているか確認
- `index.html` がルートディレクトリにあるか確認
- 数分待ってから再度アクセス

### カメラが動作しない

- Cloudflare PagesはHTTPSを自動的に使用するので問題なし
- ブラウザのカメラ権限を確認
- プライベートブラウジング/シークレットモードでは動作しない場合がある

### 変更が反映されない

- ブラウザのキャッシュをクリア（Ctrl+Shift+R または Cmd+Shift+R）
- Cloudflareダッシュボードでデプロイが完了するまで数分待つ
- 「Deployments」タブでビルドステータスを確認

## 📊 アナリティクス（オプション）

使用状況を追跡したい場合、Google Analyticsを追加できます:

```html
<!-- index.html の </head> の前に追加 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🔐 セキュリティ

- Cloudflare Pagesは自動的にHTTPSを有効化
- カメラアクセスにはHTTPSが必須
- 外部スクリプト（A-Frame、AR.js）はCDN経由で読み込み
- 個人情報は含めないことを推奨（名刺に印刷される情報のみ）

## 📞 サポート

問題が発生した場合:

1. [Cloudflare Pages ドキュメント](https://developers.cloudflare.com/pages/)を確認
2. リポジトリの Issues に問題を報告
3. README.md のトラブルシューティングセクションを参照

## 📝 次のステップ

1. ✅ Cloudflare Pagesを設定
2. ✅ URLを確認
3. ✅ 正しいURLでQRコードを生成
4. ✅ マーカーとQRコードを名刺に印刷
5. ✅ テスト配布して動作確認
6. 🎉 完成！
