# Grid
<br>

<p>
  div container를 Grid Container(그리드 컨테이너)라고 부르고,<br>
  자식 요소인 div item들을 Grid Item(그리드 아이템)이라고 부른다.
</p>

<p>
  Grid는 컨테이너에 display: grid; 를 설정하는 것으로 시작한다.
</p>

```css
.container {
  display: grid;
}
```
<br>

* 그리드 컨테이너 (Grid Container)
  
<p>
  &emsp;&emsp; <code>display: grid</code>를 적용하는, Grid의 전체 영역이다.<br>
  &emsp;&emsp; Grid 컨테이너 안의 요소들이 Grid 규칙의 영향을 받아 정렬 된다.
</p>

* 그리드 아이템 (Grid Item)
  
<p>
  &emsp;&emsp; Grid 컨테이너의 자식 요소들 이다.   
</p>

* 그리드 트랙 (Grid Track)
  
<p>
  &emsp;&emsp; Grid의 행(Row) 또는 열(Column)
</p>

* 그리드 셀 (Grid Cell)
  
<p>
  &emsp;&emsp; Grid의 한 칸을 가리킨다. 
</p>

* 그리드 라인 (Grid Line)
  
<p>
  &emsp;&emsp; Grid 셀을 구분하는 선이다.
</p>

* 그리드 번호 (Grid Number)
  
<p>
  &emsp;&emsp; Grid 라인의 각 번호이다.
</p>

* 그리드 갭 (Grid Gap)
  
<p>
  &emsp;&emsp; Grid 셀 사이의 간격이다.
</p>

* 그리드 영역 (Grid Area)
  
<p>
  &emsp;&emsp; Grid 라인으로 둘러싸인 사각형 영역으로, 그리드 셀의 집합니다.
</p>

<p>
   Grid의 속성들은 컨테이너에 적용하는 속성, 아이템에 적용하는 속성으로 나뉜다. 
</p>
<br>

## grid-template-rows / frid-template-columns (그리드 형태 정의)

<p>
  컨테이너에 Grid 트랙의 크기들을 지정해주는 속성이다.<br>
  여어가지 단위를 사용할 수 있고 섞어서 쓸 수도 있다.
</p>

```css
.container {
  grid-template-columns: 200px 200px 500px;
  /* grid-template-columns: 1fr 1fr 1fr; */
  /* grid-template-columns: repeat(3, 1fr) */
  /* grid-template-columns: 200px 1fr */
  /* grid-template-columns: 100px 200px auto */

  gird-template-rows: 200px 200px 500px;
  /* grid-template-rows: 1fr 1fr 1fr; */
  /* grid-template-rows: repeat(3, 1fr); */
  /* grid-template-rows: 200px 1fr; */
  /* grid-template-rows: 100px 200px auto; */
}
```
<br>

* grid-template-rows는 행(row)의 배치
* grid-template-columns는 열(column)의 배치

### repeat 함수

```css
.container {
  grid-template-columns: repeat(5, 1fr);
  /* grid-template-columns: 1fr 1fr 1fr 1fr 1fr; */
}
```

<p>
  repeat는 반복되는 값을 자동으로 처리할 수 있는 함수이다.<br>
  <strong>repeat(반복횟수, 반복값)</strong><br>
  repeat(3, 1fr 4fr 2fr); 이런 식의 패턴도 가능하다.
</p>
<br>

### minmax 함수
<p>
  최소값과 최대값을 지정할 수 있는 함수이다<br>
  <strong>minmax(100px, auto)</strong>의 의미는 <strong>최소한 100px, 최대는 자동으로 늘어남</strong> 이다.
</p>

```css
.container {
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, minmax(100px, auto));
}
```
<br>

### auto-fill 과 auto-fit
<p>
  auto-fill 과 auto-fit은 column의 개수를 미리 정하지 않고 설정된 너비가 허용하는 한 최대한 셀을 채운다.
</p>

```css
.container {
  grid-template-columns: repeat(auto-fill, minmax(20%, auto));
}
```

<p> 
  auto-fill의 크기를 20% 설정하면 공간이 남게 된다.<br>
  auto-fill 대신 auto-fit을 사용하면, 남은 공간을 채운다.
</p>
<br>

