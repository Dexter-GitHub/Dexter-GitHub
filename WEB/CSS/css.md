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
        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and
        scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with
        the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
    </p> 
    <p id="font2">
        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and
        scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with
        the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
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

> 레이아웃 예제를 보기전 시멘틱 태그(sementic tag)를 사용한 레이웃 구성표를 참고하자.   

#### 시멘틱 태그란 ?

> <div> 태그의 기능과 마찬가지로 block element이면서 사이트의 구조(레이아웃)을 설계하기 위한 태그.       
> HTML의 구조를 설계하는데 있어 태그에 의미를 부여 함으로써 사이트의 구조를 파악하기 용이할 수 있도록 도와주기 위해 만들어진 태그.

<img width="500px" src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F4rchP%2FbtqYN03i7Ml%2FdFfx6I4t3FzrZfGSKwrfkk%2Fimg.png">
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
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quae, quaerat repellat a explicabo quibusdam ea rem pariatur repellendus qui magnam, fugit, recusandae sequi omnis? Sed, tenetur. Libero
                mollitia sapiente blanditiis facilis tempore adipisci dignissimos accusantium obcaecati sit veniam culpa voluptas commodi amet, rem excepturi, quaerat optio inventore! Optio dolores atque, ipsa
                officiis, obcaecati molestias vitae sapiente voluptatum adipisci, eaque necessitatibus voluptatibus doloremque accusantium suscipit alias provident aliquid soluta odit deserunt officia hic
                ducimus a dolore! Possimus expedita ex iste aspernatur deserunt, nostrum molestias fugiat dolorum sed laudantium, in aliquam culpa illo nulla voluptates ratione dignissimos rem, at quasi magni
                mollitia?
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
<br>

## float

<p>
    Float는 편집 디자인에서 이미지를 삽화로 삽입할 때 사용하는 기법이다. 또한 레이아웃을 잡을 때도 사용하는 기능이기 때문에 꽤 중요하다.
</p>

* float 속성을 무시하는 태그를 적용할 때 "clear: both"  또눈 "right" or "left" (float 속성을 사용하는 엘리먼트 방향에 따라 적용)

### float를 이용한 holy fgrail layout example
<br>

```
<!DOCTYPE html>
<html>
<head>
    <style>
        * {
            box-sizing: border-box;
        }
        .container {
            width: 540px;
            border: 1px solid gray;
            margin: auto;
        }   
        header {
            border-bottom: 1px solid gray;
        }
        nav {
            float: left;
            width: 120px;
            border-right: 1px solid gray;
        }
        article {
            float: left;
            width: 300px;
            border-left: 1px solid gray;
            border-right: 1px solid gray;
            margin-left: -1px;
        }
        aside {
            float: left;
            width: 120px;
            border-left: 1px solid gray;
            margin-left: -1px;
        }
        footer {
            clear: both;
            border-top: 1px solid gray;
            text-align: center;
            padding: 20px;
        }        
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>CSS</h1>
        </header>        
        <nav>
            <ul>
                <li>position</li>
                <li>float</li>
                <li>flex</li>
            </ul>
        </nav>
        <article>
            <h2>float</h2>                
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Aspernatur asperiores possimus eos illo voluptate porro repellat sequi architecto ab! At doloribus ipsam quidem nobis. Ex exercitationem
            aspernatur accusantium! Rem eaque tempora vero ducimus magni dolores necessitatibus nam assumenda optio. Cumque laborum dolorem inventore quaerat impedit reiciendis ipsum consequatur saepe optio. 
        </article>
        <aside>
            ad
        </aside>        
        <footer>
            copyleft
        </footer>
    </div>
</body>
</html>
```
<br>

## multi column
<p>
    다단(multi column)은 신문처럼 화면을 분할해서 좀 더 읽기 쉽도록 만든 레이아웃을 의미한다.   
    CSS에서는 이러한 레이아웃을 쉽게 구현할 수 있는 기능을 제공합니다. 
</p>

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="author" content="Dexter">
    <style>
            .column {
                text-align: justify;
                column-count: 4;
                /* column-width: 200px; */
                column-gap: 30px;
                column-rule-style: solid;
                column-rule-width: 5px;
                column-rule-color: red;
            }
            h1 {
                column-span: all;
            }
        </style>
