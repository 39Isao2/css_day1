# 03:CSS（基本、装飾編）
## CSS（Cascading Style Sheets） 
HTMLと同様にWeb制作の中で用いられる言語の一つがこのCSS(Cascading Style Sheets)です。 <br>
HTMLに「文書を作成する」という役割があったように、 <br>
CSSには「装飾（デザイン）の指定をする」という役割が存在します。 <br>
<br>
HTMLとCSSをリンクさせることによって、CSSの指示内容がHTMLに反映されます。 <br>
Web言語は言語ごとに役割があり、いくつかの言語を組み合わせてWebページを作るのが一般的な制作手法となります。 <br>

## セレクタ、プロパティ、値

```

h1{
    color:red;
}

セレクタ { 
    プロパティ: 値；
}

どこの { 
    なにを : どうする；
}

```

### CSSファイルのリンク方法
```
<link rel="stylesheet" href="css/style.css">
```

### ユニバーサルセレクタ
```
*{
  margin:0px;
  padding:0px;
}
```

### 子孫セレクタ
```
section p{
  color:limegreen;
}
```

### IDセレクタ
```
#koumoku02{
  background-color:skyblue;
}
```

### classセレクタ
```
.strong{
    color:pink;
    font-size:36px;
    font-weight:bold;
}

.line{
    text-decoration:underline;
}

/* 数字始まりはダメ */
/* 2個以上、指定可能 */
<p class="strong line">ライン</p>
```

## よくあるパーツを作ってみよう！
