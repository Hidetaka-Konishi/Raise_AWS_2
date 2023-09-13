# Gitの初期設定
 新規リポジトリのデフォルトブランチ名をmainに変更　```git config --global init.defaultBranch main```
 
 ユーザー名の設定　```git config --global user.name "ユーザー名"```

 メールアドレスの設定　```git config --global user.email "メールアドレス"```

設定内容の確認　```git config --global --list```

# GitHubでプルリクエストを発行する手順
1. GitHubで新しいリポジトリを作成します。

2. ローカルマシンに対してクローンを作成するために、コマンドプロンプトを開き```git clone [リポジトリのURL]```を実行します。

3. ```cd [リポジトリ名]```[^1]を実行し、クローンしたローカルリポジトリに移動します。そして、ブランチを作成するために```git checkout -b [ブランチ名]```を実行します。ブランチ名で指定する名前は自由です。

4. ```notepad lecture02.md```のようにコマンドを実行すると、テキストエディタが起動するので、ファイルに情報を書き込んで保存します。今回は、Windowsのメモ帳を使用するので```notepad```になります。 ```lecture02.md```はファイル名です。任意の名前を付けてください。

5. ローカルリポジトリの変更を宣言するためのコマンド```git add lecture02.md```を実行します。

6. ローカルリポジトリの変更を決定するためのコマンド```git commit -m "Added my learning in lecture02.md"```を実行します。```"Added my learning in lecture02.md"```の部分はこのコミットが何の目的で変更されたのかを書く説明書きの部分です。

7. リモートリポジトリにプッシュするためのコマンド```git push origin [リポジトリ名]``` を実行します。

8. GitHubのリポジトリのページから「Pull requests」タブ、「New Pull Request」ボタンをクリックします。ブランチの選択では、今回lecture02ブランチを使用したいので「lecture02」を選択します。「Create Pull Request」をクリックするとプルリクエストが完成します。

[^1]: リポジトリのURLがhttps://github.com/Hidetaka-Konishi/kadai_3.gitだった場合のリポジトリ名はkadai_3になる

# コンフリクトを解消し、git pushするまでの流れ
1. コンフリクトが発生しているファイルを特定するために```git status```を実行する。実行して開かれたメッセージに「Unmerged paths」という場所の「both added」にコンフリクトが発生しているファイル名が記載されている。
2. Windowsのエクスプローラーを開き、コンフリクトを起こしているファイル名をエクスプローラーの検索欄から検索し、そのファイルをクリック、「Windowsを検索する」を選択する。
3. 対象のファイルをテキストエディタで開いたらコンフリクトが発生している部分が以下のように示されている。

```markdown
<<<<<<< HEAD
This is my change.
=======
This is the change from the remote.
>>>>>>> origin/main
```

仮に「This is my change.」の部分を採用したい場合は以下のように編集します。編集が終わったらファイルを保存することでコンフリクトが解消されます。

```markdown
This is my change.
```
4. ```git add [ファイル名]```を実行。
5. ```git commit -m "任意のメッセージ"```を実行。
6. ```git push [リポジトリのURL] [ブランチ名]```を実行。

# git pullからgit pushまでの手順
1. ```cd リポジトリ名```で操作したいリポジトリに移動する。
2. ```git pull [リポジトリのURL] [ブランチ名]```を実行する。
3. Windowsのエクスプローラーから変更したいファイルを探し、変更します。
4. ```git add .```を実行する。
5. ```git commit -m "任意のメッセージ"```を実行する。
6. ```git push [リモートリポジトリのURL] [ブランチ名]```を実行する。
