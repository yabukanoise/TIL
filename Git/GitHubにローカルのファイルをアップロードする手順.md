---
title: "GitHubにローカルのファイルをアップロードする手順"
date: 2025-08-10T13:55:03+09:00
draft: false
---

# GitHubにローカルのファイルをアップロードする手順

リモートリポジトリが空で、ローカルに既にファイルが存在する場合、以下の手順でローカルのプロジェクトをリモートリポジトリに接続し、ファイルをアップロードする。

## 手順

### 1. ローカルリポジトリの初期化

ファイルがあるディレクトリに移動し、Gitリポジトリを初期化する。

```bash
cd /path/to/your/project  
git init
```

### 2. ファイルのステージング

すべてのファイルをGitに追加する。

```bash
git add .
```

### 3. コミットの実行

変更をコミットする。

```bash
git commit -m "Initial commit"
```

### 4. リモートリポジトリの追加

GitHubのリモートリポジトリを`origin`として追加する。

```bash
git remote add origin https://github.com/あなたのユーザー名/リポジトリ名.git
```

### 5. ブランチ名の設定

GitHubのデフォルトブランチが`main`の場合、ローカルのブランチ名を合わせる。

```bash
git branch -M main
```

### 6. リモートリポジトリへのプッシュ

初回のプッシュで、リモートブランチを指定する。

```bash
git push -u origin main
```

## 補足

- **リモートにファイルが既に存在する場合**  
  例: GitHub上でREADMEファイルを作成している場合、プッシュ時にコンフリクトが発生する可能性がある。その場合、以下のコマンドでリモートの変更をローカルにマージしてからプッシュする。

```bash
git pull origin main --allow-unrelated-histories  
git push origin main
```

これで、ローカルのファイルをGitHubにアップロードできる。
