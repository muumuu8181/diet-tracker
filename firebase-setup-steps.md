# Firebase設定手順（5分で完了）

## 1. Firebase プロジェクト作成
1. [Firebase Console](https://console.firebase.google.com/) にアクセス
2. 「プロジェクトを作成」をクリック
3. プロジェクト名を入力（例：`diet-tracker-app`）
4. Googleアナリティクスは「無効」でOK
5. 「プロジェクトを作成」

## 2. Realtime Database 有効化
1. 左メニューの「構築」→「Realtime Database」
2. 「データベースを作成」をクリック
3. 場所：「米国」でOK
4. セキュリティルール：「テストモードで開始」を選択（30日間公開アクセス可能）
5. 「有効にする」

## 3. ウェブアプリの設定取得
1. プロジェクト概要ページで「ウェブ」アイコン（</>）をクリック
2. アプリのニックネーム：`diet-tracker`
3. 「アプリを登録」
4. 表示された設定をコピー

## 4. アプリに設定を適用

**以下のコードをコピーして、GitHub上のindex.htmlを編集してください：**

### 726-734行目を以下に置き換え：
```javascript
const firebaseConfig = {
    apiKey: "[ここに実際のAPIキーを貼り付け]",
    authDomain: "[ここに実際のauthDomainを貼り付け]",
    databaseURL: "[ここに実際のdatabaseURLを貼り付け]",
    projectId: "[ここに実際のprojectIdを貼り付け]",
    storageBucket: "[ここに実際のstorageBucketを貼り付け]",
    messagingSenderId: "[ここに実際のmessagingSenderIdを貼り付け]",
    appId: "[ここに実際のappIdを貼り付け]"
};
```

### 737-740行目のコメントを外す：
```javascript
firebase.initializeApp(firebaseConfig);
const database = firebase.database();
const mealsRef = database.ref('diet-tracker-meals');
useFirebase = true;
```

## 5. 動作確認
1. GitHubにコミット・プッシュ
2. 数分待ってからアプリにアクセス
3. 右上のデバッグログで「Firebase: ON」を確認
4. 複数の端末でアクセスして同期をテスト

## 注意事項
- テストモードは30日間有効
- 無料枠：1GB ストレージ、10GB/月 転送量
- 同時接続：100接続まで無料
- 本番環境では認証設定が必要