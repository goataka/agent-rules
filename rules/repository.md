# リポジトリ管理ルール

## 一覧の管理

- **管理先**：[service-desk](https://github.com/goataka/service-desk) の [README](https://github.com/goataka/service-desk/blob/main/README.md) にリポジトリ一覧を置く
- **詳細**：[REPOSITORY_MANAGEMENT.md](https://github.com/goataka/service-desk/blob/main/REPOSITORY_MANAGEMENT.md) に並び順、設定条件、反映状況の見方を置く
- **対象**：所有する全リポジトリとし、フォークも含める
- **区分**：非公開と公開で表を分け、非公開を上に置く
- **列**：リポジトリ、説明、反映状況の3列とする
- **説明**：説明のないリポジトリは「—」とする

## 並び順

- **基準**：利用頻度の高い順
- **指標**：既定ブランチの直近1年のコミット数の降順
- **同数の場合**：直近3か月のコミット数の降順、次にリポジトリ名の順

## 設定条件

### 全リポジトリ共通

全リポジトリ共通の条件は6項目とする

1. **Wiki 無効**：Wiki 機能をオフにする
2. **Issue/PR 関係者のみ**：Issue permissions と Pull request permissions を Collaborators only にする
   - 期限：なし
3. **Squash のみ**：マージ方式を Squash merge のみ許可する
   - 不許可：Merge commit と Rebase merge
4. **Squash メッセージ=PR タイトル**：Squash merge のコミットメッセージを Pull request title にする
5. **更新ブランチ提案**：Always suggest updating pull request branches を有効にする
6. **ブランチ自動削除**：Automatically delete head branches を有効にする

### 公開リポジトリの追加条件

公開リポジトリのみに適用する条件は2項目とする

7. **自動マージ**：Allow auto-merge を有効にする
8. **Interaction limits**：Limit to repository collaborators を最長の6か月で有効にする
   - 注意：期限になると自動解除されるため、再設定する
   - 補足：解除後も条件2により関係者のみは維持される

## 反映状況

- **表記**：反映済みの項目数/対象の項目数
- **対象項目数**：公開リポジトリは条件1〜8の8項目、非公開リポジトリは条件1〜6の6項目
- **状態**：
  - **反映済み**：すべて反映
  - **一部反映**：一部のみ反映
  - **未反映**：ほぼ反映できていない
- **例外**：個別の例外は説明欄に記載する
- **確認日**：反映状況を確認した日を記載する

## 運用

- **リポジトリの追加時**：設定条件を反映し、並び順に従う位置に一覧へ追加する
- **設定の変更後**：設定画面の値を読み直し、想定どおりであることを確認する
- **一覧の更新**：設定やコミット数が変わったら、反映状況と並び順を更新する
- **Interaction limits**：自動解除の前に再設定する
