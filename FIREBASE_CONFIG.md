# Firebase設定の詳細手順

## 重要：アプリは現在LocalStorageモードで動作中

現在のアプリは各デバイスでLocalStorageにデータを保存しています。
Firebase設定を完了すると、全デバイス間でリアルタイム同期されます。

## Firebase Console での設定

### Step 1: プロジェクト作成
```
https://console.firebase.google.com/
↓
「プロジェクトを作成」
↓
プロジェクト名: diet-tracker-app
↓
Googleアナリティクス: 無効
↓
「プロジェクトを作成」
```

### Step 2: Realtime Database設定
```
左メニュー「構築」→「Realtime Database」
↓
「データベースを作成」
↓
場所: us-central1 (米国)
↓
セキュリティルール: 「テストモードで開始」
↓
「有効にする」
```

### Step 3: ウェブアプリ設定
```
プロジェクト概要の「</>」アイコンをクリック
↓
アプリのニックネーム: diet-tracker
↓
Firebase Hostingは「設定しない」
↓
「アプリを登録」
```

### Step 4: 設定コードを取得
Firebase Consoleに表示される以下のような設定をコピー：

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyB...",
  authDomain: "diet-tracker-app.firebaseapp.com",
  databaseURL: "https://diet-tracker-app-default-rtdb.firebaseio.com/",
  projectId: "diet-tracker-app",
  storageBucket: "diet-tracker-app.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef123456"
};
```

## GitHub上でのコード修正

### 方法1: GitHub Web Editor使用
1. https://github.com/muumuu8181/diet-tracker にアクセス
2. `index.html` をクリック
3. 編集ボタン（鉛筆アイコン）をクリック
4. 726-734行目を実際の設定に置き換え
5. 737-740行目のコメント（//）を削除
6. "Commit changes"

### 方法2: コードエディタ使用
```bash
# ローカルでファイルを編集後
git add index.html
git commit -m "Add Firebase configuration"
git push origin main
```

## 設定後の確認方法

1. **GitHub Pagesの更新を待つ**（2-3分）
2. **アプリにアクセス**: https://muumuu8181.github.io/diet-tracker/
3. **デバッグログを確認**:
   - 右上のログエリアで「Firebase: ON」表示
   - 「Firebase初期化完了」メッセージ
4. **同期テスト**:
   - スマホで記録追加
   - PCで同じ記録が表示されることを確認

## トラブルシューティング

### Firebase: OFFのまま
- `useFirebase = true` が設定されているか確認
- コンソールエラーを確認

### エラー: "Firebase not defined"
- Firebase SDKが正しく読み込まれているか確認
- インターネット接続を確認

### データが同期されない
- databaseURLが正しいか確認
- Realtime Databaseのルールを確認
- ブラウザのコンソールでエラーを確認

## セキュリティ設定（後日推奨）

テストモード（30日間有効）後は、以下のルールに変更：

```json
{
  "rules": {
    ".read": "auth != null",
    ".write": "auth != null"
  }
}
```

認証機能の追加も推奨します。