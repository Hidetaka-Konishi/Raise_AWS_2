# Gitの初期設定
 新規リポジトリのデフォルトブランチ名をmainに変更　```git config --global init.defaultBranch main```
 
 ユーザー名の設定　```git config --global user.name "ユーザー名"```

 メールアドレスの設定　```git config --global user.email "メールアドレス"```

設定内容の確認　```git config --global --list```

# GitHubでプルリクエストを発行、第三者にレビュー、マージまでの手順
1. GitHubで新しいリポジトリを作成します。

2. ローカルマシンに対してクローンを作成するためにはコマンドプロンプトを開き```git clone [リポジトリのURL]```を実行します。

3. ブランチを作成したいので ```cd [リポジトリ名]```を実行し、クローンしたローカルリポジトリに移動します。そして、ブランチを作成するために```git checkout -b [ブランチ名]```を実行する。

4. ```notepad lecture02.md```のようにコマンドを実行すると、テキストエディタが起動するので、そのファイルに情報を書き込んで保存します。今回は、Windowsのメモ帳を使用するので```notepad```になります。

5. ローカルリポジトリの変更を宣言するためのコマンド```git add lecture02.md```を実行します。

6. ローカルリポジトリの変更を決定するためのコマンド```git commit -m "Added my learning in lecture02.md"```を実行します。```"Added my learning in lecture02.md"```の部分はこのコミットが何の目的で変更されたのかを書く説明書き。

7. リモートリポジトリにプッシュするためのコマンド```git push origin lecture02``` を実行します。

8. 
