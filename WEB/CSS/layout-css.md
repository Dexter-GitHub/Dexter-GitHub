# CSS 레이아웃 
<p>
  display 속성에서 inline과 block, 이 둘을 합쳐놓은 inline-block에 대하여 설명 한다.
</p>
<br>

## 인라인 요소 (Inline Elements)
<p>
  display 속성이 inline으로 지정된 엘리먼트는 전후 줄바꿈 없이 한 줄에 다른 엘리먼트들과 가로로 배치 된다.<br>
  대표적인 inline 엘리먼트로 &lt;span&gt; 이나 &lt;a&gt;, &lt;em&gt; 태그 등을 들 수 있다.
</p>

<p>
  inline 엘리먼트를 사용할 때 주의할 점은, width 와 height 속성을 지정해도 무시된다.<br>
  왜냐하면 해당 태그가 마크업하고 있는 컨텐츠의 크기 만큼만 공간을 차지하도록 되어 있다.<br>
  또한 margin 과 padding 속성은 좌우 간격만 반영되고, 상하 간격은 반영이 되지 않는다.
</p>

### 요약

* 한 줄에 여러 개 배치
* 기본 너비 값은 컨텐츠의 너비 값
* 크기 값을 가질 수 없음
* 상하 마진은 가질 수 없음

<code>span</code>, <code>a</code>, <code>small</code>, <code>big</code>, <code>em</code>, <code>u</code>, <code>ins</code>, <code>i</code>, <code>s</code>, <code>del</code>, <code>br</code>, <code>q</code>,<br>
<code>b</code>, <code>strong</code>, <code>mark</code>, <code>sub</code>, <code>sup</code>, <code>label</code>, <code>map</code>, <code>cite</code>, <code>abbr</code>, <code>time</code>

<p>글자를 개별적으로 꾸미는 서식에 관련된 태그들</p>
<br>

## 블록 요소 (Block Elements)
<p>
  display 속성이 block으로 지정된 엘리먼트는 전후 줄바꿈이 들어가 다른 엘리먼트들을 다른 줄로 밀어내고 혼자 한 줄을 차지한다.<br>
  block 엘리먼트는 inline 엘리먼트와 달리 width, height, margin, padding 속성이 모두 반영된다.
</p>

### 요약

* 한 줄에 한 개만 배치
* 기본 너비 값은 100%
* 크기 값을 가질 수 있음
* 상하좌우 마진 가질 수 있음

<code>div</code>, <code>p</code>, <code>table</code>, <code>blockquote</code>, <code>ul</code>, <code>ol</code>, <code>li</code>, <code>dl</code>, <code>td</code>, <code>dd</code>, <code>table</code>,<br>
<code>tr</code>, <code>td</code>, <code>th</code>, <code>form</code>, <code>hr</code>, <code>h1~h6</code>, <code>header</code>, <code>nav</code>, <code>footer</code>, <code>main</code>,<br>
<code>section</code>, <code>article</code>, <code>aside</code>, <code>figure</code>, <code>figcaption</code>, <code>summary</code>, <code>details</code>, <code>address</code>

<p>
  레이아웃에 관련된 태그들, 목록 태그, 제목 태그, 테이블 관련, 시맨틱(semantic) 태그들
</p>
<br>

## 인라인 블록 (Inline Block Elements) 
<p>
  display 속성이 inline-block 으로 지정된 엘리먼트는 기본적으로 inline 엘리먼트처럼 전후 줄바꿈 없이 한 줄에 가로로 배치 된다.<br>
  block 엘리먼트 처럼 width 와 height 속성 지정 및 margin 과 padding 속성의 상하 간격 지정이 가능하다.<br>
</p>

<p>
  대표적인 inline-block 엘리먼트로 &lt;button&gt; 이나 &lt;input&gt;, &lt;select&gt; 태그 등을 들 수 있다.
</p>

### 요약

* 한 줄에 여러 개 배치
* 기본 너비 값은 컨텐츠의 너비 값
* 크기 값을 가질 수 있음
* 상하좌우 마진 가질 수 있음

<code>img</code>, <code>input</code>, <code>button</code>, <code>textarea</code>, <code>select</code>, <code>Font Icon Tag</code>, <code>video</code>, <code>audio</code>, <code>iframe</code>

<p>
  이미지를 비롯한 대부분의 폼 요소(label은 인라인요소)
</p>
<br>

## flex
<p>
  div container를 flex container(플렉스 컨테이너)라고 부르고, 자식 요소안 div item 들을 flex item(플렉스 아이템) 이라고 한다.
</p>

