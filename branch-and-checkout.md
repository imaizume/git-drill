# branch & checkout | ブランチを作る

## 難易度 :star:

ブランチは

## 概要

- `git branch` でブランチの一覧を表示する
- `git branch (ブランチ名)` でブランチを作成する
  - 例えば `git branch develop` で `develop` という名前のブランチを作成する
  - 現在のブランチを `develop` に切り替えるには別途 `git checkout` コマンドが必要 (`git checkout develop`)
- `git branch -d (ブランチ名)` でブランチを削除する
  - ただし現在自分がいる(`git checktout` した)ブランチを消すことはできない

## 例題 (リポジトリ: [git-drill/branch-and-checkout](https://github.com/git-drill/branch-and-checkout))

TODO: 例題リポジトリのブランチ図を入れる

- :mag: 現在 `master` ブランチ上にいる
- :octocat: `develop` ブランチが存在することを確認してチェックアウトせよ
- :octocat: 次に `develop` ブランチ上で新たなブランチ `my-branch` を作成しチェックアウトせよ
- :octocat: また `my-branch` 上では `my-branch` が消せないことを確かめよ
- :octocat: 最後に `useless` ブランチが存在することを確認して削除せよ

## 例題回答

1. `git status` - 表示されるメッセージの最初の行が"On bracnh master"となっていることを確認。
2. `git branch` - ブランチ一覧の中に `develop` が表示されているのを確認。
3. `git checkout develop` - 現在のブランチを `develop` ブランチに変更。
4. `git branch my-branch` - 新しいブランチ `my-branch` を作成。
5. `git checkout my-branch` - 現在のブランチを `my-branch` に変更。
6. `git branch -d my-branch` - `my-branch` の削除をしようとするが失敗(error: Cannot delete branch 'my-branch')。
7. `git branch` - ブランチ一覧の中に `useless` が表示されているのを確認。
8. `git branch -d uselss` - `useless` の削除に成功(Deleted branch useless)。

## 例題解説

1. 現在の自分の状態を確認するには `git status` を使います。慣れないうちは、操作の合間にこまめに自分の状態を確認するようにしましょう。
2. メッセージが複数行表示されますが、最初の行のみに着目すれば大丈夫です。"On branch master"(master上にいる)というメッセージを確認します。
3. `master` ブランチから `develop` ブランチに切り替えます。続けて `git status` を実行すると"On branch develop"が表示されることが確認できます。
4. `git branch my-branch` で `my-branch` ブランチが作成されます。ただし現在のブランチは `develop` のままです。
5. 先程作った `my-branch` に移動します。
6. 現在のブランチ `my-branch` を消すことはできません。`my-branch` 以外のブランチに移動しないと消すことはできませんが例題では削除しません。
7. 代わりに `useless` ブランチを削除します。これは自分がいるブランチではないので削除可能なはずです。
8. `useless` を削除することができました。同じ要領で `develop` や `master` も削除可能です。

## 演習

TODO

