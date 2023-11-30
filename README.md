# Gitの初期設定
 新規リポジトリのデフォルトブランチ名をmainに変更　`git config --global init.defaultBranch main`
 
 ユーザー名の設定　`git config --global user.name "ユーザー名"`

 メールアドレスの設定　`git config --global user.email "メールアドレス"`

設定内容の確認　`git config --global --list`

# GitHubでプルリクエストを発行する
1. GitHubで新しいリポジトリを作成する。
2. ローカルマシンに対してクローンを作成するために、PowerShellを開き`git clone [リポジトリのURL]`を実行する。
3. `cd [リポジトリ名]`[^1]を実行し、クローンしたローカルリポジトリに移動する。
4. ブランチを作成するために`git checkout -b [ブランチ名]`を実行する。ブランチ名で指定する名前は自由です。
5. `notepad [ファイル名].md`のようにコマンドを実行すると、テキストエディタが起動するので、ファイルに情報を書き込んで保存する。今回は、Windowsのメモ帳を使用するので`notepad`になる。 
6. ローカルリポジトリの変更を宣言するためのコマンド`git add .`を実行する。
7. ローカルリポジトリの変更を決定するためのコマンド`git commit -m "任意のメッセージ"`を実行する。`"任意のメッセージ"`の部分はこのコミットが何の目的で変更されたのかを書く説明書きの部分。
8. リモートリポジトリにプッシュするためのコマンド`git push origin [ブランチ名]`を実行する。
9. GitHubのリポジトリのページから「Pull requests」タブ、「New Pull Request」をクリックする。
10. ブランチの選択では、プルリクエストしたいブランチを選択し、「Create Pull Request」をクリックする。

[^1]: リポジトリのURLがhttps://github.com/Hidetaka-Konishi/kadai_3.gitだった場合のリポジトリ名はkadai_3になる

# コンフリクトを解消し、`git push`するまでの流れ
1. コンフリクトが発生しているファイルを特定するために`git status`を実行する。実行して開かれたメッセージに「Unmerged paths」という場所の「both added」にコンフリクトが発生しているファイル名が記載されている。
2. Windowsのエクスプローラーを開き、コンフリクトを起こしているファイル名をエクスプローラーの検索欄から検索し、そのファイルをクリック、「Windowsを検索する」を選択する。
3. 対象のファイルをテキストエディタで開いたらコンフリクトが発生している部分が以下のように示されている。

```
<<<<<<< HEAD
This is my change.
=======
This is the change from the remote.
>>>>>>> origin/main
```

仮に「This is my change.」の部分を採用したい場合は以下のように編集します。編集が終わったらファイルを保存することでコンフリクトが解消されます。

```
This is my change.
```
4. `git add .`を実行する。
5. `git commit -m "任意のメッセージ"`を実行する。
6. `git push [リポジトリのURL] [ブランチ名]`を実行する。

# `git pull`から`git push`まで
1. `cd [リポジトリ名]`で操作したいリポジトリに移動する。
2. `git branch`を実行して、`git push`する予定のブランチにいるかを確認する。もし、`git push`するブランチとは違うブランチにいる場合は`git checkout [ブランチ名]`でブランチを切り替える。
3. `git pull [リポジトリのURL] [ブランチ名]`を実行する。
4. Windowsのエクスプローラーから変更したいファイルを探し、変更する。
5. `git add .`を実行する。
6. `git commit -m "任意のメッセージ"`を実行する。
7. `git push origin [ブランチ名]`を実行する。

# ローカルの画像をリモートリポジトリのmdファイルに反映させたプルリクエスト
1. GitHubで新しいリポジトリを作成する。
2. `git clone [リポジトリのURL]`を実行する。
3. `cd [リポジトリ名]`を実行し、クローンしたローカルリポジトリに移動する。
4. ブランチを作成するために`git checkout -b [ブランチ名]`を実行する。
5. `notepad [ファイル名].md`のようにコマンドを実行すると、テキストエディタが起動するので、ファイルに情報を書き込んで「保存」をクリックする。今回は、Windowsのメモ帳を使用するので`notepad`になる。
6.  mdファイルが保存されているフォルダにを開き、その中に画像を保存するためのフォルダを作成する。
7.  画像用のフォルダに画像をドラッグアンドドロップする。
8.  ドラッグアンドドロップした画像のファイル名を変更する。
9.  画像のパスを取得して、そのパスを`![任意のメッセージ](./フォルダ名/ファイル名)`の形式に書き換えてmdファイルに記載し、保存する。
10.  `git add .`を実行する。
11.  `git commit -m "任意のメッセージ"`を実行する。
12.  `git push origin [ブランチ名]` を実行する。
13. GitHubのリポジトリのページから「Pull requests」タブ、「New Pull Request」をクリックする。
14. ブランチの選択では、プルリクエストしたいブランチを選択し、「Create Pull Request」をクリックする。
