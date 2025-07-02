# 웹퍼블리싱 수업 week 01
### 1일차 - HTML, CSS 란 (h1~h6, ul, ol, li, dt, dl, dd)
* DOM과 CSSOM이란?
  + DOM : 내용을 담당하고 있는 정보뭉치(모양과 색X) -> 디폴트 값으로 인해 자동으로 모양이 정해진다
  + CSSOM : 모양과 색에 대한 정보 뭉치
* 문자는 따옴표를 사용하고 숫자는 사용하지않는다
* head는 세팅(style도 여기에 포함), body는 내용
* 기능
  * alt + shift + 아래방향키 : 그 줄이 복사된다
  * ctrl + / : 주석
* 태그와 요소
  + <> : 시작태그 </> : 종료태그
  + h1, h2, h3 ... h6
  + br 태그 : br태그로 줄바꿈을 할 경우 하나의 문장으로 인식하여 하나의 상자가 된다 -> 문단과 문단의 간격을 css로 조정 불가능
  + p 태그 : p태그로 나누면 두 문단이 두개의 상자로 인식하여 css를 이용하여 간격을 조정할 수 있다
  + 순서가 없는 목록(ul, li) : 등수나 순서가 없이 하나의 주제로 나열되어있는 컨텐츠를 표시할때 사용    
    ```html
    <ul> 
      <li>콜라</li>
      <li>사이다</li>
      <li>오렌지 쥬스</li>
    </ul>
    ```
    
    잘못 된 예 : ul의 직계자식으로는 li만 들어갈수있다 만약 필요한 경우 li의 자식으로 넣을수 있다
    ```html
    <ul>
      <h3>편의점에 파는 음료들</h3> ->이렇게 넣을 수 없다
      <li>콜라</li>
    </ul>
    ```
  + 순서가 있는 목록(ol, li) : li 앞에 간격과 표시되는 숫자는 브라우저 측 css에 명령되어 있다
    ol의 직계자식으로 li만 가능
    ```html
    <ol>
      <li>사이다</li>
      <li>콜라</li>
      <li>오렌지주스<li>
    </ol>
    ```
  + 정의하기 위한 목록(dl, dt, dd) : dl 부모, dt 정의될 대상, dd 설명하는 역할
    ```html
    <dl>
      <dt>종류:</dt>
      <dd>콜라</dd>
      <dd>사이다</dd>
      <dd>오렌지쥬스</dd>
      <dt>색소가없는것:</dt>
      <dd>오렌지쥬스</dd>
    </dl>
    ```
    + 주의할 점 : dl 의 자식은 dt,dd만 올수있다 / dt없이 dd만 사용x
    + 올바른 예 : 하나의 정의에 다수의 설명 가능, 다수의 정의에 하나의 설명 가능 / 필요한 의미의 태그들은 dt, dd 안에 넣어서 사용
    ```html
    <dl>
      <dt>종류:</dt>
      <dd>
        <ul>
            <li>콜라</li>
            <li>사이다</li>
        </ul>
      </dd>
      <dd>
        <p> 콜라는 몸에 해롭다</p>
      </dd>
    </dl>
    ```

---

### 2일차 - CSS요소 ( 다양한 인라인태그들 )
* 최신규격 문서세팅을 하기 하기 위해서는 -> !DOCTYPE html을 적어줘야 한다
* 블록성질 상자는 한칸을 차지하는 기본단위의 상자를 만들기 위해서이다
* block 성질 상자는 한 줄을 차지한다
* div와 span은 범용적인 요소여서 특정부분에 스타일을 설정하고 싶을때 적합한 태그가 없을경우 사용된다

  ex) div

    혜진은 배가 div 고프다 div

    -> 혜진은 배가

    -> 고프다
  
* inline 상자는 한줄에 적용 된다

  ex) 혜진은 배가 span 고프다 span -> 혜진은 배가 고프다

* 인라인상자는 인라인 태그를 넣지 않아도 글자만 있다면 그 글자를 보여주기 위해 자동 생성된다. 자동생성되는 되는 인라인 상자를 Anonymous inline box라고 부름
* div 을수 /div 는 블록상자(div) > 라인상자(자동생성) > 인라인 상자(자동생성) > '을' '수'가 있는것
* div 을 span 수 /span /div라면 '을'은 익명의 인라인 상자로, '수'는 span 인라인 상자로 쪼개진것
* 블록성질상자가 만들어지는 태그는 div, h1, ul.. 등
* 인라인성질상자 만들어지는 태그 a, span, strong,em,i,b,cite,q,s,img 이다
* p태그에 div를 넣는건 안된다. div안에는 p 가능
* 기능 : alt를 누른채 원하는 곳에 마우스를 누르면 <b>멀티커서</b>가 생긴다, shift를 누른상태에서 방향키를 누르면 동시에 다같이 선택된다