## row-gap / column-gap / gap (간격 만들기)
<p>
  그리드 셀 사이의 간격을 설정한다.
</p>

```css
.container {
  row-gap: 10px;
  /* row의 간격을 10px로 */
  column-gap: 20px;
  /* column의 간격을 20px로 */
}
```

```css
.container {
  gap: 10px 20px;
  /* row-gap: 10px; column-gap: 20px; */
}
```

```css
.container {
  gap: 20px;
  /* row-gap: 20px; column-gap: 20px; */
}
```

<p>
  초기에는 앞에 grid- 를 붙여서 grid-gap, grid-row-gap, grid-column-gap 이었는데,<br>
  블라우저 호환 범위를 넓히기 위해 아래처럼 이전 버전의 이름을 둘다 쓰기도 한다.
</p>

```css
.container {
  grid-gap: 20px;
  gap: 20px;
}
```
<br>

## grid-auto-columns / grid-auto-rows (그리드 형태를 자동으로 정의)
<p>
   grid-template-columns(또는 grid-template-rows)의 통제를 벗어난 위치에 있는 트랙의 크기를 지정하는 속성이다.
</p>

```css
.container {
  grid-template-rows: repeat(3, minmax(100px, auto))
}
```

<p>
위 코드에서 repeat 횟수를 3으로 지정하였다. 그런데 row 개수를 미리 알 수 없는 경우면,<br>
아래 코드와 같이 grid-auto-rows를 사용한다.
</p>

```css
.container {
  grid-auto-rows: minmax(100px, auto);
}
```
<br>

## 각 셀의 역역 지정
<br>

* grid-column-start
* grid-column-end
* grid-column
* grid-row-start
* grid-row-end
* grid-row

<p>
  이 속성들은 Grid 아이템에 적용하는 속성으로, 각 셀의 영역을 지정한다.
</p>

```css
.item:nth-chold(1) {
  grid-column-start: 1;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 2;
}
```

<p>
  grid-column은 start와 end 속성을 한번에 쓰는 축약형이다.
</p>

```css
.item:nth-child(1) {
  grid-column: 1 / 3;
  grid-row: 1 / 2;
}
```

<p>
  시작번호 / 끝번호를 지정하는 방법 외에, 몇 개의 셀을 차지하게 할 것인지를 지정해줄 수 있다.
</p>

```css
.item:nth-child(1) {
  /* 1번 라인에서 2칸 */
  grid-column: 1 / span 2;
  /* 1번 라인에서 3칸 */
  grid-row: 1 / span 3;
}
```
<br>

## grid-template-areas (영역 이름으로 그리드 정의)

<p>
  각 영역(Grid Area)에 이름을 붙이고, 그 이름을 이용해서 배치하는 방법이다.
</p>

```css
.container {
  grid-template-areas:
      "header header header"
      "  a     main    a   "
      "  .      .      .   "  /* 빈칸 */
      "footer footer footer"
}
```

<p>
  위의 형태로 각자 차지하는 셀의 개수만큼 해당 위치에 이름을 쓰면 된다.<br>
  각 셀마다 공백을 하나씩 넣어서 구분해준다.<br>
  빈칸은 마침표 또는 "none"을 사용하면 된다.
</p>

```css
.header { grid-area: header; }
.sidebar-a { grid-area: a; }
.main-content { grid-area: main; }
.sidebar-b { grid-area: b; }
.footer { grid-area: footer; }
/* 이름 값에 따옴표가 없는것에 주의 */
```
<br>

## grid-auto-flow 자동 배치

<p>
  아이템이 자동 배치되는 흐름을 결정하는 속성이다.
