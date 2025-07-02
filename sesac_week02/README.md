## 웹퍼블리싱 week02

### 4일차 박스다루기
* `box-sizing: border-box;` 이렇게 세팅하면 border값이 포함된 박스 높이가 자동으로 된다
* padding 상하좌우 다른값을 주는 방법(시계방향 상->우->하->좌) => margin도 동일하다
 + padding과 margin의 다른점
    + box1에 bottm에 margin을 주고 box2에 top에 margin을 주면 큰 값으로 병합된다 (좌우는 제외)  
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
