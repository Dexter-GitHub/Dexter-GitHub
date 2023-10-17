# CSS(Cascading Style Sheet)
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/CSS3_logo_and_wordmark.svg/363px-CSS3_logo_and_wordmark.svg.png" width="100">
<br>

## CSS를 html에 포함시킬 수 있는 두가지 방법
<br>

```
<!DOCTYPE html>
<html>
<head>
    <style>
        h2 {
            color: blue;
        }
    </style>
</head>
<body>
    <h1 style="color:red">Hello World</h1>
    <h2>Hell world</h2>
</body>
</html>
```
<br>

## 선택자

### ID 선택자
<br>

```
<!DOCTYPE html>
<html>
<head>   
    <style>
        /* Tag 선택자 */
        li {
            color: red;
            text-decoration: underline;
        }
        /* ID 선택자 */
        #select {
            font-size: 50px;
        }
    </style> 
</head>
<body>
    <ul>
        <li>HTML</li>
        <li id="select">CSS</li>
        <li>JavaScript</li>
    </ul>
</body>
</html>
```
<br>

### 부모 자식 선택자
<br>

```
<!DOCTYPE html>
<html>
<head>
   <style>
        /* 상속 Tag 선택자 */    
        ul li {
            color:red;
        }
        /* 상속 Tag 선택자 */
        #lecture > li {
            border: 1px solid red;            
        }
        /* 각각의 Tag 선택자 */
        ul, ol {
            background-color: powderblue;
        }        
   </style>
</head>
<body>
    <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
    </ul>
    <ol id="lecture">
        <li>HTML</li>
        <li>CSS
            <ol>
                <li>slelctor</li>
                <li>declaration</li>
            </ol>
        </li>
        <li>JavaScript</li>
    </ol>
</body>
</html>
```
<br>


## CSS cheat sheet
<img src="https://i.pinimg.com/564x/c5/3a/9a/c53a9af294644583b92d21bb66e504fe.jpg">
<br>

## 가상 클래스 선택자
<br>

* :link - 방문한 적이 없는 링크
* :visited - 방문한 적이 있는 링크(일부 속성만 사용 가능)
* :hover - 마우스를 롤오버 했을 때
* :active - 마우스를 클릭했을 때
* :focus - 포커스 하였을 때
<br>

## Cascading 우선순위 
Style attribute > ID selector > Class selector > Tag selector

> 속성 뒤 !important 키워드를 사용하면 가장 높은 우선순위를 적용할 수 있다.   
> 하지만, !important 사용은 권장 되지 않으며 Cascading 우선순위를 잘 적용하여 사용하는 것이 좋다.

### Example
```
<!DOCTYPE html>
<html>
<head>
    <style>
        li {color: red !important; }
        #idsel{color:blue;}
        .classel{color: green;}
    </style>
</head>
<body>
    <ul>
        <li>html</li>
        <li id="idsel" class="classsel" style="color:powderblue;">css</li>
        <li>javascript</li>
    </ul>
    <ol>
        <li>style attribute</li>
        <li>id selector</li>
        <li>class selector</li>
        <li>tag selector</li>
    </ol>
</body>
</html>
```
<br>

## font size
<br>

> font 단위 = px(절대적), em(상대적), rem(상대적)   
> px는 고정 크기이며 em 또는 rem은 사용자 환경에 따라 변경되는 단위이며, rem단위가 많이 사용되고 있다.   
> em 단위 는 상위 요소의 글꼴 크기에 상대적이다.    
> 반면 rem에서 "r"은 "root"를 나타내기 때문에, rem 단위 는 HTML 문서의 루트 글꼴 크기에만 상대적이다.
<br>

## color
<br>

> css에서 color 표현방식은 rgb 또는 hex 표현 방식을 쓴다.

```
rgb(255, 255, 255) // 첫번째 인수 red, 두번째 인수 green, 세번째 인수 blue
#FF0000            // red
#00FF00            // green
#0000FF            // blue
```
<br>

## font-family
<br>

* serif = 장식있는 폰트
* sans-serif = 장식이 없는 폰트
* monospace = 고정폭

### Example
```
<!DOCTYPE html>
<html>
<head>
    <style>
        #type1 {
            font-size: 5rem;
            font-family: Arial, verdana, Helvetica, monospace;
            font-weight: bold;  /* 폰트 굵기 */
            line-height: 2;     /* 줄간격 (default=1.2) */
        }
        #type2 {
            font: bold 5rem/2 arial, verdana, Helvetica, serif;
        }
    </style>
</head>
<body>
    <p id="type1">
        Hello world<br>
        Hello world
    </p>
    <p id="type2">
        Hello world<br>
        Hello world
    </p>
</body>
</html>
```
> font 속성은 옵션 순서가 정해저 있음으로 구글 검색을 통해 순서를 확인하고 사용한다.
<br>

## WEB font
<br>

google web font 사용 예제

```
<!DOCTYPE html>
<html>
<head>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100&family=Roboto:ital,wght@0,100;0,300;1,100&family=Tilt+Neon&display=swap" rel="stylesheet">
    <style>
        #font1 {
            font-family: 'Roboto', sans-serif;
        }   
        #font2 {
            font-family: 'Tilt Neon', sans-serif;
        }   
    </style>
</head>
<body>
    <p id="font1">
        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    </p> 
    <p id="font2">
        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    </p> 
</body>
</html>
```
<br>

## inline or block
<br>

* h1 태그는 기본적으로 block 레벨이다. block은 화면전체를 사용하는 특성을 가지고 있다.   
* a 태그는 기본적으로 inline 레벨이다.
* 아래 display 속성을 통해 레벨을 변경할 수 있다.

