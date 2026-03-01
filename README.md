# techblog

ZennとQiitaの記事をGitHubで同時管理するリポジトリです。

[C-Naoki/zenn-qiita-sync](https://github.com/C-Naoki/zenn-qiita-sync) を利用して、Zenn形式で書いた記事を自動的にQiita形式に変換・同期します。

## ディレクトリ構造

```
.
├── .github/
│   └── workflows/
│       └── publish.yml   # 自動同期ワークフロー
├── articles/             # Zenn記事（Zenn CLIで管理）
├── books/                # Zenn本（任意）
├── images/               # 記事で使う画像
└── qiita/
    └── public/           # Qiita記事（自動生成）
```

## セットアップ

### 1. Qiitaトークンの設定

[Qiita > 設定 > アプリケーション](https://qiita.com/settings/applications) でアクセストークンを発行し、GitHubリポジトリの `Settings > Secrets and variables > Actions` に `QIITA_TOKEN` として登録します。

### 2. ZennのGitHub連携

[Zenn Dashboard](https://zenn.dev/dashboard/deploys) でこのリポジトリを連携します。

## 使い方

```bash
# 新しい記事を作成
npm run zenn:new

# Zennプレビュー
npm run zenn:preview

# Qiitaプレビュー
npm run qiita:preview
```

mainブランチにpushすると、GitHub Actionsが自動的にQiitaへも同期します。

## 参考

- [ZennとQiitaの記事をGitHubで同時管理](https://zenn.dev/k42uma/articles/zenn-qiita-sync)
- [C-Naoki/zenn-qiita-sync](https://github.com/C-Naoki/zenn-qiita-sync)
- [Zenn CLI](https://github.com/zenn-dev/zenn-editor)
- [Qiita CLI](https://github.com/increments/qiita-cli)
