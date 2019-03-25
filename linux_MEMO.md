#Git学習メモ
##Gitコマンド

【英単語】
　modified 修正
　inable いない
  failed 失敗しました
  empty 空の
  fatal 致命的な
　initialized　初期化  

【ショートカット Visual studio code】
 ctrl + pgup 次のタブ
 ctrl + pgdn 次のタブ
 
 【linuxコマンド】
　find -name ファイルorディレトクリ名　ファイルおよびディレトクリを探す
　find -maxdepth 1 カレントディレトクリのみを検索する。1より大きく少なくしたら変わる  　
　history 使用したコマンドを一覧表示
　echo 文字　> ファイル名　ファイルに文字を入力する。上書き
　echo 文字　>> ファイル名　ファイルに文字を追記する。
　shift HOME　上部へスクロール


【git コマンド】

　git --version gitのバージョン確認
　git config --global user.name jun-hiratsuka ユーザー名を設定
  git config --list
　git config --global core.editor "code --wait" Visual Studio Codeをエディタに設定
　git config core.editor gitのエディタを確認
　git config --global user.name ユーザ名　globalにユーザ名を登録
　git config --global user.email  メールアドレス　globalにメールアドレスを設定  
　git config --global --unset 設定項目 Gitに登録した設定項目を削除(例:user.name)
  git config --global http.procy アドレス　gitの接続先プロキシサーバを設定(例:http://example.com:8080)プロキシサーバURLとポート番号を指定
  git config --global http.procy アドレス　gitの接続先プロキシサーバ認証が必要な場合(例:http://username:password@example.com:8080)プロキシのサーバ名:ﾊﾟｽﾜｰﾄﾞ@プロキシサーバーURL:ボード番号
  touch ファイル名　新規ファイルを作成
  git cp 変更前ファイル名 変更後ファイル名
  git mv 変更前ディレクトリ名　変更後ディレクトリ名
  git rm -r --ignore-unmatch  ディレクトリ名　 リポジトリ削除時、gitに登録してないファイルを削除す
　git -rf システムファイルを含むすべてを削除。禁断。　
  

ローカルリポジトリを作る
　　git init カレントディレクトリをリポジトリに変更する
ファイルの状態を確認
　　git status
ファイルを登録する
　　git add ファイル名
ファイルの差分を確認する
　　git diff ワークツリーとステージングエリアの差分を確認する。
　　git diff --cached ステージングエリアとGitディレクトリ(コミット先)の差分を確認する。
ワークツリーの変更を取り消す
    git checkout --取り消すファイル名
ステージングエリアへの登録を取り消す
　　git reset HEAD ファイル名　※HEADは最新のaddを消すという意味
コミットを取り消す
　　git reset --soft ワークツリーはそのままでコミットを消す
　　git reset --hard ワークツリーも含めてコミットを消す
ファイル削除
　　git rm 削除するファイル名

ディレクトリ削除
　　git rm -r 削除するディレクトリ名
ファイル・ディレトクリの移動
　　git mv 元のファイル、ディレトクリ 移動先のファイル、ディレクトリ
gitで管理しないファイルを設定
　　①.gitignoreファイルを作成(リポジトリ内に格納)
　　②.gitignore内にgitで管理しないファイル名を入力
　　➂git statusで管理しないファイル名が出力されないことを確認(直前に変更が必要だけど)
コミットのログ確認
　　git log

githubとの認証にSSH keyを生成する
　　①gitにコマンド入力し鍵(sshkey)を作成する
　　 コマンド:ssh-keygen -t rsa -b 4096 -C "メールアドレス"
    ②鍵の場所を確認する。(一応メモっとこう)
    ➂Enter passphraseと表示されたらsshのパスフレーズを入る
    ④Githubにパスフレーズを登録するためクリップボードにコピる
     windowsの場合 clip < /c/Users/ユーザディレトクリ/.ssh/id_rsa.pub
     macの場合     pbcopy < /Users/ユーザディレトクリ/.ssh/id_rsa.pub
    ➄Githubからsetting→SSH and GPG kyes→Lew SSH kyeを選択
    ⑥titleを入力→keyにペースト→Add SSH kye
    ➆gitで確認用コマンドを入力
    ssh -T git@github.com
    ⑧Hi～が表示されたら完了 
    
ブランチをリモートリポジトリに飛ばす
　　git push リモブランチ名　ローカルブランチ名

リモートリポジトリを追加する
　　git remote add origin git@github.com:jun-hiratsuka/linux_study.git

リモートリポジトリを確認する
　　git remote -v

pushのコマンド楽々化
   git push -u origin master 次回から git push だけで勝手に origin master で push してくれる。

変更ファイルをすべてステージングエリアに追加する
　 git add -A


git initを実施
リモートリポジトリを作成
1 コミット

リモートリポジトリ追加コマンドを追記。
2 コミット