### Example
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">    
    <style>
        h1, a {border: 1px solid red;}     
        h1 {display: inline;}   
        a {display: block;}
    </style>
</head>
<body>
    <h1>Hello wolrd</h1>
    안녕하세요. <a href="https://github.com/Dexter-GitHub">Dexter</a>입니다. 
</body>
</html>
```  
<br>

## box 모델
<br>

* margin은 엘리먼트 테두리간의 간격을 조절한다.
* padding은 box 모델과 데이터 간의 간격을 조절한다.

### Example
```
<!DOCTYPE html>
<html>
<head>
    <style> 
        p, a {            
            border: 10px solid red;
            padding: 20px;
            margin: 40px;
            width: 120px;   /* inline 레벨 태그는 width, height 값은 무시 된다. */
        }
    </style>    
</head>
<body>
    <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Tempora, explicabo.
    </p>
    <p>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Tempora, explicabo.
    </p>
    안녕하세요.<a href="https://a.com">Dexter</a>입니다.
</body>
</html>
```
<br>

### box sizing
<br>

* box 모델의 width 또는 height 지정시에 border의 사이즈 때문에 예측이 힘들다.
* box-sizing 속성을 이용하면 보다 예측이 쉬운 형태로 조절 가능하다.
### Example
```
<!DOCTYPE html>
<html>
<head>
    <style>
        div {
            margin: 10px;
            width: 150px;
            box-sizing: border-box;
        }
        #small {
            border: 10px solid black;
        }
        #Large {
            border: 30px solid black;
        }
    </style>    
</head>
<body>
    <div id="small">Hello</div>
    <div id="Large">Hello</div>
</body>
</html>
```
<br>

## 포지션(Position)
<br>

* static : 포지션 관련 값들을 무시한다. (기본값)
* relative : 옵셋(left, right, top, bottom)값들이 부모 엘리먼트 상대적으로 적용된다.
* absolute : 절대 포지션(position 값이 지정된 부모 엘리먼트를 상대적으로 옵셋 값 적용)
* fixed : 스크롤에 관계없이 위치 고정
<br>

## flex
<br>
<p>
CSS의 flex는 엘리먼트들의 크기나 위치를 쉽게 잡아주는 도구이다.   
지금까지 레이아웃과 관련된 다양한 속성들이 있었지만 그리 효과적이지 않았다.   
flex를 이용하면 레이아웃을 매우 효과적으로 표현할 수 있다.  
</p>

* flex를 사용하기 위해서는 컨테이너 태그에 display: flex 속성을 부여하야 한다.
* flex-direction을 이용해서 정렬방향을 바꿀 수 있다.
<br>

### grow & shrink

<p>
아이템은 컨테이너의 크기에 따라서 작아지기도 하고 커지기도 한다. 이 때 작아지고, 커지는 비율을   
지정하는 방법이 바로 grow & shrink 이다.
</p>

### Example 
```
<!DOCTYPE html>
<html>
<head>
    <style>
        .container {
            background-color: powderblue;
            height: 200px;
            display: flex;
            flex-direction: row;
        }
        .item {
            background-color: tomato;
            color: white;
            border: 1px solid white;            
        }
        .item:nth-child(1) {
            flex-basis: 150px;
            flex-grow: 1;
        }
        .item:nth-child(2) {
            flex-basis: 150px;
            flex-shrink: 1;
        }
    </style>
</head> 
<body>
    <div class="container">
        <div class="item">1</div>
        <div class="item">2</div>
        <div class="item">3</div>
        <div class="item">4</div>
        <div class="item">5</div>
    </div>
</body>
</html>
```
<br>

### holy grail layout example
<br>

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">    
    <style>
        body {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .container {
            display: flex;
            flex-direction: column;
            width: 800px;
            border: 1px solid gray;
        }
        header {
            border-bottom: 1px solid gray;
            padding-left: 20px;
        }
        footer {
            border-top: 1px solid gray;
            padding: 20px;
            text-align: center;
        }
        .content {
            display: flex;
        }
        .content nav {
            border-right: 1px solid gray;
        }
        .content aside {            
            border-left: 1px solid gray;
        }
        nav, aside {
            flex-basis: 150px;
            flex-shrink: 0;
        }       
        main {
            padding: 10px;
        }
        nav {
            order: -1;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Dexter</h1>
        </header>
        <section class="content">
            <main>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quae, quaerat repellat a explicabo quibusdam ea rem pariatur repellendus qui magnam, fugit, recusandae sequi omnis? Sed, tenetur. Libero mollitia sapiente blanditiis facilis tempore
                adipisci dignissimos accusantium obcaecati sit veniam culpa voluptas commodi amet, rem excepturi, quaerat optio inventore! Optio dolores atque, ipsa officiis, obcaecati molestias vitae sapiente voluptatum adipisci, eaque necessitatibus
                voluptatibus doloremque accusantium suscipit alias provident aliquid soluta odit deserunt officia hic ducimus a dolore! Possimus expedita ex iste aspernatur deserunt, nostrum molestias fugiat dolorum sed laudantium, in aliquam culpa illo nulla
                voluptates ratione dignissimos rem, at quasi magni mollitia?
            </main>
            <nav>
                <ul>
                    <li>html</li>
                    <li>css</li>
                    <li>javascript</li>
                </ul>
            </nav>          
            <aside>
                AD
            </aside>
        </section>
        <footer>
            <a href="https://github.com/Dexter-GitHub">Home Page</a>
        </footer>
    </div>
</body>
</html>
```
<br>

## Media query(사용 장치에 따라 UI 표현)

<p>
media query는 화면의 종류와 크기에 따라서 디자인을 달리 줄 수 있는 CSS의 기능이다. 특히 최근의 트랜드인 반응형 디자인의 핵심 기술이라고 할 수 있다.
</p>

