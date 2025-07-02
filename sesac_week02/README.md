# 웹퍼블리싱 week02

### 4일차 박스다루기
* height 값이 지정이 안되어있으면 콘텐츠에 맞춰서 박스가 줄어들거나 커진다
* width도 정해지지 않으면 브라우저 크기에 따라 정해진다
* `box-sizing: border-box;` 이렇게 세팅하면 border값이 포함된 박스 높이가 자동으로 된다
* padding 상하좌우 다른값을 주는 방법(시계방향 상->우->하->좌) => margin도 동일하다
 + padding과 margin의 다른점
    + box1에 bottm에 margin을 주고 box2에 top에 margin을 주면 큰 값으로 병합된다 (좌우는 제외)
    + magin은 음수값이 가능하다
```html
	{ padding : 10px; } 4면의 값이 모두 같을때
	{ padding : 10px 20px; } 상/하 , 좌/우 : 상하가 같고 좌우가 같을때
	{ padding : 10px 20px 15px; } 상, 좌/우, 하 : 상하가 다르고 좌우가 같을때
	{ padding : 10px 20px 12px 15px; } 상, 우, 하, 좌
	{ padding-top : 10px; } top, right, left, bottom 한 면씩 따로 지정가능
```
* margin left, right를 auto로 주면 가운데 정렬이 된다
* margin: 0 auto; 로 주면 좌우 auto가 된다(노멀 플로우에서 가운데 정렬은 이렇게 적어야함)
* normal flow에서는 위아래 auto가 되지않고 좌우만 가능하다 그래서 margin: auto; 는 아니다(flex 공간에서는 된다)
* 박스 안에 여러개의 박스가 나열되어있을때 같은 margin-top을 주는방법
```html
   HTML
	<div class="text">
		<p>안녕하세요</p>
		<p>반갑습니다</p>
		<p>감사합니다</p>
	</div>
   CSS
	.text > p + p { margin-top : 20px; } : p의 형을 둔 p동생에게 margin-top을 적용하는방법
	그래서 p의 형을 둔 p동생들은 전부 margin-top이 적용된다
```
* inline 태그는 위 아래로 padding, margin 을 줄수없다(좌우는 가능)
* text-align : left, center, right

----

### 5일차 이미지 다루기
* object-fit : cover -> 이미지가 짤리지 언정 비율을 유지해서 div사이즈에 맞춰서 들어간다, figma : fill과 같다
* object-fit : contain -> 공간이 남을지 언정 짤리지 않게(꽉차게) div 사이즈에 맞춰 들어감, figma : fit과 같다
* backgruond-image: url('이미지위치')
* background-repeat: no-repeat -> 백그라운드 이미지가 반복되지않게 / repeat-x로 넣으면 x값에만 들어간다
* background-position: right bottom; 이렇게해도되고 퍼센트,px 다 넣을수있다

***이미지 hover***
* `<a href="" class="like">즐겨찾기</a>`<br>시각장애인을 위해 기계가 읽을 수 있게 글씨는 작성하되 비장애인에게는 보이지 않아야 하기에 font size를 0으로 한다

<img src="https://github.com/user-attachments/assets/99818939-52da-4912-af7e-bdcab595b517" style="margin-left=100px;">

* 이미지에 마우스를 가져다 댔을때 색상이 바뀌는건 이미지의 위치가 바뀌는것이다
* 꼭 <b>background-repeat:no-repeat</b>을 걸어야 한다
```html
 CSS
   .icon > .like {
            border: 1px solid black;
            width: 50px;
            height: 50px;
            display: block;
            font-size: 0;
            background-image: url('./images/icon.png');
            background-repeat: no-repeat;
            background-position: 0 0;
        }
        .icon > .like:hover {
            background-position: -50px 0; -> 왼쪽으로 이동할때는 (-)를 붙여준다
```
