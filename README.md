# Bootstrap導入サンプルサイト
## このサンプル目的
cssをできるだけ書かずに整ったデザインを実装する！
HTMLにBootstrapで決められたclassをつけるだけでデザインが変わります。

### 目次
1.  Bootstrapの導入
2. よく使うやつ
	- container
	- row, column
	- サイズ調整
	- round
	- icon
3. 例
	1. ナビゲーションバー
	2. ドロップダウンメニュー
	3. sns icon
	4. ジャンボトロン
	5. カード
	6. フォーム
	7. News
4. 配色のアレンジ
 
## 1. Bootstrapの導入
### 読み込み
Bootstrapが作ったCSSやjavascriptを読み込むと，ルールに沿ってHTMLを書くだけで整ったデザインになります。

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

### 参考サイト
[日本語ガイド](https://bootstrap-guide.com/)
[実例]( https://bootstrap-guide.com/example)
https://qiita.com/michimichix521/items/3d7193e6002ed2b0e676

## よく使うやつ
### レイアウト
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

### サイズ調整
HTML要素に`mb-3`や`px-2`といったclassをつけることでmargin(要素の外側のスペース)やpadding(要素の内側のスペース)を調整できます。
https://bootstrap-guide.com/utilities/spacing

### round
要素の角が丸くなります。
```html
<div class="round"></div>
```

### icon
アイコンフォントを使います。
[Bootstrap icon](https://icons.getbootstrap.jp) から好きなiconを見つけて名前を確認して`<i>` タグのclassにつける、もしくはコードをコピペ。

例：alarm。下のようなコードを書くと目覚まし時計のiconが出ます。
```html
<i class="bi bi-alarm"></i>
``` 

※ うまく表示できない場合は1の読み込みでicon用のcssをちゃんと読み込んでいるか確認してみよう。

## 3. 例
### ナビゲーションバー
### ドロップダウンメニュー
### sns icon
### ジャンボトロン
### カード
### フォーム

## 4. 配色のアレンジ


