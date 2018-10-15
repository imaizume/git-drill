# add --patch | 行単位でaddする (★★★)

## 概要

- `git add` には `-p (--patch)` オプションが存在する
- `-p` を使うとファイルを行単位で `add` できる
- 1つのファイルを複数のcommitに分けることが可能

## 例題 (リポジトリ: [git-drill/add-patch](https://github.com/git-drill/add-patch))

[`index.html`](url) のL5,L8,L10の内容に変更を加えた。 [操作] `index.2.html` を `index.html` としてコピー(上書き)
L5,L8,L10のそれぞれを別のコミット、合計3つのコミットにしてください。

## 例題回答

1. `git add -p index.html`
2. _Stage this hunk_ で `s` を入力しEnter
3. 以下の表示がされていることを確認して `y` を入力しEnter

-  <title>Patch Add</title>
+  <title>Git Drill - Patch Add</title>

4. `q` を入力しEnter
5. git diff で以下の表示を確認

```
--- a/index.html
+++ b/index.html
@@ -5,9 +5,9 @@
   <title>Git Drill - Patch Add</title>
 </head>
 <body>
-  <p><code>git add --patch</code>すると行単位で<code>add</code>することができます。</p>
+  <p><code>git add --patch</code>または<code>git add -p</code>すると行単位で<code>add</code>することができます。</p>
   <p>なぜそうする必要があるのでしょうか?</p>
-  <p>それは1つのcommitを大きな変更の塊に分けるためです。</p>
+  <p>それは1つの変更を小さなcommitの塊に分けるためです。</p>
 </body>
 </html>
```

6. `git diff --staged` で以下の表示を確認

```
--- a/index.html
+++ b/index.html
@@ -2,7 +2,7 @@
 <html lang="en">
 <head>
   <meta charset="UTF-8">
-  <title>Patch Add</title>
+  <title>Git Drill - Patch Add</title>
 </head>
 <body>
   <p><code>git add --patch</code>すると行単位で<code>add</code>することができます。</p>
```

7. 任意のタイトルでgit commitする 例: `git commit -m "タイトルにサイト名を追加"`
8. 上記1~7をあと1回繰り返す (L8の差分のみをgit commitする)
9. 通常のgit commitでL10の差分をgit commitする
10. `git log --oneline` で新しい3つのcommitができていることを確認
11. `git show HEAD` から `git show HEAD~2` で1行差分のコミットとなっていることを確認

## 演習

TODO

