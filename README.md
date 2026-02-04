# WebAR 名刺アプリケーション

QRコードを使用した名刺向けWebARアプリケーション

## 🚀 デモ

GitHub Pagesでホストされています: `https://<your-username>.github.io/WebAR/`

例: `https://igawakazuha.github.io/WebAR/`

## 📱 機能

- **QRコード統合**: 名刺にQRコードを印刷し、簡単にWebARアプリにアクセス
- **マーカーベースAR**: カメラを名刺のマーカーに向けると、3D情報が表示されます
- **カスタマイズ可能**: 名前、役職、連絡先情報を簡単にカスタマイズ
- **モバイル対応**: スマートフォンやタブレットで動作
- **GitHub Pages対応**: 追加のサーバー設定不要で公開可能

## 🛠️ セットアップ

### 1. GitHub Pagesの有効化

1. GitHubリポジトリの **Settings** > **Pages** に移動
2. **Source** で `main` ブランチを選択
3. **Save** をクリック
4. 数分後、`https://あなたのユーザー名.github.io/WebAR/` でアクセス可能になります

### 2. 名刺の作成

#### マーカーのダウンロード

1. `marker-generator.html` をブラウザで開く
2. 「マーカーをダウンロード」ボタンをクリック
3. ダウンロードした画像を名刺に印刷（推奨サイズ: 5cm × 5cm以上）

#### QRコードの生成

1. `marker-generator.html` の QRコード生成セクションを使用
2. あなたのGitHub PagesのURLを入力（例: `https://igawakazuha.github.io/WebAR/`）
3. 「QRコード生成」ボタンをクリック
4. QRコードをダウンロードして名刺に印刷（推奨サイズ: 2cm × 2cm程度）

### 3. 情報のカスタマイズ

`index.html` を編集して、表示される情報をカスタマイズします:

```html
<!-- 名前 -->
<a-text value="山田 太郎" ...>

<!-- 役職 -->
<a-text value="Webデベロッパー" ...>

<!-- メールアドレス -->
<a-text value="yamada@example.com" ...>

<!-- 電話番号 -->
<a-text value="TEL: 03-1234-5678" ...>
```

## 📖 使い方

### エンドユーザー向け

1. 名刺のQRコードをスキャン
2. WebARアプリケーションが開きます
3. 「ARを開始」ボタンをクリック
4. カメラの使用を許可
5. カメラを名刺のマーカーに向ける
6. AR情報が表示されます！

### 開発者向け

```bash
# リポジトリのクローン
git clone https://github.com/あなたのユーザー名/WebAR.git
cd WebAR

# ローカルサーバーで起動（HTTPSが必要です）
python3 -m http.server 8000

# ブラウザで開く
# Chrome/Edge: chrome://flags で "Insecure origins treated as secure" を有効化し、
# localhost:8000 を追加してカメラアクセスを許可
```

## 📁 ファイル構成

```
WebAR/
├── index.html                  # メインのWebARアプリケーション
├── marker-generator.html       # マーカーとQRコード生成ツール
├── marker-training.html        # カスタムマーカートレーニング（オプション）
├── assets/
│   ├── marker.png             # 印刷用マーカー画像
│   └── pattern-marker.patt    # AR.js用マーカーパターン
└── README.md                   # このファイル
```

## 🎨 カスタマイズ

### 3Dコンテンツの変更

`index.html` の `<a-marker>` セクションを編集して、3Dオブジェクトをカスタマイズできます:

```html
<!-- 例: 別の3Dモデルを追加 -->
<a-entity gltf-model="url(./assets/your-model.glb)" ...></a-entity>
```

### スタイルの変更

スプラッシュ画面やUIの色は、`<style>` タグ内で変更できます。

## 🔧 技術スタック

- **A-Frame**: WebVRフレームワーク
- **AR.js**: マーカーベースAR
- **QRCode.js**: QRコード生成
- **GitHub Pages**: ホスティング

## 📝 注意事項

- **HTTPSが必要**: カメラアクセスにはHTTPS接続が必要です（GitHub Pagesは自動的にHTTPSを使用）
- **照明**: マーカー認識には十分な照明が必要です
- **マーカーサイズ**: 小さすぎるマーカーは認識が困難です（5cm × 5cm以上推奨）
- **ブラウザ互換性**: Chrome、Safari、Edge、Firefoxで動作確認済み

## 🤝 貢献

プルリクエストを歓迎します！大きな変更の場合は、まずIssueを開いて変更内容を議論してください。

## 📄 ライセンス

MIT License

## 🔗 リンク

- [AR.js Documentation](https://ar-js-org.github.io/AR.js-Docs/)
- [A-Frame Documentation](https://aframe.io/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

## 💡 トラブルシューティング

### カメラが起動しない
- ブラウザのカメラ権限を確認してください
- HTTPSで接続していることを確認してください

### マーカーが認識されない
- マーカーが十分な大きさで印刷されているか確認
- 照明が十分か確認
- マーカーが平らな面にあるか確認
- カメラのフォーカスが合っているか確認

### GitHub Pagesで表示されない
- リポジトリが公開されているか確認
- GitHub Pages設定で正しいブランチが選択されているか確認
- 数分待ってから再度アクセスしてみてください