</p>

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(25%, auto));
  grid-template-rows: repeat(5, minmax(50px, auto));
  grid-auto-flow: dense;  /* 빈 셀을 채우는 옵션 */
}
item:nth-child(2) { grid-column: auto / span 3; }
item:nth-child(5) { grid-column: auto / span 3; }
item:nth-child(7) { grid-column: auto / span 2; }
```
<br>

## align-items (세로 방향 정렬)
<p>
  아이템들을 세로(column축) 방향으로 정렬한다. 컨테이너에 적용.
</p>

```css
.container {
  align-items: stretch;
  /* align-items: start; */
  /* align-items: center; */
  /* align-items: end; */
}
```
<br>

## justify-items (가로 방향 정렬)

<p>
  아이템들을 가로(row 축) 방향으로 정렬한다. 컨테이너에 적용한다.
</p>

```css
.container {
  justify-items: stretch;
  /* justify-items: start; */
  /* justify-items: center; */
  /* justify-items: end; */
}
```
<br>

### place-items

<p>
  align-items와 justify-items를 같이 쓸 수 있는 단축 속성이다.<br>
  align-items, justify-items의 순서로 작서하고, 하나의 값만 쓰면 두 속성 모두에 적용 된다.
</p>

```css
.container {
  place-items: center start;
}
```
<br>

## align-content (아이템 그룹 세로 정렬)

<p>
  Grid 아이템들의 높이를 모두 합한 값이 Grid 컨테이너의 높이보다 작을 때 Grid 아이템들을 통째로 정렬한다.
</p>

```css
.container {
  align-content: stretch;
  /* align-content: start; */
  /* align-content: center; */
  /* align-content: end; */
  /* align-content: space-between; */
  /* align-content: space-around; */
  /* align-content: space-evenly; */
}
```
<br>

## justify-contemt (아이템 그룹 가로 정렬)

<p>
  Grid 아이템들의 너비를 모두 합한 값이 Grid 컨테이너의 너비보다 작을 때 Grid 아이템들을 통째로 정렬한다.
</p>

```css
.container {
  justify-content: stretch;
  /* justify-content: start; */
  /* justify-content: center; */
  /* justify-content: end; */
  /* justify-content: space-between; */
  /* justify-content: space-around; */
  /* justify-content: space-evenly; */
}
```
<br>

### palce-content

<p>
  align-content와 justify-content를 같이 쓸 수 있는 단축 속성이다.<br>
  align-content, justify-contnent의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용된다.
</p>

```css
.container {
  palce-content: space-between center;
}
```
<br>

## align-self (개별 아이템 세로 정렬)

<p>
  해당 아이템을 세로(column축) 방향으로 정렬한다. 아이템에 적용한다.
</p>

```css
.item {
  align-self: stretch;
  /* align-self: start; */
  /* align-self: center; */
  /* align-self: end; */
}
```
<br>

## justify-self (개별 아이템 가로 정렬)

<p>
  해당 아이템을 가로 (row축) 방향으로 정렬한다. 아이템에 적용한다.
</p>

```css
.item {
  justify-self: stretch;
  /* justify-self: start; */
  /* justify-self: center; */
  /* justify-self: end; */
}
```
<br>

### place-self

<p>
  align-self와 justify-self를 같이 쓸 수 있는 단축 속성이다.<br>
  align-self, justify-self의 순서로 작성하고, 하나의 값만 쓰면 두 속성 모두에 적용된다.
</p>

```css
.item {
  place-self: start center;
}
```
<br>

## order (배치순서)

<p>
  각 아이템들의 시각적 나열 순서를 결정하는 속성이다.<br>
  숫자값이 들어가며, 작은 숫자일 수록 먼저 배치된다.
</p>

```css
.item:nth-child(1) { order: 3; }
.item:nth-child(2) { order: 1; }
.item:nth-child(3) { order: 2; }
```
<br>

## z-index

<p>
  z-index로 Z축 정렬을 할 수 있다. 숫자가 클 수록 위로 올라온다.
</p>

```css
.item:nth-child(5) {
  z-index: 1;
  transform: scale(2);
}
/* z-index를 설정 하지 않으면 0이므로, 1만 설정해도 다른 아이템보다 위로 올라온다.
```

|표준|IE|
|----|--|
|display:geid;|display: -ms-grid;|
|grid-template-rows|-ms-grid-rows|
|grid-tempalte-columns|-ms-grid-columns|
|grid-row-start|-ms-grid-row|
|grid-column-start|-ms-grid-column|
|grid-row: 1 / span 2; 에서 span 2|-ms-grid-row-sapn: 2|
|grid-column: 1 / span 2; 에서 span 2|-ms-grid-column-sapn: 2|
|align-self|-ms-grid-row-align|
|justify-self|-ms-grid-column-align|






