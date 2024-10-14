# GitHubにローカルのファイルをアップロードする手順

リモートリポジトリが空で、ローカルに既にファイルが存在する場合、以下の手順でローカルのプロジェクトをリモートリポジトリに接続し、ファイルをアップロードできます。

## 手順

### 1. ローカルリポジトリを初期化

まず、ファイルがあるディレクトリに移動し、Gitリポジトリを初期化します。

```bash
cd /path/to/your/project  
git init
```

### 2. ファイルをステージング

すべてのファイルをGitに追加します。

```bash
git add .
```

### 3. コミット

変更をコミットします。

```bash
git commit -m "Initial commit"
```

### 4. リモートリポジトリを追加

GitHubのリモートリポジトリを`origin`として追加します。

```bash
git remote add origin https://github.com/あなたのユーザー名/リポジトリ名.git
```

### 5. ブランチ名を設定

GitHubのデフォルトブランチが`main`の場合、ローカルのブランチ名を合わせます。

```bash
git branch -M main
```

### 6. リモートリポジトリにプッシュ

初回のプッシュで、リモートブランチを指定します。

```bash
git push -u origin main
```

## 補足

- **リモートにファイルが既にある場合**  
  例: GitHub上でREADMEファイルを作成している場合、プッシュ時にコンフリクトが起きる可能性があります。その場合は、以下のコマンドでリモートの変更をローカルにマージしてからプッシュします。

```bash
git pull origin main --allow-unrelated-histories  
git push origin main
```

これで、ローカルのファイルがGitHubにアップロードされます。

