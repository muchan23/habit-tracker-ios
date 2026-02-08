# Day 1 画面遷移

## 画面一覧

1. HabitListView（習慣一覧）
2. AddHabitView（習慣追加）
3. SettingsView（設定: v1はプレースホルダ）

## 遷移図

- HabitListView
  - 右上「+」タップ -> AddHabitView（モーダル）
  - 行のスワイプ削除 -> 習慣削除
  - 行のチェック操作 -> 当日達成ON/OFF
  - 下部またはナビゲーションから SettingsView（任意）
- AddHabitView
  - 保存 -> HabitListViewへ戻る（一覧更新）
  - キャンセル -> HabitListViewへ戻る

## 各画面責務

### HabitListView

- 習慣一覧表示
- 当日達成チェック操作
- ストリーク表示
- 削除操作

### AddHabitView

- 習慣名入力
- 入力バリデーション（空文字NG）
- 保存/キャンセル

### SettingsView

- v1では通知時刻などの将来設定用プレースホルダ

## UI文言（初期）

- タイトル: 習慣
- 追加ボタン: 追加
- 保存ボタン: 保存
- キャンセルボタン: キャンセル
- 空状態: 習慣を追加して始めましょう
