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
使用するHTMLファイルからCSSファイルまでのパスを記述して読み込みます。
```
<link rel="stylesheet" href="css/style.css">
```

## セレクタについて（CSSを設定する要素の取得方法）

### ユニバーサルセレクタ
全ての要素に対して、装飾がかかります。
```
*{
  margin:0px;
  padding:0px;
}
```

### 子孫セレクタ
こちらの例だと、sectionタグの中のpタグに装飾がかかります。
```
section p{
  color:limegreen;
}
```

### IDセレクタ
こちらの例だと、idがtargetのタグに装飾がかかります。<br>
```
<p id="target">ここに文章</p>

#target{
  background-color:skyblue;
}
```

### classセレクタ
こちらの例だと、classがstrongのタグに装飾がかかります。<br>
```
<p class="strong">ここに文章</p>

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

### リンク擬似クラス
hover状態の時などの少し特殊な指定方法です。
```
ul li a:hover{
  color:pink;
  font-size:36px;
}

参考:[CSS] 疑似クラス一覧
https://pasomaki.com/css-pseudo_class/
```


<!--
# セレクタと獲得ポイント (classよりidが優先される)
CSSでセレクタ を指定する際、指定したセレクタ に獲得ポイントというものが与えられます。特に表示に影響するものではなく、CSSの優先順位を決定づけるものになります。

```
以下セレクタ の種類毎の獲得ポイントです。

ユニバーサルセレクタ ：0ポイント
要素名セレクタ ：1ポイント
擬似要素：1ポイント　※「要素名::before」や「要素名::after」など
class名セレクタ ：10ポイント
id名セレクタ ：100ポイント

上の考え方で計算をするため、例えばid名testというp要素に命令を出すと以下のようになります。

P { color：#000 }・・・1ポイント
#test { color：#f00 }・・・100ポイント

同じ要素に異なるセレクタ で命令を出していますが、よりポイントの高いid名セレクタ の指定が優先されます。
```
-->
<!--
デベロッパーツールの使い方<br>
https://saruwakakun.com/html-css/basic/chrome-dev-tool
-->

<!--
# ボックスモデル
```
<h1>ボックスモデルについて</h1>
<section>
    <div class=“boxA”>ボックスA</div>
    <div class=“boxB”>ボックスB</div>
</section>


.boxA{
  background-color:tomato;
  width:200px;
  height:200px;
  padding:20px; /* 内側の余白詰め物*/
  border:10px;
  margin-bottom:40px; /* 強い方が勝つ */
}

.boxB{
  width:200px;
  height:200px;
  padding:20px;
  box-sizing:border-box;
  background-color:skyblue;
}
```

-->
# marginとpaddingについて
全ての要素は表示領域とその境界線、余白があり、この3つを合わせた領域のことをボックスと呼びます。<br>
内側と外側は余白をとることができ、ボーダー内側の余白をpadding、外側の余白をmarginと呼びます。<br>


<img src="boxmodel.png" width="400px">

```
<h1>marginとpaddingについて</h1>
<section>
    <div class=“boxA”>ボックスA</div>
    <div class=“boxB”>ボックスB</div>
</section>

```

```
.boxA{
  width:200px;
  height:200px;
  padding:20px;
  background-color:skyblue;
}

.boxB{
  width:200px;
  height:200px;
  margin:20px;
  background-color:red;
}

```

### 角丸の表現
ブロック要素の角を丸くすることができます。 
正円の半径の大きさを使って、円弧をベースにした角丸を実装できます。 <br>
参考：https://www.webcreatorbox.com/tech/border-radius

<img src="circle.png" width="200px">

```


以下のように書くことで、4角の角丸のサイズを一括で設定ができます。 
border-radius:サイズ;

/* border-radius: 30px; */
border-radius: 50%;   など


.boxA {
    background-color: pink;
    width: 300px;
    height: 300px;
    border-radius: 50%;
    text-align: center;
    line-height: 300px;
}

    

以下のプロパティ名で四隅の角丸の大きさをそれぞれ個別に設定することも可能です。

border-top-left-radius
border-top-right-radius
border-bottom-right-radius
border-bottom-left-radius

```


# 背景画像(background-image)の表示方法（よく使います！）

html
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    
    <!-- ここ！ -->
    <link rel="stylesheet" href="css/style.css">
    
    <div class="target"></div>
    
</head>
<body>
    
</body>
</html>
```

css
```
*{
    padding: 0;
    margin: 0;
}
h1{
    color:red;
    width:100%;
    height:100vh;
}

body{
    width: 100vw;   /*vw デバイスサイズに対して*/
    height: 100vh;    
    background-image:url(../images/sora.jpg);
    background-size: cover;
    background-repeat: no-repeat;
}

.target{
    width: 200px;
    height: 200vh;    
    background-image:url(../images/sora.jpg);
    background-size: cover;
    background-repeat: no-repeat;
}

```
CSSのbackground-sizeで背景画像サイズを設定する方法を徹底解説!!<br>
https://www.sejuku.net/blog/83148

# リセットCSS（ブラウザの初期cssをリセット）
リセットCSSとは、ブラウザによって異なるデフォルトのCSSを打ち消して、<br>
ブラウザ間の表示を揃えるためのCSSのことをいいます。
```
/* 簡易リセットcss */
*{
  margin:0px;
  padding:0px;
  box-sizeing:border-box;
}
```
2020年リセットCSS <br>
https://webdesign-trends.net/entry/8137




## 練習問題(よくあるパーツを作ってみましょう！)

<img src="img/mondai1.png" width="600px">

<br>
答えのURL:

<!--
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="css/style.css">
    <title>Document</title>
</head>
<body>

    <h1>よくあるパーツを作ってみよう！</h1>

    <div id="box1">
        <h2>01:よくある見出しとテキストブロック</h2>
        <p>テキストテキストテキストテキストテキスト
            テキストテキストテキストテキストテキスト
        </p>
    </div>


    <a id="btn" href="#">ボタン</a>
    
</body>
</html>

```

```

/* リセットcss */

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body{
    padding: 50px;
}

h1{
    margin-bottom: 50px;
}


/* 問い1 */
#box1{
    width: 500px;
    padding: 20px;
    border: 2px solid #333;
    margin-bottom: 100px;
}

