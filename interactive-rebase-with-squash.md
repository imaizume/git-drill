# rebase --interactive (squash/re-order) | 複数のcommitを1つにまとめる/順序を入れ替える (★★★)

## 概要

- `git rebase -i (--interactive)` でコミットログの編集ができる
- ログ編集画面でリストの先頭を `squash` に書き換えるとその前のコミットと統合される
- リストの順序を入れ替えるとコミットの順序が入れ替わる

## 例題 (リポジトリ: [git-drill/add-patch](https://github.com/git-drill/add-patch))

1. :octocat: `index.html` の過去3回のcommitの順序を入れ替えよ
2. :octocat: 任意のcommit複数個を1つのcommitに統合せよ

(1の後に2を実行すること)

## 例題回答1

1. `git rebase -i HEAD~3`
2.  vim画面で先頭が以下の表示になっていることを確認
    ```
    pick 569b19b ページタイトルを変更
    pick 4b4359c コンテンツ(前半)を変更
    pick 6072288 コンテンツ(後半)を変更
    ```
3. (直近の2コミットの順序を入れ替える場合) vim画面で1行目と2行目を入れ替えて保存
    ```
    pick 4b4359c コンテンツ(前半)を変更
    pick 569b19b ページタイトルを変更
    pick 6072288 コンテンツ(後半)を変更
    ```
4. `Successfully rebased and updated refs/heads/master.` が表示されていることを確認

## 例題回答2

1. `git rebase -i HEAD~3`
2.  vim画面で先頭が以下の表示になっていることを確認(コミットハッシュは実際と異なる場合があります)
    ```
    pick 4b4359c コンテンツ(前半)を変更
    pick 569b19b ページタイトルを変更
    pick 6072288 コンテンツ(後半)を変更
    ```
3. (3コミットを統合する場合) vim画面で2行目と3行目の行頭を `squash` に書き換えて保存
    ```
    pick 4b4359c コンテンツ(前半)を変更
    squash 569b19b ページタイトルを変更
    squash 6072288 コンテンツ(後半)を変更
    ```
4. 任意のコミットメッセージを入力して保存
5. `git log --oneline` で統合されたcommitができていることを確認

## 演習

TODO

