# merge --abort | mergeを中止する

## 難易度: :star:

## コマンドの概要

- merge中に問題が生じ、作業自体を取り消したい場合には --abort オプション付きで実行することでキャンセルが可能です。

## 例題 (リポジトリ: [git-drill/merge-abort](https://github.com/git-drill/merge-abort))

1. :mag: このリポジトリでは1つのテキストファイル(sample.md)が管理されています。
2. :mag: checkout直後はローカルではmasterブランチのみが参照可能です。
3. :octocat: リモートリポジトリにmasterとdevelopの2つのブランチが存在することを確認してください。
4. :octocat: masterブランチに以下のいずれかのブランチをmergeしてください。
  1. リモートのdevelopブランチ
  1. ローカルのdevelopブランチ (checkoutする必要があります)
5. :octocat: コンフリクトが発生しmergeが完了しないことを確認してからmerge自体を中止してください。

## 例題の模範回答

{% youtube src="" %}{% endyoutube %}

1. `git branch -a` で以下の表示を確認します。
  ```
  * master
    remotes/origin/develop
    remotes/origin/master
  ```
2. 現在のリポジトリの状態を確認します。
{%ace lang='sh'%}
git status
git log --all --graph --oneline
{%endace%}
3. 以下のいずれかを実行してmergeします
  1. リモートのdevelopブランチをmergeする場合
{%ace lang='sh'%}
git merge origin/develop
{%endace%}
  2. ローカルのdevelopブランチをmergeする場合
{%ace lang='sh'%}
git checkout -b develop origin/develop
git checkout master
git merge develop
{%endace%}
4. コンフリクトによりmerge作業が停止したことを確認します。
{%ace lang='sh'%}
  Auto-merging sample.txt
  CONFLICT (content): Merge conflict in sample.txt
  Automatic merge failed; fix conflicts and then commit the result.

  > git status

  On branch master
  Your branch is up to date with 'origin/master'.

  You have unmerged paths.
    (fix conflicts and run "git commit")
    (use "git merge --abort" to abort the merge)

  Unmerged paths:
    (use "git add <file>..." to mark resolution)

    both modified:   sample.txt

  no changes added to commit (use "git add" and/or "git commit -a")
{%endace%}
5. merge作業を中止するには以下を実行すれば完了です。
{%ace lang='sh'%}
git merge --abort
{%endace%}
6. merge作業前の状態と同じであることを確認します。
{%ace lang='sh'%}
git status
git log --all --graph --oneline
{%endace%}

## 例題の解説

1. `git branch` の `-a (--all)` オプションは、現在のブランチを含む全てのブランチを表示します。
1. 今回使用した `git log` の各オプションについて知りたい場合は、[こちらの課題]()を解いてみましょう。
1. checkout直後はmasterブランチのみが手元にある状態のため、developをマージするには以下のいずれかを実行する必要があります。
  - リモートのdevelopブランチをmasterへmergeするか、または
  - リモートのdevelopブランチをローカルにcheckoutしそれをmasterへmerge
1. mergeの途中で "CONFLICT (content): Merge conflict in ..." というメッセージは、2つの差分を自動的にmergeできなかったことを表します。今回はmergeを中止しますが、[コンフリクトを目視で確認し手動で統合することも可能]()です。中止する場合は `--abort` オプション付きでmergeコマンドを実行します。
1. merge前の状態に戻ります。なお複数ファイルがコンフリクトしていた場合や、手動でのマージ作業を途中まで行った場合でも、同様に中止可能です。

## 演習


