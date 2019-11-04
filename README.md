# Udemy はじめてのGitとGithub 学習メモ

- git commit [-v, -m] 
    コミット時に変更差分が見れる。
- 1作業ずつcommitするのが原則
- わかりやすいコミットメッセージを書く
    - 1行目 変更内容の要約
    - 2行目 空行
    - 3行目 変更理由
- git log [-p, --oneline, -n 3] [ファイル名の指定]
    commit履歴が見れる。
- git status
    現在の状況を確認
- git diff [--staged] 
    ワークツリーとステージングとの変更差分を見れる。
    --stagedを付けるとステージングとローカルリポジトリとの変更差分。
- GitHub使い方
    - 行を選択したURLを生成できる
    - ソースをコピーしたい時はRawを使う
    - blame 誰がいつ変更したのかが見れる。
- .gitignore
    - #から始まる行はコメント
    - 指定したファイルを除外
        index.html
    - ルートディレクトリを指定
        /root.html
    - ディレクトリ以下を除外
        dir/
- コミットしたファイルをGit管理から外す
    - git rm [ファイル名]
        ファイルごとGit管理から削除
    - git rm -r [ディレクトリ名]
        ディレクトリごとGit管理から削除
    - git rm --cached [ファイル名]
        ファイルは残す場合
        .gitignoreに追記すること
- git rm で削除したファイルを復元する。
    git reset HEAD <ファイル名>
    git checkout <ファイル名>

# Udemy もう怖くないGit 学習メモ

- gitはスナップショットとして保存する為、変更差分を計算する必要がなく早い
- git add
    - ファイルの中身をハッシュ化して、ハッシュ値とファイルの内容をマッピングしたインデックスを作成する。
- git commit
    - ツリーの作成、ファイル構成を表す、スナップショットがわかる。
    - コミットの作成、ツリーへのポインターと作成者、日付、コミットメッセージ、親コミットを保存
- git mv <旧ファイル> <新ファイル>
    - 以下のコマンドと同じ
    > mv <旧ファイル> <新ファイル>   
    > git rm <旧ファイル> <新ファイル> 
    > git add <新ファイル>


ステージの情報を取ってきてワークツリーを上書きする。
- git checkout --<ファイル名>
- git checkout --<ディレクトリ名>
- git checkout --.

ステージした変更を取り消す。
- git reset HEAD <ファイル名>
- git reset HEAD <ディレクトリ名>
- git reset HEAD .
  今自分がいるブランチの最新のコミットの履歴でステージを上書きするよ。

直前のコミットをやり直す。
- git commit --amend
 リモートリポジトリにPushしたコミットはやり直してはいけない。
 別の誰かが取り込んでいた場合に不具合が生じる為
 
### リモートを表示する
- git remote
- git remote -v

### リモートから情報を取得する
    - git fetch <リモート名>
    - git fetch origin
     リモートリポジトリからローカルリポジトリにとってくる。ワークツリーには反映しない。
    - git merge origin/master でワークツリーに取り込む
    - git pull origin master で上記の2手順を一度にできる。
      git pull origin master はmasterブランチを現在のブランチに取り込む。現在のブランチをmasterブランチに取り込むのではない

### リモート詳細情報を表示する
    - git remote show origin

### リモートを変更・削除する
    - git remote rename <旧リモート名> <新リモート名>
    - git remote rm <リモート名>

### ブランチとは
- ブランチとはコミットを指し示したポインタ
- HEADとは今自分が作業しているブランチを指し示したポインタ
- commitするとブランチが指し示すコミットファイルが最新のものに変わる。

### ブランチを新規追加する
- `git branch <ブランチ名>`
 ブランチを作成するだけで切り替えは行わない。

### ブランチの一覧を表示する
- `git branch
- `git branch -a

### ブランチを切り替える
- `git checkout <既存ブランチ>`
- `git checkout -b <新ブランチ>`
 ブランチを新規作成して切り替える
 
