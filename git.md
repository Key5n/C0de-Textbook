---
marp: true
paginate: true
theme: c0de
math: katex
---

---

<!-- _class: lead -->

# Git 入門

![w:400 bg left:33%](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)

<!-- footer : ![w:50px](https://raw.githubusercontent.com/Key5n/C0de-Textbook/Key5n/content/images/logo_c0de.png) 名古屋工業大学プログラミング部 C0de -->

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

<!-- _class: src -->

<!-- _header: タイトル -->

```javascript
function helloWorld(const arg){
  return "Hello World";
}
const a = 1;
console.log(helloWorld(a));

const users = [
  {
    id: 1,
    name: Andrew
  },
  {
    id: 2,
    name: Anna
  }
]

```

# ソースコード

なんでやねん:sob:

「わぁ...」「泣いちゃった！」「ふーーーん」「ってコト！？」

---

<!-- _class: image-one -->

<!-- _header: Gitとは -->

![](https://raw.githubusercontent.com/Key5n/C0de-Textbook/Key5n/content/images/linus.png)

- フィンランド出身のプログラマ  
  Linus が Linux カーネル開発のために作った分散型ソースコード管理システム
  - じゃｋｌｓｄｊｆｌ
    - どっこいしょーどっこいしょーどっこいしょーどっこいショーソーランソーランソーランソーランどこいしょー

1. aid
   1.asdjf
1. asjdkf
1. ajsd
