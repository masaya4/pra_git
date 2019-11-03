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
- git diff [HEAD] 
    ワークツリーとステージングとの変更差分を見れる。
    HEADを付けるとステージングとローカルリポジトリとの変更差分。
- GitHub使い方
    - 行を選択したURLを生成できる
    - ソースをコピーしたい時はRawを使う
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

