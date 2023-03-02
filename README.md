# Bootstrap導入サンプルサイト
[サイトを見る](https://npo-clack.github.io/bootstrap-sample/)

## このサンプル目的
cssをできるだけ書かずに整ったデザインを実装する！
HTMLにBootstrapで決められたclassをつけるだけでデザインが変わります。

※ 凝ったデザインを作りたい場合は自分でcssをたくさん書く必要があります。

### 目次
1.  Bootstrapの導入
2. よく使うやつ
 	1. レイアウト
	2. サイズ調整
	3. round
	4. icon
3. 例
	1. ナビゲーションバー
	2. ドロップダウンメニュー
	3. sns icon
	4. ジャンボトロン
	5. カード
4. 配色のアレンジ
 
## 1. Bootstrapの導入
### 読み込み
Bootstrapが作ったCSSやjavascriptを読み込むと、ルールに沿ってHTMLを書くだけで整ったデザインになります。

```html
<!DOCTYPE html>

<html lang="ja">
	<head>
		<meta charset="UTF-8">
		<title>My Home Page - Bootstrap</title>

		<!-- CSS -->
		<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

		<!-- Bootstrap icon用css -->
		<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.0/font/bootstrap-icons.css">
	
	</head>
	<body>
	
		<!-- なんか書く -->
		<!-- なんか書く -->
		<!-- なんか書く -->
		
		<!-- Bootstrap javascript -->
		<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
	</body>

</html>
```

css, js: https://getbootstrap.jp/docs/5.0/getting-started/introduction/
icon: https://icons.getbootstrap.jp/#使い方

### 基本的な使い方
[Bootstrap設置ガイド](https://bootstrap-guide.com/)に行くとサンプルがたくさんあるので
(1) 作りたいパーツを見つける。(ドロップダウンメニュー、ツールチップなど。パーツの名前が難しいので「コンポーネント」などを一通り見てみて)
(2) **HTMLの書き方**と**classの付け方**を確認する。
(3) 自分のコードに必要なHTMLとCSSを書き込む（もしくはコピペ）。

もしくは、下の例からコピペして不要な箇所を削除。

### 参考サイト
[日本語ガイド](https://bootstrap-guide.com/)
[実例]( https://bootstrap-guide.com/example)
https://qiita.com/michimichix521/items/3d7193e6002ed2b0e676

## 2. よく使うやつ
### 2-1. レイアウト
countainer: いい感じの幅の要素を作ってくれます。
```html
<div class="container">
</div>
```

row, col: 下のようにすると `<div class="col">写真とか</div>` を同じ幅で並べてくれます。
```html
<div class="container">
	<div class="row">
		<div class="col">写真とか</div>
		<div class="col">写真とか</div>
		<div class="col">写真とか</div>
	</div>
</div>
```

### 2-2. サイズ調整
HTML要素に`mb-3`や`px-2`といったclassをつけることでmargin(要素の外側のスペース)やpadding(要素の内側のスペース)を調整できます。
https://bootstrap-guide.com/utilities/spacing

### 2-3. round
要素の角が丸くなります。
```html
<div class="round"></div>
```

### 2-4. icon
アイコンフォントを使います。
[Bootstrap icon](https://icons.getbootstrap.jp) から好きなiconを見つけて名前を確認して`<i>` タグのclassにつける、もしくはコードをコピペ。

例：alarm。下のようなコードを書くと目覚まし時計のiconが出ます。
```html
<i class="bi bi-alarm"></i>
``` 

※ うまく表示できない場合は1の読み込みでicon用のcssをちゃんと読み込んでいるか確認してみよう。

## 3. 例
### 3-1. ナビゲーションバー
次のところに書いてあります。

### 3-2. ドロップダウンメニュー
ナビゲーションバーと一緒に実装。

![dropdown](https://user-images.githubusercontent.com/48050669/222440920-cf58e3da-0a69-47ef-bfa9-a78db4cc46ea.gif)

必要なのは下の3つを適切に配置すること。
1. ドロップダウン全体を表すdiv要素。 `class="dropdown"`が必須。
2. ドロップダウンを開閉するボタン。 `class="dropdown-toggle"`と`data-bs-toggle="dropdown"`が必須。
3. ドロップダウンの中身。`class="dropdown-menu"`と`class="dropdown-item"`。

```html
<nav class="navbar">

	<div class="container-fluid">
		<a href="index.html" class="display-3 navbar-brand m-3 main-color">My Home Page</a>
	
		<!-- dropdown -->
		<!-- !important 1. ドロップダウン全体を表すdiv要素 -->
		<div class="dropdown m-3 px-5">
			
			<!-- !important 2. ドロップダウンを開閉するボタン -->
			<button class="btn dropdown-toggle main-color" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
			Menu
			</button>

			<!-- !important 3. ドロップダウンの中身  -->
			<ul class="dropdown-menu main-color" aria-labelledby="navbarDropdown">
				<li><a class="dropdown-item" href="#works">Works</a></li>
				<li><a class="dropdown-item" href="#about">About</a></li>
				<li><a class="dropdown-item" href="#register">Register</a></li>
				<li><a class="dropdown-item" href="#news">News</a></li>
				<li><a class="dropdown-item" href="#access">Access</a></li>
				<li><hr class="dropdown-divider"></li>
				<li>あとでsns iconを実装</li>
			</ul>
		</div>
	</div>
</nav>
```
### 3-3. sns icon
基本的には2-4のiconと同じです。snsのiconを探してきて並べます。

<img width="147" alt="icons" src="https://user-images.githubusercontent.com/48050669/222438981-149ed975-e1b2-4572-acba-37500a854938.png">

```html
<div class="py-2">
    <a href="https://www.facebook.com" target="_blank"><i class="bi bi-facebook mx-1 base-color h4"></i></a>
    <a href="https://www.twitter.com" target="_blank"><i class="bi bi-twitter mx-1 base-color h4"></i></a>
    <a href="https://www.instagram.com" target="_blank"><i class="bi bi-instagram mx-1 base-color h4"></i></a>
</div>
```


### 3-4. ジャンボトロン
目立たせたいメッセージがある時に使えます。

<img width="1504" alt="Jumbotron" src="https://user-images.githubusercontent.com/48050669/221405550-80916e16-ce43-40f1-b95f-62ba82863f08.png">

1. 背景を横幅全体に広げる。`class="container-fluid"`。
2. ピンクの丸い角の枠を作る。`class="container rounded"`。
3. スペースを調整。`class="p-4 my-4"`など。

```html
		<!-- !important 1. 背景を横幅全体に広げる。 -->
    <section class="container-fluid py-5 text-center bg-main-color">
			<!-- !important 2. ピンクの丸い角の枠を作る。 -->
			<!-- !important 3. スペースを調整。 -->
      <div class="container bg-accent-color p-4 my-4 rounded">
        <h1 id="about" class="display-4 mb-4 base-color">About</h1>
        <!-- class="lead"で目立たせる -->
        <p class="lead">これは単純なヒーローユニット、注目のコンテンツや情報に特別な注意を喚起するためのシンプルなジャンボトロンスタイルのコンポーネントです。</p>
        <hr class="my-4">
        <p>より大きなコンテナの範囲内でコンテンツに空間をあけるため、文字の体裁と空白ユーティリティクラスを使用している。</p>
      </div>
    </section>
```
### 3-5. カード
<img width="1504" alt="cards" src="https://user-images.githubusercontent.com/48050669/221405513-0c17f1ab-70cc-4b34-a423-5606aa758b40.png">

1. カードの配置を設定する。`class=row row-cols-1 row-cols-md-3`。
2. 各カードの幅を設定する。`class=col`。

```html
<div class="container py-5">
	<div class="row row-cols-1 row-cols-md-3 gy-4">
		<!-- 個別のカードのHTML -->
		<div class="col">
			<div class="card h-100">
				<!-- 中身を書く -->
			</div>
		</div>

		<!-- 個別のカードのHTMLを5個続ける -->
	</div>
</div>
```

個別のカードのHTML

1. カードの全体を表すdiv要素。
2. カード内の要素のデザイン。`card-img-top`、`card-body`、`card-title`、`card-text`。

```html
<div class="col">
	<div class="card h-100">
		<img src="img/night_momiji_river.png" class="card-img-top h-100" alt="...">
		<div class="card-body">
			<h5 class="card-title">card-title</h5>
			<p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
			<div class="text-end pb-1 text-secondary small"><i class="bi bi-calendar-event mx-1 accent-color"></i>2022/7/24</div>
			<div class="text-end text-secondary small"><i class="bi bi-geo-alt-fill mx-1 accent-color"></i>Kyoto</div>
		</div>
	</div>
</div>
```

## 4. 配色のアレンジ
配色で印象が大きく変わるのでうまく色を組み合わせを選んでみましょう。
### 4-1. 配色のコツ
Webサイトを綺麗に見せる配色のコツは見やすい色の組み合わせにして、色を使いすぎないことです。
また、選んだ色に背景用や強調用といった役割を決めてそのルール通りに使うことで整った印象を与えてくれます。

例えば、好きな3色を選んで、下のような割合で使うといい感じです。
1. ベースカラー：主に背景用。70%くらい。
2. メインカラー：主役の色。ロゴや見出しに使う。25%くらい。
3. アクセントカラー：差し色。強調したいときにワンポイント入れる。5%くらい。

```
ベースカラー：メインカラー：アクセントカラー = 70 : 25 : 5
```

※ 割合はあくまで目安なので、数字にこだわらずだいたいでオッケーです。

<img width="1504" alt="colors" src="https://user-images.githubusercontent.com/48050669/222434646-b3b17265-d451-4edd-bb3d-30ae20f312e7.png">


### 4-2. 配色選び
見やすい3色を選んで見ましょう。見やすい組み合わせの3色を選ぶのを助けてくれるサイト
[random-material-palette](https://www.threebu.it/random-material-palette/)を使ってみます。

やることは
1. [random-material-palette](https://www.threebu.it/random-material-palette/)で色の組み合わせを決める。
2. カラーコード(`#F0F4C3`みたいなやつ)を3色分コピーして使う。

![random-palette-comment](https://user-images.githubusercontent.com/48050669/222438120-b32b363e-82de-42e8-a293-a68e4a38c209.jpg)


使ってみるとこんな感じ。

![random-palette2](https://user-images.githubusercontent.com/48050669/222435507-a7dd3724-0ae1-471f-8d3b-b2d7e1929d01.gif)

他にもいろいろあるので興味があったらサイトに行ってみてください。

参考リンク
- 配色について
	- [WEBデザインの配色のコツとおすすめサービスご紹介
](https://qiita.com/aucfan_hasebe/items/dd413c0cda776f84c6e4)
- 色選び
	- [random-material-palette: クリックするだけで3色の組み合わせをランダムに提案。](https://www.threebu.it/random-material-palette/)
	- [より細かい色の組み合わせを提案してくれる。](https://www.happyhues.co/)
	- [画像から4色の組み合わせを提案。](https://imagehues.com/)



