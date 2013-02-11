Faux Column
===========
## 문제

<dl>
	<dt>faux [fou] </dt>
	<dd>모조의</dd>
</dl>

블럭요소로 컬럼 레이아웃을 구성할 때 블럭요소는 자기가 필요한 만큼만 늘어나고 더이상 늘어나지 않는다. 그래서 배경색을 높이가 가장 큰 컬럼만큼 채워 주고자 할 때 곤란함을 겪게 된다.

![블럭요소로 컬럼 레이아웃을 구성할 때 블럭요소는 자기가 필요한 만큼만 늘어나고 더이상 늘어나지 않는다. 그래서 배경색을 높이가 가장 큰 컬럼만큼 채워주고자할 때 곤란함을 겪게 된다.](http://elegantcoder.github.com/Fronteers-Repo/images/Layout/FauxColumns/tilecheat_1.gif "Faux Columns 개요 이미지")

## 해결
세로로 반복되는 배경이미지로 배경색이 있는 컬럼처럼 보이도록 구현한다.
body 에 배경관련 속성을 준다. repeat-y 속성을 주어 세로로 반복 시키고, 가로 기준으로 화면 중앙에 위치한 레이아웃인 경우 background-position: 50% 0 으로 준다.

### 이미지
![세로로 반복되는 배경이미지](http://elegantcoder.github.com/Fronteers-Repo/images/Layout/FauxColumns/tilecheat_2.gif "세로로 반복되는 배경 이미지")

### HTML
```html
<body>
	<div id="container">
		<div id="left"></div>
		<div id="right"></div>
		<div id="clear"></div>
	</div>
</body>
```

### CSS
```css
body {
	background: #ccc url('./background.gif') repeat-y 50% 0;
}

#container {
	width: 980px;
	margin: 0 auto;
}

#left, #right {
	float:left;
	padding: 20px;
}

#left {
	width: 661px;
}

#right {
	width: 239px;
}

#clear {
	clear: both;
}
```


## 참고
* [http://alistapart.com/article/fauxcolumns](http://alistapart.com/article/fauxcolumns)