#### 인라인태그
* 인라인태그는 p태그 안에 넣어도 된다
  + span : 선택할때
  + strong : 강조할때, 강한중요성
  + em : 약한강조(이탤릭체)
  + i : 나는달라(이탤릭체)
  + b : 나는달라(볼드), 강조하고싶다면 strong을 써야한다
  + q : 짧은 인용(쌍따옴표가 생긴다)
  + s : 옛날에는 그랬는데 아닐때(가운데 줄처리)
  + cite : 긴인용(노래,대본,책 등 저작권있는거 인용- 이탤릭체)
  + small : 요약 저작권,라이센스요건,법적규제같은것들
  + del : 삭제된 범위를 나타낼때(가운데 줄)
  + ins : 추가된 범위를 나타낼때 (밑줄)
  + img src를 꼭넣어줘야한다, alt는 어떤이미지인지설명해주는것
  ```html
    <img src="이미지링크", alt="이미지설명" />
  ```
  + a : 링크를 추가하는 요소, href가 있어야 클릭이 된다 쌍따옴표안에 #을 넣거나 공란으로 두면 새로고침이 된다
  ```html
    <a href="링크1">링크2</a> : 링크1과 링크2에 동일한 링크를 넣으면 링크2가 웹페이지에 표시되고 누르면 링크1로 링크된다
  ```
  + href = 주소 target = _blank를 하면 새창으로 열린다
  + href = #point로 이동해라
  + href = mailto: 메일주소
  + href = tel : 전화번호
  + address : 연락처, p태그보다 div태그가 낫다
  ```html
   <address>
      <div> hyejin의 메일 </div>
      <div> 서울특별시 </div>
   </address>
  ```
  + id=point는 한지점, class=는 여러개 이름을 붙일수 있다
  ```html
    <p id="point" class="uxui">안녕하세요</p>
  ```
  + p태그 안에 꺽새를 표현할때는 그냥 꺽새를 쓰면 안된다, &lt와 &gt가 꺽새
  ```html
    <p>&lt;div&gt;태그는 이런겁니다</p>
  ```
#### CSS
 * head에 style로 css가 들어간다
 * class를 스타일에 넣을경우 앞에 점을 적으면 된다
  ```html
    <style>
        .basic{ color : blue; }
    </style>
    <body>
        <p class="basic"> 안녕하세요 </p>
    </body>
 ```
  * border-radius : 박스라운드, padding : 안쪽여백, margin : 바깥여백 -> 숫자와 픽셀을 사용한다
 ```html
  .basic { border-radius: 8px;
            padding : 4px;
            margin: 4px; }
  ```
 * box shadow : x축 y축, rgba 값
```html
  .basic { 4px 5px rgba(0,0,0,1); }
```
  + rgba는 앞에 세개는 색상값 맨마지막은 색상이 퍼지는 정도
 
 * 대상을 선택할때 부모이름 > 자식이름 을 이용해서 구조적으로 선택할 수 있다
 * 대상을 선택할때 부모이름(빈칸)자손이름을 이용해 구조적으로 선택할 수 있다
 
 ```html
<style>
 .career > h2 { color: blue; }
 .career li li { border : 2px solid red ; }
</style>
<body>
<div class="career info_box"> = class 이름이 두개인거
		<h2>경력사항</h2>
		<h3>회사경력</h3>
		<ul>
			<li>현)가민 에이전시</li>
			<li>여성
				<ul>
					<li>웹디자인팀</li>
					<li>웹퍼블리싱팀</li>
				</ul>
			</li>
			<li>남성
				<ul>
					<li>웹디자인팀</li>
					<li>웹퍼블리싱팀</li>
				</ul>
			</li>
			<li>전)솔트솔루션</li>
		</ul>
	</body>
```

---

### 3일차 CSS 선택자
 * 브라우저 측 css는 작성자와 중복 될시 무력화 된다. 리셋용 css를 만들어서 사용함
```html
  /* reset */
		body {
			font-size: 12px;
			font-style: normal;
			font-weight: 400;
			line-height: 1.2; 
		}
		h1, h2, h3, h4, h5, h6 {
			font-size:1em;
			font-weight:bold;
		}
		h1, h2, h3, h4, h5, h6, div, p, dl, body, dt, dd, ul, ol, li, form, fieldset, blockquote, address, table, thead, tbody, tfoot, tr, td, caption {
			margin:0;
			padding:0;
		}
		li {
			list-style:none;
		}
```

#### Head 
 * html lan="ko" -> 영어는 en head전에 DOCTYPE 다음에 선언해주면 된다
 * meta charset="utf-8" 적어줘야함
   
   `<link rel="styleshee" href="./css/basic.css/>` -> 현재공간에있는 css를 찾고 이 파일로 들어가라

 * title 여기에 적기
 
 #### CSS
 * `:first child` 가상클래스 선택자는 부모요소의 자식요소중에서 제일 첫번째에 위치하는 요소를 선택한다
```html
   HTML	
   <ol>
	<li>첫번째입니다</li>
	<li>두번째입니다</li>
	<li>세번째입니다</li>
   </ol>

   CSS
   li:first child{ color : blue; } : 첫번째 li만 블루가 들어간다
```
 * 총 높이가 322px일 경우 패딩값+보더값을 빼야 height 값
 * height를 줬을때 글자양이 많아서 박스에 넘치면 overflow-y 히든을 주면된다
 * scroll은 스크롤이 생긴다
 * auto는 넘치면 스크롤이 생기고 필요없으면 안생긴다
```html
	.box { overflow-y : auto; }
```

 * 아래에 쓴게 우선이 되서 위에 쓴거를 덮어쓴다
 * hover은 마우스를 가져다 되면 색이 변경된다
 * ease 속도의 느낌
 * box-sizing은 넓이와 높이를 정하는 기준을 설정한다
   기본값으로 컨텐츠 영역(content-box)으로 되어있는데 보더영역(boredr-box)으로 기준을 바꾸면 설정한 사이즈에
   컨텐츠 영역 -> 패딩영역 -> 보더영역 모두가 포함
```html
	.basic h2+div {} -> h2 뒤에 붙어있는 div라는 의미
	.button: hover {} -> 마우스 가져다 되면 색이 변경됨
	.button: activ { transform : translate(5px,5px); box-shadow: non; } -> 가로세로 5px만큼 움직이는거
```  