#box1 h2{
    border-left: 10px solid red;
    padding-left: 20px;
}

#box1 p{
    color: #333;
    font-size: 14px;
    line-height: 1.5;
}



/* 遠いに*/

#btn{
    display: block;
    width: 200px;
    padding: 20px;
    background:aquamarine;
    color: #333;
    border-radius: 20px;
    text-align: center;
    text-decoration: none;
}


```


-->


<!--
html
```

<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>パーツ制作課題</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <h1>パーツ制作課題</h1>

    <section id="koumoku01" class="parts01">
        <h2>01：見出しとテキストのパーツ</h2>
        <p>テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキスト</p>
    </section>

    <section id="koumoku02" class="parts02">
        <h2>02：ボタンの制作</h2>
        <p><a href="">ボタン</a></p>
    </section>
    
</body>
</html>
```

css
```
* {
    margin: 0;
    padding: 0;
}

h1 {
    color: #f00;
}

section {
    margin: 40px;
}

.parts01 {
    border: solid 4px #444 ;
    width: 500px;
    padding: 20px;
    box-sizing: border-box;
}

.parts01 h2 {
    border-left: solid 8px #f00 ;
    padding-left: 12px;
    margin-bottom: 12px;
}

.parts02 p a {
    background-color: skyblue;
    display: block;
    width: 140px;
    height: 40px;
    text-align: center;
    line-height: 40px;
    text-decoration: none;
    color: #00f;
    border-radius: 20px;
    transition: 1s;
}

.parts02 p a:hover {
    background-color: pink;
    color: #f00;
}

.parts03 {
    background-color: #ccc;
    width: 500px;
    height: 300px;
    padding-top: 12px;
    background-image: url(../images/sora.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
}

.parts03 h2 {
    /* background-color: #444; */
    background-color: rgba(0,0,0, 0.5);
    color: #fff;
}
```
-->


# その他の表現

### グラデーション

<img src="img/gradation.png" width="300px">

```
参考：https://saruwakakun.com/html-css/basic/linear-radial-gradient 

線形の例：
background: linear-gradient(方向, 開始色, 終了色);
background: linear-gradient(to right, #FFC778, #FFF);

円形の例:
background: radial-gradient(中央の色, 外側の色); 
background: radial-gradient(#F13F79 20%, #FFC778 70%); 

.boxB {
    background: linear-gradient(to right, #1E90FF, #FFF);
    width: 400px;
    height: 300px;
}

```



### 影
ボックスシャドウ<br>
参考: https://saruwakakun.com/html-css/basic/box-shadow 

<img src="img/box-shadow.png" width="300px">

```
box-shadow: 左右の向きpx  上下の向きpx ぼかしpx 広がりpx 色 内側指定;
例 .box {box-shadow: 2px 2px 4px -2px gray inset}

.boxC {
    width: 400px;
    height: 300px;
    background-color: skyblue;
    box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.3);
}


```

## フォント系の指定
```

/* 
フォントファミリーの指定
上から順番に継承していく */
body {
  font-family: "Helvetica Neue",
    Arial,
    "Hiragino Kaku Gothic ProN",
    "Hiragino Sans",
    Meiryo,
    sans-serif;
}



.boxD p{
    color:red; // 色の指定
    font-size: 20px; // サイズ
    font-size: 2em; // サイズ
    font-style: italic; // 斜め
    font-weight: bold; 太字
    line-height: 1.5; 　// 行間
    letter-spacing: 0.2em; 
 }
 
近年の流れはfont-sizeはremで指定することもある
html {
    /* 1rem = 10px相当 */
    font-size: 62.5%;
}
に設定して
p{
    font-size:1.5rem;  // のように指定するのが主流
}
```

【2021年版】font-familyの正しい指定方法・タイプ別おすすめフォント設定例<br>
https://willcloud.jp/knowhow/font-family/
<br>

css letter-spacingで字間を調整する方法まとめ<br>
https://saruwakakun.com/html-css/reference/letter-spacing

<br>
line-heightで行間を調整する方法：おすすめの値は？ <br>
https://saruwakakun.com/html-css/reference/line-height



### line-heightの図解
line-height 40pxの場合
<img src="img/line-height-1.jpg" width="300px">



## webフォントについて
https://saruwakakun.com/html-css/basic/google-fonts <br>


```
こちらがまとまっています。
https://saruwakakun.com/html-css/basic/google-fonts

webフォントが表示されるまでのサーバーの仕組み: https://www.asobou.co.jp/blog/web/webfont
```