<p>
  display 속성이 flex 으로 지정된 엘리먼트는 기본적으로 가로 방향으로 배치 된다.<br>
  자신이 가진 컨텐츠의 width 만큼 차지하고, height는 컨테이너의 높이만큼 늘어난다.
</p>
<br>

### inline-flex
<p>
  inline-flex는 inline-block 처럼 동작 한다.
</p>
<br>

### flex-direction
<p>
  아이템들이 배치되는 축의 방향을 결정하는 속성이다.
</p>
<br>

```css
.container {
  flex-direction: row;
  /* flex-direction: column; */
  /* flex-direction: row-reverse; */
  /* flex-direction: column-reverse; */
}
```
<br>

#### row (기본값)
<p>
  아이템들이 행(가로) 방향으로 배치된다.
</p>

#### row-reverse
<p>
  아이템들이 역순으로 가로 배치된다.
</p>

#### column
<p>
  아이템들이 열(세로) 방향으로 배치된다.  
</p>

#### column-reverse
<p>
  아이템들이 역순으로 세로 배치된다.
</p>
<br>

### flex-wrap (줄넘김 속성)
<p>
  컨테이너가 더이상 아이템들을 한 줄에 담을 여유 공간이 없을 때<br>
  아이템 줄바꿈을 어떻게 할지 결정하는 속성이다.
</p>

```css
.container {
  flex-wrap: nowrap;
  /* flex-wrap: wrap; */
  /* flex-wrap: wrap-reverse; */
}
```
<br>

#### nowrap (기본값)

<p>
  줄바꿈을 하지 않는다. overflow 발생
</p>

#### wrap

<p>
  줄바꿈 한다. float이나 inline-block으로 배치한 요소들과 비슷하게 동작.
</p>

#### wrap-reverse

<p>
  줄바꿈을 하는데, 아이템을 역순으로 배치한다.
</p>
<br>

### flex-flow

<p>
  flex-direction과 flex-wrap을 한꺼번에 지정할 수 있는 단축 속성이다.<br>
  direction, wrap의 순으로 사용한다.
</p>

```css
.container {
  flex-flow: row wrap;
  /* 아래의 두 줄을 단축하여 사용 */
  /* flex-direction: row; */
  /* flex-wrap: wrap; */
}
```
<br>

### justify-content

<p>
  메인축 방향으로 아이템들을 정렬하는 속성이다.
</p>

```css
.container {
  justify-content: flex-start;
  /* justify-content: flex-end */
  /* justify-content: center */
  /* justify-content: space-between; */
  /* justify-content: space-around; */
  /* justify-content: space-evenly; */
}
```
<br>

#### flex-start (기본값)

<p>
  아이템들을 시작점으로 정렬한다.<br>
  flex-direction이 row(가로 배치)일 때는 왼쪽, column(세로 배치)일 때는 위.
</p>

#### flex-end

<p>
  아이템들을 끝점으로 정렬한다.<br>
  flex-direction이 row(가로 배치)일 때는 오른쪽, column(세로 배치)일 때는 아래.
</p>

#### center

<p>
  아이템들을 가운데로 정렬한다.
</p>

#### space-between

<p>
  아이템들의 "사이(between)"에 균일한 간격을 만들어 준다.
</p>

#### space-around

<p>
  아이템들의 "둘레(around)"에 균일한 간격을 만들어 준다.
</p>

#### space-evenly

<p>
  아이템들의 사이와 양 끝에 균일한 간격을 만들어 준다.
</p>
<br>

### align-items(수직축 방향 정렬)

<p>
  수직축 방향으로 아이템들을 정렬하는 속성.
</p>

```css
.container {
  align-items: stretch;
  /* align-items: flex-start; */
  /* align-items: flex-end; */
  /* align-items: center; */
  /* align-items: baseline; */
}
```

#### stretch (기본값)

<p>
  아이템들이 수직축 방향으로 끝까지 늘어난다.
</p>

#### flex-start

<p>
  아이템들을 시작점으로 정렬한다.<br>
  flex-direction이 row(가로 배치)일 때는 위, column(세로 배치)일 때는 왼쪽.
</p>

#### flex-end

<p>
  아이템들을 끝으로 정렬한다.<br>
  flex-direction이 row(가로 배치)일 때는 아래, column(세로 배치)일 때는 오른쪽.
</p>

#### center

<p>
  아이템들일 가운데로 정렬한다.
</p>

#### baseline

<p>
  아이템들을 텍스트 베이스라인 기준으로 정렬한다.
</p>
<br>

> [TIP]<br>
> <code>justify-content: center;</code><br>
> <code>align-item: center;</code><br>
> 위와 같이 해주면 아이템을 한 가운데어 놓을 수 있다.
<br>

