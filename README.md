# 基本的な操作方法

<br>

## ターミナルで新しいフォルダを作る

1. **新しいフォルダを作成する**

- 以下のコマンドで、`my-first-website`という名前のフォルダが作成される。
  ```sh
  mkdir #my-first-website
  ```
- 今作ったフォルダの中に移動する
  ```sh
  cd my-first-website
  ```

2. **GitとGitHubの準備**

- Gitがインストールされているか確認する
  ※バージョンが表示されたらOK

  ```sh
  　git --version
  ```
- Gitの名前を設定

  ```sh
  　git config --global user.name"Your Name"
  ```
- Gitのメールアドレスを設定

  ```sh
  　git config --global user.email "Your.email@example.com"
  ```

3. **リモートリポジトリを作る**

- GitHubにログイン
- 右上の「+」マークをクリック → 「New repository」を選択
- 以下の情報を入力：
  　　Repository name: my-first-website
  　　Description: 「初めてのウェブサイト」（任意）
  　　Publicを選択（無料で公開）
  　　他のチェックボックスは全て外す（重要！）
  　　「Create repository」をクリック

4. **リモートリポジトリを作る**

- ターミナルに戻って、現在のフォルダをGitリポジトリにする。
  ※「Initialized empty Git repository」と表示されたら成功
  ```sh
  　git init
  ```

5. **リモートとローカルを紐づける**

- GitHubのページに表示されているURLをコピーして、以下のコマンドを実行
  ```sh
  　git remote add origin https://github.com/あなたのユーザー名/my-first-website.git
  ```
- 確認する
  ※originという名前でURLが登録されていれば成功
  ```sh
  　git remote -v
  ```

6. **HTMLファイルを作る**

- index.htmlファイルを作成
  ```sh
  　echo '`<!DOCTYPE html>`' > index.html
  ```
- テキストエディタでファイルを編集する
  ```sh
  　open index.html
  ```
- 以下のHTMLコードをコピー・貼り付け・保存（ctrl+s）
  ```html

  ```

| `<!DOCTYPE html><br />``<html lang="ja"><br />``<br /><head>``<br />`  `<meta charset="utf-8"><br />`  `<meta name="viewport" content="width=device-width, initial-scale=1"><br />`  `<title>`初めてのウェブページ `</title><br />``</head><br />``<br /><body>``<br />`  `<p>`これは私が初めて作ったウェブページです。`</p><br />``</body><br />``<br /></html>` |
  |

```:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

```

7. **コミットとプッシュ**

- 変更されたファイルを確認する
  ※赤い文字で「index.html」が表示される
  ```sh
  　git status
  ```
- 変更したindex.htmlをステージに追加

```sh
  　git add index.html
```

- 状態を確認
  ※今度は緑色で「index.html」が表示される
  ```sh
  　git status
  ```
- コミット（保存）する
  ```sh
  　git commit -m "最初のホームページを作成"
  ```
- GitHubにmainブランチを作成
  ```sh
  　　git branch -M main
  ```
- - GitHubにプッシュ（アップロード）する

  ```sh
  git push -u origin main
  ```

8. **GitHub Pagesで公開する**
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

---

## ファイルを作成してGitHubにプッシュする方法

### パターン1：新しいファイルを追加してプッシュする

1. **リポジトリフォルダ内に移動する**
   ターミナルを開き、以下のコマンドでリポジトリフォルダに移動する。

   ```sh
   cd #programming
   ```
2. **新しいファイルを作成**
   リポジトリフォルダ内に移動し、以下のコマンドで新しいファイルを作成する。

   ```sh
   touch #new_file.md
   ```
3. **作成したファイルをVSCodeで開く**
   以下コマンドでVSCodeでファイルを開き、保存 `ctrl s`する。

   ```sh
   code #new_file.md
   ```
4. **Gitにファイルの存在を知らせる**
   以下のコマンドで、新しく追加した `new_file.md`をGitの**ステージングエリア**に追加する。ステージングエリアとは、次にコミットする変更の一覧を準備する場所。

   ```sh
   git add new_file.md
   ```

   ⚠️ 複数のファイルをまとめて追加したい場合は、`git add .`とすると、フォルダ内の全ての変更をまとめてステージングできる。

   <br>
5. **変更内容を確定（コミット）**
   ステージングエリアに追加した変更に、\*\*「今回の変更はこういう内容です」\*\*という説明文（コミットメッセージ）を付けて確定する。

   ```sh
   git commit -m "feat: add new_file.md"
   ```

   * `git commit`: 変更を確定するコマンド
   * `-m`: コミットメッセージをコマンドライン上で直接入力するためのオプション
   * `"feat: add new_file.md"`: コミットメッセージ。`feat`は「機能追加」という意味。
     どんな変更か分かりやすく書くようにする。

   <br>
6. **GitHubにプッシュ**
   ローカルで確定した変更を、GitHubのリモートリポジトリにアップロードする。

   ```sh
   git push origin main
   ```

   * `git push`: ローカルの変更をリモートに反映させるコマンド
   * `origin main`: 準備で使った `git pull`と同じく、アップロード先を指定している。
     `<br>`

以上の手順で、GitHubのリポジトリに新しい `new_file.md`が追加される。

---

## パターン2：既存のファイルを編集してプッシュする

すでに存在する `README.md`などのmdファイルの内容を更新して、その変更をGitHubに反映させる手順。

1. **ファイルを編集**
   リポジトリ内の既存のmdファイル（例：`README.md`）を以下コマンドで開き、内容を好きなように編集して保存する。

   ```
   code #ファイル名
   ```
2. **Gitにファイルの変更を知らせる**
   変更した `README.md`をステージングエリアに追加する。

   ```sh
   git add README.md
   ```

   💡どのファイルが変更されたか確認したい時は、`git status`コマンドが便利。ステージングエリアに追加されていない変更があれば赤文字で表示される。
3. **変更内容を確定（コミット）**
   変更内容が分かるように、コミットメッセージを付けて確定します。

   ```sh
   git commit -m "docs: update README.md"
   ```

   * `"docs: update README.md"`: 今回はドキュメントの更新なので、`docs`というプレフィックスを付けている。
4. **GitHubにプッシュ**
   最後に、ローカルの変更をGitHubにプッシュする。

   ```sh
   git push origin main
   ```

   以上の手順で、GitHub上の `README.md`が、編集した最新の内容に更新される。

---

## まとめ

どちらのパターンも、基本的な流れは同じ。

1. **`git pull`**: まずリモートの最新を取得して、作業を始める
2. **`git add`**: 変更をステージングエリアに追加する
3. **`git commit`**: 変更内容を確定する
4. **`git push`**: 確定した変更をGitHubに送る