</head>
<body>
    <div class="column">
        ... long text(ex:Lorem1000)
        <h1>Title</h1>
        ...
    </div>
</body>
</html>
```
<br>

## background
<p>
CSS를 이용하면 엘리먼트의 배경을 지정할 수 있다.
</p>

* background-color : red
* background-image : url("bg.png")
* background-repeat : repeat, no-repeat, repeat-x, repeat-y
* background-attachment : scroll, fixed
* background-position : left top or x% y% or x y
* background-size : 100px 100px or cover or contain
<br>

## filter
<p>
    필터는 이미지에 다양한 효과를 추가하는 방법이다. 
</p>

```
<!DOCTYPE html>
<html>
<head>
    <style>
        img {
            width: 200px;
            transition: all 1s;
        }
        img:hover {
            -webkit-filter: grayscale(100%) blur(3px);
            -o-filter: grayscale(100%) blur(3px);
            filter: grayscale(100%) blur(3px);
            width: 200px;
        }
        h1 {
            -webkit-filter: blur(3px);
            -o-filter: blur(3px);
            filter: blur(3px);
        }
    </style>
</head>
<body>
    <h1>CSS</h1>
    <img src="images.png" alt="">
</body>
</html>
```
<br>

## Transform
<p>
    transform은 엘리먼트의 크기, 위치, 모양을 변경하는 속성이다. 
</p>

<a target="_blank" href="https://codepen.io/vineethtrv/pen/XKKEgM">CODE PEN CSS Transform link</a>

## Transition
<p>
    전환은 효과가 변경되었을 때 부드럽게 처리해주는 CSS의 기능이다. 
</p>

* transition-duration
* transition-property
* transition-delay
* transition-timing-function
* transition
<br>

<a target="_blank" href="https://matthewlein.com/tools/ceaser">transition timming function 만들기</a>

#### Example
```
<!DOCTYPE html>
<html>
<head>
    <style>
        a {
            font-size: 3rem;
            display: inline-block;
            /* 
            transition-property: font-size transform;
            transition-duration: 0.1s; 
            transition: all 0.1s;
            */
            transition: font-size 1s, transform 0.1s;
        }
        a:active {
            transform: translate(20px, 20px);
            font-size: 2rem;
        }
    </style>
</head>
<body>
    <a href="#">Click</a>
</body>
</html>
```
<br>

## link, import
<br>

```
...
<head>
    <!-- <link rel="stylesheet" href="style.css"> or -->
    <style>
        /* css 선언 안에서 사용가능 */
        @import url('style.css');
    </style>
</head>
...
```
<br>

## 코드 경량화(minify)
<br>

#### WEB 어플리케이션을 이용한 경량화

* <a target="_blank" href="https://adamburgess.github.io/clean-css-online/">CLEAN CSS LINK</a>
<br>

#### IDE 확장 익스텐션 설치
* vscode 확장 익스텐션 minifier을 설치하여 사용 가능하다.
<br>

#### nodejs 기반 minify를 이용한 경량화

설치
```
npm install clean-css-cli -g
```

사용법
```
cleancss -o filename.min.css filename.css
```
<br>

## Fontello

<p>
    딩벳폰트는 폰트 대신 어떤 문자에 해당하는 이미지로 이루어진 폰트를 의미합니다.
    fontello는 딩벳이나 아이콘을 폰트로 제공하는 여러 서비스를 모아둔 서비스입니다. 
    특히 SVG 파일을 업로드하면 폰트로 만들어주기도 합니다. 
</p>

#### fontello 사이트
* <a target="_blank" href="https://fontello.com/">fontello link</a>

> 위 사이트에서 원하는 아이콘을 선택하고, 다운받는다. 사용방법은 아래 예시 코드와 같다.

```
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="css/fontello.css">
    <style>
        body {
            font-family: "fontello";
            font-size: 100px;
        }
    </style>
</head>
<body>
    <!-- 아이콘 코드를 사용 (font-family 속성 정의가 필요) -->
    &#xe800<br>  
    &#xf119
    <i class="icon-frown"></i>    <!-- 아이콘 이름으로 사용(font-family 속성 정의가 필요치 않다)  -->
</body>
</html>
```
<br>