### align-content (여러 행 정렬)
<p>
  flex-wrap: wrap; 이 설정된 상태에서, 아이템들의 행이 2줄 이상 되었을 때의 수직축 방향 정렬을 결정하는 속성
</p>

```css
.container {
  flex-wrap: wrap;
  align-content: stretch;
  /* align-content: flex-start; */
  /* align-content: flex-end; */
  /* align-content: center; */
  /* align-content: space-between; */
  /* align-content: space-around; */
  /* align-content: space-evenly; */
}
```
<br>

## flex item에 적용하는 속성
<br>

### flex-basis

<p>
  flex-basis는 flex 아이템의 기본 크기를 설정한다.<br>
  flex-direction이 row 일 때는 width, column일 때는 height.
</p>

```css
.item {
  flex-basis: auto;  /* 기본값 */
  /* flex-basis: 0; */
  /* flex-basis: 50% */
  /* flex-basis: 300px */
  /* flex-basis: 10rem; */
  /* flex-basis: content; */
}
```

<p>
  flex-basis의 값으로는 width, height등에 사용하는 각종 단위의 수가 들어갈 수 있고,<br>
  기본값 auto는 해당 아이템의 width값을 사용한다. width를 따로 설정하지 않의면 컨텐츠의 크기가 된다.<br>
  content는 컨텐츠의 크기로, width를 따로 설정하지 않은 경우와 같다.
</p>
<br>

### flex-grow (유연하게 늘리기)
<p>
  flex-grow는 아이템이 flex-basis의 값보다 커질 수 있는지를 결정하는 속성이다.<br>
  0보다 큰 값이 설정되면 해당 아이템이 유연한(flexible) 박스로 변하고 원래의 크기보다 커지며 빈공간을 채운다.
</p>

```css
.item {
  flex-grow: 1;
  /* flex-grow: 0; */ /* 기본값 */
}
```

<p>
  flex-grow에 설정되는 숫자의 의미는 아이템들의 flex-basis를 제외한 여백 부분을 flex-grow에 지정된 숫자의 비율로 나누어 가진다.
</p>

```css
/* 1:2:1의 비율로 설정할 경우 */
.item {
  .item:nth-child(1) { flex-grow: 1; }
  .item:nth-child(2) { flex-grow: 2; }
  .item:nth-child(3) { flex-grow: 1; }
}
```
<br>

### flex-shrink (유연하게 줄이기)
<p>
  flex-shrink는 flex-grow와 쌍을 이루는 속성으로, 아이템이 flex-basis의 값보다 작아질 수 있는지를 결정한다.<br>
  flex-shrink에는 0보다 큰 값이 설정 되면 해당 아이템이 유연한(flexible) 박스로 변하고 flex-basis보다 작아진다.<br>
  기본 값이 1이기 때문에 따로 설정하지 않아도 아이템이 flex-basis보다 작아질 수 있다.
</p>

<p>
  flex-shrink를 0으로 설정하면 아이템의 크기가 flex-bisis보다 작아짖지 않기 때문에 고정폭의 컬럼을 만들 수 있다.<br>
  고정 크기는 width로 설정한다.
</p>
<br>

### flex
<p>
  flex-grow, glex-shrink, flex-basis를 한 번에 쓸 수 있는 축약형 속성이다.  
</p>

```css
.item {
  flex: 1;
  /* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
  flex: 1 1 auto;
  /* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
  flex: 1 500px;
  /* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```
<br>

### align-self (수직축으로 아이템 정렬)

<p>
  수직축 방향을 정렬한다.
</p>

```css
.item {
  align-self: auto;
  /* align-self: stretch; */
  /* align-self: flex-start; */
  /* align-self: flex-end; */
  /* align-self: center; */
  /* align-self: baseline; */
}
```

<p>
  기본값은 auto로 기본적으로 align-items 설정을 상속 받는다<br>
  align-self는 align-tiems보다 우선순위가 높다.
</p>
<br>

### order (배치순서)

<p>
  각 아이템들의 나열 순서를 결정하는 속성이다.<br>
  작은 숫자일 수록 먼저 배치된다.
</p>

```css
.item:nth-child(1) { order: 3; }
.item:nth-child(2) { order: 1; }
.item:nth-child(3) { order: 2; }
```
<br>

### z-index

<p>
  z-index로 Z축 정렬 한다. 숫자가 클수록 위로 올라온다.
</p>

```css
.item:nth-child(2) {
  z-index: 1;
  transform: scale(2);
}
/* z-index의 기본값이 0이므로, 1만 설정해도 위로 올라온다. */
```


