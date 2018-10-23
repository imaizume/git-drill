# 演習問題の使い方

この問題集には、各ページに例題と演習問題があります。
例題で操作のパターンをつかんでもらい、演習問題でより汎用的な操作に慣れることができるように書いています。

両者とも、[公式のGitHub](https://github.com/git-drill)にてたたき台となるリポジトリを用意していますので `git clone` でダウンロードしてください。
途中で間違えたら、リポジトリを削除して再度 `git clone` することで、何度でも最初からやりなおすことができます。

## gitの初期設定

gitをインストール後、演習を行う前に最低限必要な項目をgitに設定します。
これは演習問題を解くだけでなく問題のリポジトリをダウンロードするためにも必要です。
よくわからなければコピーペーストでも構わないので、やっておくようにします。
([gitの公式マニュアル](https://git-scm.com/book/ja/v1/%E4%BD%BF%E3%81%84%E5%A7%8B%E3%82%81%E3%82%8B-%E6%9C%80%E5%88%9D%E3%81%AEGit%E3%81%AE%E6%A7%8B%E6%88%90#%E5%80%8B%E4%BA%BA%E3%81%AE%E8%AD%98%E5%88%A5%E6%83%85%E5%A0%B1)にも同様の解説が載っています。)


1. macであれば「ターミナル」 windowsであれば「コマンドプロンプト」を開きます。
1. 立ち上がった画面 `git` と入力してEnterを押した後 "usage: git..." に続く長いメッセージが出力されることを確認。
1. "bash: command not found: git" と出力された場合は、gitのインストールが完了していないか失敗している可能性がありますので、詳しい人にヘルプを求めてください。
1. 次の2つの項目を実行します。日本語の部分は自分のステータスに合わせて変えても構いませんが、よくわからなければ次のサンプルをコピーペーストしてください、実在するかどうかは関係ありませんので好きな値を設定してください。
  - `git config --global user.name "(あなたの名前)"`
  - `git config --global user.email "(あなたのメールアドレス)"`
1. 上記設定コマンドのサンプル
  - `git config --global user.name "Git Learner"`
  - `git config --global user.email gitlearner@example.com`

設定は以上です、特に何も出力されない場合も設定は完了しているので大丈夫です。

{% youtube src="https://youtu.be/gCkPZ5EVU5g" %}{% endyoutube %}

## リポジトリをダウンロードする方法

上記の設定ができたら、問題のリポジトリをダウンロードしましょう。
以下ではデスクトップフォルダ(mac/linuxは `~/Desktop` windowsは `%homepath%\Desktop`)にダウンロードする想定で説明しています。

1. 問題のページにあるリンクから、git-drillのリポジトリへ移動。
1. 右上の "Clone or Download" を選択。
1. "Clone with HTTPS" (GitHubにログインしていてかつsshによるダウンロードができる場合はsshでも可)と表示されるのを確認し、テキストエリア内のURL(`https://github.com/git-drill/XXX.git`)をコピー。
1. ダウンロードしたZIPを解凍。
1. ターミナルアプリを開く。
1. `cd ~/Desktop` (mac/linux) または `cd %hommepath%\Desktop` (windows) を入力してEnterすることで、ターミナル内でデスクトップフォルダに移動する。
1. `git clone (先程コピーしたURL)` を入力してEnter、リポジトリが手元にコピーされる。デスクトップにも新しいフォルダができたことを確認。
1. `cd (リポジトリのフォルダ名)` または `cd ` (cdの後に半角スペースを1つ) の状態で上記で確認したフォルダのアイコンをターミナル内にドラッグ&ドロップ後、Enterする。
1. ターミナル上で演習を開始することができます。

{% youtube src="https://youtu.be/gCkPZ5EVU5g" %}{% endyoutube %}

