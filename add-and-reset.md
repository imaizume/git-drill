# add & reset | 差分のステージとアンステージ


// TODO: 概念図

## 難易度: :star:

## 概要

- `git add FILE` で次のコミットにFILEの差分を含める (ステージ)
- `git reset` で次のコミットに含める差分をクリアする (アンステージ)
- `git reset FILE` で次のコミットからFILEの差分を除外する (アンステージ)

## 例題 (リポジトリ: [git-drill/add-and-reset](https://github.com/git-drill/add-and-reset))

- :computer: [`index.html`](url) の内容に変更を加えた。
  - :white_check_mark: `index.2.html` を `index.html` にコピー(上書き)
- :computer: [`style.css`](url) の内容に変更を加えた。
  - :white_check_mark: `style.2.html` を `style.css` にコピー(上書き)
- :octocat: `index.html`の変更をステージせよ
- :octocat: `index.html`の変更をアンステージせよ
- :octocat: `index.html`と`style.css`の変更をステージせよ
- :octocat: `index.html`と`style.css`の変更をアンステージせよ

## 例題回答

{% youtube src="" %}{% endyoutube %}

- `git add index.html` で`index.html`をステージ
- `git reset index.html`で`index.html`のみをアンステージ
- git add *` で`index.html`と`style.css`をステージ (`git add index.html style.css`でも同じ)
- git reset` で`index.html`と`style.css`をアンステージ (`git reset index.html style.css`でも同じ)

## 例題解説

**`git add`コマンドは、、次のコミットに変更差分を含めるようgitに指示するためのコマンドです。**
詳しくは[add & commit](add-and-commit.md)をご覧ください。

しかし**誤って`git add`をした場合に、操作を取り消す(= 次のコミットに含める差分をクリアする)必要が生じる場合があります。**
**そのためのコマンドが`git reset`です。**

