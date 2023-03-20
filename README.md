# What's this?

部活で後輩に Git を説明するために作った資料です．  
資料は marp で作られています．

# Note

CI は Github actions により実現されています．
`git.pdf`以外のファイルが変更された状態で push されると自動で`git.pdf`ファイルや`git.[0-9]+.png`が`git.md`ファイルより生成されます．

# About theme

@Key5n が公式テーマ`gaia`を継承しつつ独自にテーマを作りました．  
その思想は以下です．

1. スライドに`<!-- _class: src -->`が適用された場合，ソースコードは画面右 40%を占めるように設定
   ![ソースコード貼り付けの例](https://github.com/Key5n/C0de-Textbook/blob/Key5n/main/git.004.png?raw=true)
   - このとき本文は画面左 60%を占めるように設定
1. スライドに`<1-- _class: img -->`が適用された場合，画像を右寄りに設定
   ![画像貼り付けの例](https://github.com/Key5n/C0de-Textbook/blob/Key5n/main/git.003.png?raw=true)
   - `float: right`により設定しているので文字は画像を回り込むようになっています
   - note: 画像 2 枚を比較したいときはこのクラスを使用しないでください．どちらの画像も右寄りになってしまいます

## 今後実装したいもの

1. 画像を 2 枚を比較しやすいようにする
1. ソースコードを 2 つを比較しやすいようにする

# To Do

1. Github actions の実行の遅さをなんとかする
   - npx を使用しているため毎回パッケージをロードしている．これをなんとかしたい．  
      想定解決策 ↓
     1. Docker
     1. Github actions の cache
1. png 画像をいずれかのフォルダの下に出力されるようにしたい
   - 少し docs 見てもわからなかったため一旦放置

# Contribute

本番ブランチ：`main`  
@Key5n の本番用の作業ブランチ：`Key5n/main`  
@Key5n の markdown の編集用のブランチ：`Key5n/content`

# Agenda

1. 資料の方向性
   (e.g. 詳細に，最短で 6 割方使えるように，例題を加える)
2. 役割分担
3. 資料作りの作業日
   (e.g. ○ 〇日の〇〇時)
4. 取り扱う内容の選別
   (e.g. 環境構築，add, commit, diff, branch, push をやって stash をやらない)
5. 演習問題

# 資料の方向性

Git とその周り（コマンドライン，VSCode）の導入

1. Github Desktop による GUI でまず説明する
2. 環境構築
3. CUI に入る

# 資料作りの作業日

今日，明日

# 取り扱う内容の選別

## GUI

- [ ] Github Desktop

## コマンドライン

- [ ] add
- [ ] commit
- [ ] log
- [ ] diff
- [ ] branch
- [ ] push
- [ ] checkout
- [ ] clone
- [ ] stash
- [ ] switch
- [ ] reset
- [ ] merge
- [ ] rm
- [ ] revert

# 役割分担

# 演習問題

1. 環境構築
1. ローカルリポジトリにコミット
1. ステージングしてしまったものを元に戻す
1. コミットしたものを戻す
1. リモートリポジトリにプッシュ
1. ブランチ作成
1. マージ
1. コンフリクト解消
1. クローンして PR を送りつける
1. PR にコメント・レビューしてみる
1. gitignore

## 環境構築

何かのサイトを参考にする

- WSL の入れ方

## ローカルリポジトリにコミット

- add とコミットの使い方
- コミットメッセージの書き方
- verbose

## ステージングしてしまったものを元に戻す

- restore

## コミットしたものを戻す

- revert

## リモートリポジトリにプッシュ

- push

## ブランチ作成

- branch
- checkout
- switch

## マージ

- merge

## コンフリクト解消

- VSCode でコンフリクト解消

## クローンして PR を送り付ける

- clone
- push

## PR にコメント・レビューしてみる

- Github web

## gitignore

- 一度上げたものを削除する

# 拡張機能

[Github Pull Request and Issues](https://github.com/gitkraken/vscode-gitlens)
[Github Repositories]
[Git Graph]
[GitLens]
