# Gitの初期設定
 新規リポジトリのデフォルトブランチ名をmainに変更　```git config --global init.defaultBranch main```
 
 ユーザー名の設定　```git config --global user.name "ユーザー名"```

 メールアドレスの設定　```git config --global user.email "メールアドレス"```

設定内容の確認　```git config --global --list```

# GitHubでプルリクエストを発行する手順
1. GitHubで新しいリポジトリを作成します。

2. ローカルマシンに対してクローンを作成するために、コマンドプロンプトを開き```git clone [リポジトリのURL]```を実行します。

3. ```cd [リポジトリ名]```[^1]を実行し、クローンしたローカルリポジトリに移動します。そして、ブランチを作成するために```git checkout -b [ブランチ名]```を実行します。

4. ```notepad lecture02.md```のようにコマンドを実行すると、テキストエディタが起動するので、ファイルに情報を書き込んで保存します。今回は、Windowsのメモ帳を使用するので```notepad```になります。 ```lecture02.md```はファイル名です。任意の名前を付けてください。

5. ローカルリポジトリの変更を宣言するためのコマンド```git add lecture02.md```を実行します。

6. ローカルリポジトリの変更を決定するためのコマンド```git commit -m "Added my learning in lecture02.md"```を実行します。```"Added my learning in lecture02.md"```の部分はこのコミットが何の目的で変更されたのかを書く説明書きの部分です。

7. リモートリポジトリにプッシュするためのコマンド```git push origin lecture02``` を実行します。

8. GitHubのリポジトリのページから「Pull requests」タブ、「New Pull Request」ボタンをクリックします。ブランチの選択では、今回lecture02ブランチを使用したいので「lecture02」を選択します。「Create Pull Request」をクリックするとプルリクエストが完成します。

[^1]: リポジトリのURLがhttps://github.com/Hidetaka-Konishi/kadai_3.gitだった場合のリポジトリ名はkadai_3になる
