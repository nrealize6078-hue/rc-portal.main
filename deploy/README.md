# リアライズクラブ 各種コンテンツ — GitHub Pages デプロイ用一式

このフォルダの中身を **そのまま** リポジトリのルートに push してください。

## 同梱ファイル
- `index.html` — トップページ（旧 realize-club-contents.html）
- `images/` — 画像7点（mio-sensei.png ほか）
- `.nojekyll` — Jekyll を無効化（フォルダ名や `_` 始まりのファイルで弾かれないため）

## デプロイ手順（新規リポジトリの場合）

```bash
# このフォルダに入る
cd deploy

# Git 初期化
git init
git branch -M main

# リモートを設定（YOUR_USERNAME と REPO_NAME を置き換え）
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git

# 全ファイルをコミット
git add -A
git commit -m "Initial deploy: realize club contents"

# push
git push -u origin main
```

## GitHub Pages 設定

1. GitHubリポジトリの **Settings → Pages** を開く
2. **Source** を `Deploy from a branch` に
3. **Branch** を `main` / `/ (root)` に設定
4. **Save** を押す
5. 1〜2分待つと `https://YOUR_USERNAME.github.io/REPO_NAME/` で公開される

## 既存リポジトリに追加する場合

```bash
# 既存リポジトリに index.html がある場合は名前を変えてバックアップ
git mv index.html index-old.html

# このフォルダの内容を既存リポジトリのルートにコピーして commit
cp -r deploy/* deploy/.nojekyll /path/to/your/repo/
cd /path/to/your/repo
git add -A
git commit -m "Add realize club contents page"
git push
```

## 404 のチェックリスト

- [ ] `index.html` がリポジトリのルートにある（サブフォルダではない）
- [ ] `images/` フォルダもリポジトリに含まれている
- [ ] `.nojekyll` ファイルがある（重要）
- [ ] Settings → Pages の Source / Branch が正しい
- [ ] push 後 1〜2分待った
- [ ] URL の末尾は `/` で終わる（例: `https://user.github.io/repo/`）

## 公開後のアクセスURL

- `https://<ユーザー名>.github.io/<リポジトリ名>/` でトップページが表示されます
