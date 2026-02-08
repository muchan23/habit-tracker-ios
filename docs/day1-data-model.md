# Day 1 データ項目定義

## Habit

- `id: UUID`
- `name: String`
- `createdAt: Date`
- `checkmarks: [String]`

備考:
- `checkmarks` は `yyyy-MM-dd` 形式の日付文字列配列とする。
- 1日1チェック前提で同一日付の重複は許可しない。

## 派生値

- `isCompletedToday: Bool`
- `currentStreak: Int`

## ストリーク計算ルール（v1）

1. 今日の日付文字列を生成する。
2. 今日が未達成なら `currentStreak = 0`。
3. 今日が達成済みなら、昨日、一昨日...と連続日数を数える。
4. 連続が途切れた時点でカウントを終了する。

## 永続化方針（Day 2で実装）

- 第一候補: SwiftData
- 代替案: UserDefaults + JSONエンコード

判断基準:
- 学習目的でApple標準を優先するためSwiftDataを第一候補にする。
- 実装複雑度が上がる場合はUserDefaultsへ一時切り替え可。
