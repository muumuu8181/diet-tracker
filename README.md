# Diet Tracker App

シンプルなダイエット記録アプリです。食事、飲み物、体重、トイレ、服装を記録でき、ドラッグ&ドロップで時間帯間の移動も可能です。

## 機能

- 📱 **レスポンシブデザイン**: モバイル・デスクトップ対応
- 🍽️ **食事記録**: 時刻と内容を記録
- 🥤 **飲み物記録**: 飲み始め〜飲み終わりの時間幅対応
- 👕 **服装記録**: 体重測定時の服装など
- 🚽 **トイレ記録**: 排尿・排便の記録
- ⚖️ **体重記録**: 服装メモ付き
- 🎯 **ドラッグ&ドロップ**: 記録を時間帯間で移動
- 📅 **日付切り替え**: 前日・翌日のデータ表示
- 💾 **ローカル保存**: LocalStorageでデータ永続化
- 🐛 **デバッグログ**: リアルタイムログ表示

## 時間帯

- 🌙 **深夜** (0-6時)
- ☀️ **朝** (6-12時)  
- 🌤️ **昼** (12-18時)
- 🌆 **夜** (18-24時)

## 技術仕様

- **フロントエンド**: HTML5, CSS3, Vanilla JavaScript
- **ストレージ**: LocalStorage
- **ドラッグ&ドロップ**: HTML5 Drag and Drop API
- **デザイン**: CSS Grid, Flexbox
- **ホスティング**: Firebase Hosting

## ローカル開発

```bash
# Firebase CLIをインストール
npm install -g firebase-tools

# Firebaseにログイン
firebase login

# ローカルサーバーで起動
firebase serve

# デプロイ
firebase deploy
```

## デプロイ手順

1. Firebase プロジェクトを作成
2. `firebase init hosting` でプロジェクトを初期化
3. `firebase deploy` でデプロイ

## ファイル構成

```
diet-tracker/
├── index.html          # メインアプリケーション
├── package.json        # プロジェクト設定
├── firebase.json       # Firebase Hosting設定
├── .gitignore         # Git除外設定
└── README.md          # このファイル
```

## 使い方

1. **記録追加**: 右下の+ボタンから記録タイプを選択
2. **時間帯移動**: 記録をドラッグ&ドロップで移動
3. **日付切り替え**: 上部の矢印ボタンで日付変更
4. **削除**: 各記録の×ボタンで削除
5. **デバッグ**: 右上のログエリアで動作確認

## ブラウザ対応

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## ライセンス

MIT License