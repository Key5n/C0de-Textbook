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
