# リポジトリ管理ルール

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

公開リポジトリのみに適用する条件は1項目とする

7. **自動マージ**：Allow auto-merge を有効にする

### 設定後の確認

- **設定の変更後**：設定画面の値を読み直し、想定どおりであることを確認する

## goatakaの場合

- **一覧の管理**：[service-desk](https://github.com/goataka/service-desk) の [README](https://github.com/goataka/service-desk/blob/main/README.md) と [REPOSITORY_MANAGEMENT.md](https://github.com/goataka/service-desk/blob/main/REPOSITORY_MANAGEMENT.md) に従う
