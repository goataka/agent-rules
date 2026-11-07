# 自動チェックルール

## プロジェクトに入れる

- **対象**：Markdown、シェルスクリプト、GitHub Actionsのワークフロー、秘密情報、コードの整形
- **ツール**：
  - Markdown：markdownlint-cli
  - シェルスクリプト：shellcheck
  - GitHub Actions：node-actionlint
  - 秘密情報：secretlint
  - 整形：prettier
- **スクリプト**：`package.json` に、チェックごとのスクリプトを定義する
  - 例：`lint:markdown`、`lint:shellcheck`、`lint:actionlint`、`lint:secrets`
- **集約**：`lint` スクリプトで、すべてのチェックをまとめて実行する
- **コミット前**：husky と lint-staged で、変更したファイルだけをチェックする
- **除外**：生成物や依存関係は除外設定に入れる
  - 例：`node_modules`、`dist`、`build`
- **無効化**：ルールを無効にする場合は、理由をコメントで残す
- **バージョン**：`^` で指定し、ロックファイルで固定する
- **実行環境**：Node.js は LTS を使う

## GHAで利用する

- **実行タイミング**：PRの作成・更新時に、`lint` スクリプトを実行する
- **同じコマンド**：ローカルと同じコマンドを使い、結果の差をなくす
- **ワークフロー**：ワークフローを変更したPRでは、actionlint を必ず実行する
- **権限**：`permissions` は必要な権限だけを明示する
- **キャッシュ**：依存関係のキャッシュを使い、実行時間を短くする
- **同時実行**：`concurrency` で、同じPRの古い実行を止める
- **必須化**：ブランチ保護で、Lintのチェックを必須にする
- **自動修正**：生成物を除き、CIで自動修正してコミットしない。失敗させ、開発者が修正する
