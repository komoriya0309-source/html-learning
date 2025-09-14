# ２日目で学んだこと

## 昨日の復習

- 前回と同じ流れで新しいリポジトリを作成した
- ローカルリポジトリの作成〜リモートリポジトリの作成、プッシュまで
- Markdown（マークダウン）記法について

## 詳しい手順

1. ターミナルで新しいフォルダを作る（作らない場合は飛ばす）

- 新しいフォルダを作成する
  mkdir my-first-website
  →my-first-websiteという名前のフォルダが作成される
- 今作ったフォルダの中に移動する
  　cd my-first-website


2. GitとGitHubの準備

- Gitがインストールされているか確認する
  　git --version　　※バージョンが表示されたらOK
- Gitの名前を設定
  　git config --global user.name"Your Name"
- Gitのメールアドレスを設定
  　git config --global user.email "Your.email@example.com"


3. リモートリポジトリを作る

- GitHubにログイン
- 右上の「+」マークをクリック → 「New repository」を選択
- 以下の情報を入力：
  　　Repository name: my-first-website
  　　Description: 「初めてのウェブサイト」（任意）
  　　Publicを選択（無料で公開）
  　　他のチェックボックスは全て外す（重要！）
  　　「Create repository」をクリック


4. リモートリポジトリを作る

- ターミナルに戻って、現在のフォルダをGitリポジトリにする
  　git init　※「Initialized empty Git repository」と表示されたら成功


5. リモートとローカルを紐づける

- GitHubのページに表示されているURLをコピーして、以下のコマンドを実行
  　git remote add origin https://github.com/あなたのユーザー名/my-first-website.git
- 確認する
  　git remote -v　　※originという名前でURLが登録されていれば成功


6. HTMLファイルを作る

- index.htmlファイルを作成
  　echo '`<!DOCTYPE html>`' > index.html
- テキストエディタでファイルを編集する
  　open index.html
- 以下のHTMLコードをコピー・貼り付け・保存（ctrl+s）
| `<!DOCTYPE html>`<br />`<html lang="ja">`<br /><br />`<head>`<br />  `<meta charset="utf-8">`<br />  `<meta name="viewport" content="width=device-width, initial-scale=1">`<br />  `<title>`初めてのウェブページ `</title>`<br />`</head>`<br /><br />`<body>`<br />  `<p>`これは私が初めて作ったウェブページです。`</p>`<br />`</body>`<br /><br />`</html>` |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |


7. コミットとプッシュ
- 変更されたファイルを確認する
　git status　　※赤い文字で「index.html」が表示される
- 変更したindex.htmlをステージに追加
　git add index.html
- 状態を確認
　git status　　※今度は緑色で「index.html」が表示される
- コミット（保存）する
　git commit -m "最初のホームページを作成"
- GitHubにmainブランチを作成
　　git branch -M main
- - GitHubにプッシュ（アップロード）する
　　git push -u origin main


8. GitHub Pagesで公開する
GitHub Pagesを有効にする
- GitHubの自分のリポジトリページを開く
- 「Settings」タブをクリック
- 左側のメニューから「Pages」を選択
- 「Source」で以下を設定：
　　　Source: Deploy from a branch
　　　Branch: main
　　　Folder: / (root)
　　　「Save」をクリック


参考ページ：https://zenn.dev/ojk/books/intro-to-html-css/viewer/html-basic
