# Firebase Hosting デプロイ手順

## 前提条件

1. Node.js (v16以上) がインストールされていること
2. Googleアカウントがあること

## 手順

### 1. Firebase CLIのインストール

```bash
npm install -g firebase-tools
```

### 2. Firebaseにログイン

```bash
firebase login
```

ブラウザが開くので、Googleアカウントでログインしてください。

### 3. Firebaseプロジェクトの作成

Firebase Console (https://console.firebase.google.com/) で新しいプロジェクトを作成します：

1. "プロジェクトを追加" をクリック
2. プロジェクト名を入力 (例: `diet-tracker-app`)
3. Google Analyticsは任意
4. プロジェクトを作成

### 4. Firebaseプロジェクトの初期化

プロジェクトフォルダで以下を実行：

```bash
firebase init hosting
```

設定項目：
- **Use an existing project**: Yes
- **Select a default Firebase project**: 作成したプロジェクトを選択
- **What do you want to use as your public directory?**: `.` (カレントディレクトリ)
- **Configure as a single-page app**: Yes
- **Set up automatic builds and deploys with GitHub?**: No (今回は手動デプロイ)
- **Overwrite index.html?**: No (既存のindex.htmlを保持)

### 5. デプロイ

```bash
firebase deploy
```

成功すると、以下のようなURLが表示されます：
```
✔ Deploy complete!

Project Console: https://console.firebase.google.com/project/your-project-id/overview
Hosting URL: https://your-project-id.web.app
```

### 6. 確認

表示されたHosting URLでアプリが正常に動作することを確認してください。

## 継続的デプロイ

コードを更新した場合は、再度以下を実行：

```bash
firebase deploy
```

## カスタムドメイン設定 (任意)

Firebase Console > Hosting > カスタムドメインを追加 から独自ドメインを設定できます。

## トラブルシューティング

### エラー: Firebase CLI not found
```bash
npm install -g firebase-tools
```

### エラー: Not authorized
```bash
firebase logout
firebase login
```

### エラー: Project not found
```bash
firebase use --add
```
でプロジェクトを選択してください。

## 注意事項

- LocalStorageのデータはブラウザローカルに保存されます
- 複数デバイス間でのデータ同期はありません
- データのバックアップは定期的にコピーボタンでログを保存してください