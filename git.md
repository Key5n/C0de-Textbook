---
marp: true
paginate: true
theme: c0de
math: katex
---

<!-- _class: lead -->

![w:400 bg left:33%](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)

# Git 入門

<!-- footer: ![w:50px](https://raw.githubusercontent.com/Key5n/C0de-Textbook/be03930d45cccc0d2fd46304746f837c318975ff/images/logo_C0de.svg) 名古屋工業大学プログラミング部 C0de -->

---

<!-- _class: image-one -->

<!-- _header: Gitとは -->

# プログラムの履歴の記録

![w:500px](https://raw.githubusercontent.com/Key5n/C0de-Textbook/Key5n/content/images/version-management.png)

### できること

- ファイル履歴をスマートに管理すること
  - 右のような例をなくすことができる
- 昔のバージョンに戻る
  - 「この実装だめだわ:sob:。戻ろ」
- スマートな共同開発
  - ファイルを送りあったりしなくてよい

---

<!-- _class: image-one -->

<!-- _header: Gitとは -->

![](https://raw.githubusercontent.com/Key5n/C0de-Textbook/Key5n/content/images/linus.png)

- フィンランド出身のプログラマ  
  Linus が Linux カーネル開発のために作った分散型ソースコード管理システム

---

<!-- _class: lead -->

![w:400 bg left:33%](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)

# コマンド

---

<!-- _header: 使用頻度ランキング（私見） -->

1. add, commit
1. status
1. push
1. init, log
1. clone
1. rm, mv
1. revert, stash, diff
1. reset
1. merge
1. branch, checkout

---

<!-- _header: 基本的な流れ1/2 -->

<!-- _class: image-one -->

![w:400](https://github.com/Key5n/C0de-Textbook/blob/Key5n/content/images/git-worktree-and-index.png?raw=true)

1. git init でローカルリポジトリの初期化
1. git add で作業ファイルの変更をインデックスに追加
1. git commit でローカルリポジトリにコミット
1. git push でリモートリポジトリにプッシュ

---

<!-- _header: 基本的な流れ2/2 -->

![w:700](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.amazonaws.com%2F0%2F284567%2Fc6162ef3-ab22-7062-d9f3-707d999a1a2a.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&w=1400&fit=max&s=2b954ddf8c5c32d79f1bee05762e4321)

---

<!-- _header: git init -->

# リポジトリの新規作成

- `.git`フォルダが作成される
- 注意
  - `.github/`と`.git/`は異なるもの
  - `git clone`した場合は必要ない

---

<!-- _header: git add -->
<!-- _class: image-one -->

![w:400](https://github.com/Key5n/C0de-Textbook/blob/Key5n/content/images/git-worktree-and-index.png?raw=true)

# ファイルのステージ(stage)

- 使い方
  - git add .zshrc
  - git add \*.c
  - git add images(ディレクトリ名)

---

<!-- _header: git commit -->

<!-- _class: image-one -->

![w:400](https://github.com/Key5n/C0de-Textbook/blob/Key5n/content/images/git-worktree-and-index.png?raw=true)

# ローカルリポジトリへのファイルのコミット

- 使い方
  - git commit -m "fix: fixed typo"
  - git commit --verbose
- git commit だけだと変な画面:smile:に遷移

---

<!-- _header: git status -->

# 状況の表示

- 使い方
  - git status
- エイリアスを登録しておこう

---

<!-- _header: git commit -->

<!-- _class: image-one -->

![w:500](https://github.com/Key5n/C0de-Textbook/blob/Key5n/content/images/git-diff.png?raw=true)

# git commit --verbose を使え

理由

- git commit --verbose は現在のインデックスと前回コミットの差を表示してくれるから
- 何も設定しないと Vim の画面が表示:blush:
- エイリアス`gc`を追加
- `git config --global commit.verbose true`でも可

---

<!-- _header: コミットメッセージの書き方 -->

# 未来の開発者がわかりやすいように書く

例

- docs: ○○ を追記
- fix: ○○ のバグを直した
- chore: ワークフローを書き直した
- feat: ○○ を実装

[参考](https://zenn.dev/itosho/articles/git-commit-message-2023)

---

<!-- _header: 問題1 -->

# ローカルリポジトリにコミット

1. 自分でリポジトリを作る(init)
1. README.md に何か書く
1. ステージングする
1. コミットする

---

<!-- _header: git log -->

# コミット履歴の閲覧

- 使い方
  - git log
  - git log --graph
    - 履歴をグラフ化してくれる
    - 現在のブランチの履歴のみ
    - GUI ソフトが必要？git log --graph --all で充分だよなぁ！？
  - git log --graph --all
    - すべてのブランチのコミット履歴をグラフとして表示

---

<!-- _header: コミットを取り消す1 -->

# git revert

- 正しくは「取り消したいコミットを打ち消すようなコミットを新しく生成する」
- マージコミットを取り消したいときは別
  - `git revert -m [1|2] <commit>`

---

<!-- _header: コミットを取り消す2 -->

# git reset

- git reset --soft

  - HEAD を指定したコミットにリセット
  - インデックスとワークツリーは無変化

- git reset --mixed

  - デフォルト
  - インデックスをリセット

- git reset --hard
  - インデックスとワークツリーをリセット
  - コミットしてない変更が消える

---

<!-- _header: 問題2 -->

# 新しくコミットしてそれを打ち消す

1. 新しく何かコミットする
1. ログで確認
1. それを打ち消す
1. ログで確認

---

<!-- _header: 演習問題3 -->

# リモートリポジトリへの追加

1.Github 上でリポジトリの作成

1. git remote -v で現在のリモートリポジトリの確認
1. git remote add origin \<url\>
1. git remote -v でリモートリポジトリが追加されていることの確認
1. git push origin \<今のブランチ名\>
1. Github 上でいろいろ見てみよう
   - コミット履歴
   - コミットメッセージ

---

<!-- _header: ブランチ -->

<!-- _class: image-one -->

# コミットに付いたラベル(ポインタ)

- ブランチの切り方

  - git switch -c hoge
  - git checkout -b

- ブランチの移動の仕方
  - git switch hoge
  - git checkout hoge

![w:500](https://github.com/Key5n/C0de-Textbook/blob/Key5n/content/images/git-branch.png?raw=true)

---

<!-- _header: コンフリクト解消 -->

<!-- _class: src -->

```
<<<<<<< HEAD
(今自分がチェックアウトしているブランチでの変更)
=======
（取りこもうとしたブランチでの変更）
>>>>>>>
```

マージしようとしたものがコンフリクトしているとこのように書き込まれる

解消には

- この\<や\>を消しつつ内容を正しいものに
  修正する
- ステージングする
- コミットする

VSCode 上でコンフリクト解消可能

---

<!-- _header: 問題4 -->

<!-- _class: image-one -->

![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.amazonaws.com%2F0%2F284567%2Fc6162ef3-ab22-7062-d9f3-707d999a1a2a.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&w=1400&fit=max&s=2b954ddf8c5c32d79f1bee05762e4321)

# フォークしてクローンして PR を出そう

1. Github 上でフォークする
1. git clone \<url\>
1. 何かしらのブランチを切る
1. 変更を加える
1. 自分のリポジトリにプッシュする
1. PR を出す

---

<!-- _header: 問題5 -->

# コンフリクトしてみよう

1. ローカルリポジトリとリモートリポジトリの内容を同期
1. ローカルの内容をいじる
1. その内容でコミットする
1. git pull でリモートから引っ張ってくる
1. コンフリクトするはず

---

<!-- _header: .gitignore -->

# 管理したくないものをリストアップ

- 例：\*.local.env
  - API キーの墓場

## 注意

一度ステージングしてしまったものを後から`.gitignore`に追加しても意味がない

- git rm --cached hoge

---

<!-- _header: 今日紹介しないけどこんなものもあるよ -->

## git diff

- コミット前にどんな変更があるか確認したい解き

## git stash

- やべ、この develop ブランチで作業するつもりが main ブランチで作業してたという時
