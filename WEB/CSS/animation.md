# CSS 트랜지션
<br>

* transition: 모든 transition 속성을 이용한 스타일을 한 줄에 설정할 수 있음
* transition-property: 요소에 추가할 전환 (transition) 효과를 설정
* transition-duration: 전환 (transition) 효과가 지속될 시간을 설정
* transition-timing-function: 전환 (transition) 효과의 속도를 설정
* transition-delay: 전환 (transition) 효과가 나타나기 전까지의 지연 시간을 설정
<br>

### transition-property

<p>
  트랜지션의 대상이 되는 CSS 프로퍼티명을 지정한다. 지정하지 않은 경우 모든 프로퍼티가 트랜지션의 대상이 된다.<br>
  복수의 프로퍼티를 지정하는 경우 쉼표(,)로 구분한다.
</p>

<p>
  주의해야 할 사항은 모든 CSS 프로퍼티가 트랜지션의 대상이 될 수 없다는 것이다.<br>
  트랜지션의 대상이 될수 있는 CSS 프로퍼티는 아래와 같다.
</p>

#### box model

* width, height, max-width, max-height, min-width, min-height
* padding, margin
* border-color, border-width, border-spacing

#### background

* background-color, background-position

#### 좌표

* top, left, right, bottom

#### 텍스트 

* color, font-size, font-weight, letter-spacing, line-height
* text-indent, text-shadow, vertical-align, word-spacing

#### etc

* opacity, outline-color, outline-offset, outline-width
* visibility, z-index

### transition-duration

<p>
  트랜지션에 일어나는 지속시간(duration)을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다.<br>
  프로퍼티값을 지정하지 않을 경우 기본값 0s이 적용되어 어떠한 트랜지션 효과도 볼 수 없다.<br>
  transition-duration 프로퍼티값은 transition-property 프로퍼티 값과 1:1 대응한다.
</p>

### transition-timing-function

<p>
  트랜지션 효과의 변화 흐름, 시간에 따른 변화 속도와 같은 일종의 변화의 리듬을 지정한다.
</p>

* ease: 기본값.느리게 시작하여 점점 빨라졌다가 느려지면서 종료한다.
* linear: 시작부터 종료까지 등속 운동을 한다.
* ease-in: 느리게 시작한 후  일정한 속도에 다다르면 그 상태로 등속 운동한다.
* ease-out: 일정한 속도의 등속으로 시작해서 점점 느려지면서 종료한다.
* ease-in-out: ease와 비슷하게 느리게 시작하여 느려지면서 종료한다.

### transition-delay

<p>
  트랜지션 발동 대기시간. 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정 한다.<br>
  transition-duration이 트랜지션 지속 시간이라면, transition-delay는 발동 대기 시간이다.
</p>

### transition

<p>
  모든 트랜지션 프로퍼티를 한번에 지정할 수 있는 shorthand이다. 값을 지정하지 않은 프로퍼티에는 기본값이 지정된다.
</p>

```css
transition: property duration function delay
  기본값      all       0       ease     0
```
<br>

# CSS 트랜스폼
<br>

<p>
  트랜스폼(transform)은 요소에 이동(translate), 회전(rotate), 확대/축소(scale), 비틀기(skew) 효과를 부여해 준다.
</p>

### 2D Transform

<p>
  기본 x, y두 좌표로만 요소를 변화 시켜 2d적인 변화를 가미할 수 있다.
</p>

* translate(x, y): 요소의 위치를 X축으로 x만큼, Y축으로 y만큼 이동시킨다. (px, %, em 등)
* translateX(n): 요소의 위치를 X축으로 x만큼 이동시킨다. (px, %, em 등)
* translateY(n): 요소의 위치를 Y축으로 y만큼 이동시킨다. (px, %, em 등)
* scale(x, y): 요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 시킨다. (0과 양수)
* scaleX(n): 요소의 크기를 X축으로 x배 확대 또는 축소 시킨다. (0과 양수)
* scaleY(n): 요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다. (0과 양수)
* skew(x-angle, y-angle): 요소를 X축으로 x각도 만큼, Y축으로 y각도만큼 기울인다. (+/- 각도 deg)
* skewX(x-angle): 요소를 X축으로 x각도만큼 기울인다. (+/- 각도 deg)
* skewY(y-angle): 요소를 Y축으로 y각도만큼 기울인다. (+/- 각도 deg)
* rotate(angle): 요소를 angle만큼 회전시킨다. (+/- 각도 deg)
<br>

### 3D Transform

<p>
  x, y, z 세 좌표를 이용해 요소를 변화 시켜 3d적인 변화를 가미할 수 있다.
</p>

* translate3d(x, y, z): 요소의 위치를 X축으로 x만큼, Y축으로 y만큼, Z축으로 z만큼 이동시킨다. (px, %, em 등)
* translateX(n): 요소의 위치를 X축으로 x만큼 이동시킨다. (px, %, em 등)
* translateY(n): 요소의 위치를 Y축으로 y만큼 이동시킨다. (px, %, em 등)
* translateZ(n): 요소의 위치를 Z축으로 z만큼 이동시킨다. (px, %, em 등)
* scale3d(x, y): 요소의 크기를 X축으로 x배, Y축으로 y배 확대 또는 축소 시킨다. (0과 양수)
* scaleX(n) 요소의 크기를 X축으로 x배 확대 또는 축소 시킨다. (0과 양수)
* scaleY(n) 요소의 크기를 Y축으로 y배 확대 또는 축소 시킨다. (0과 양수)
* scaleZ(n) 요소의 크기를 Z축으로 z배 확대 또는 축소 시킨다. (0과 양수)
* rotate3d(x, y, z): 요소를 X축으로 x각도, Y축으로 y각도, Z축으로 z각도 회전시킨다. (+/- 각도 deg)
* rotateX(x): 요소를 X축으로 x각도 회전시킨다. (+/- 각도 deg)
* rotateY(y): 요소를 Y축으로 y각도 회전시킨다. (+/- 각도 deg)
* rotateZ(z): 요소를 Z축으로 z각도 회전시킨다. (+/- 각도 deg)

### transform 

<p>
  변환함수를 프로퍼티값으로 쉽표없이 나열한다. 나열 순서에 따라 차례대로 효과가 적용된다.
</p>

```css
transform: func1 func2 func3 ...;
```
<br>

### transform-origin

<p>
  요소의 기본기준점을 설정할 때 사용된다. 기본 기준점은 요소의 정중앙이다. (50%, 50%)<br>
  설정값으로 %, px, top, left, bottom, right을 사용할 수 있다. 
</p>
<br>

# CSS 애니메이션

<p>
  애니메이션(animation)속성은 말 그대로 html 요소에 애니메이션 효과를 적용시켜 준다.<br>
  애니메이션을 적용하기 위해선 특별한 속성이 쓰여 지는데 이를 @keyframes 이라 한다. 애니메이션은 하나의 줄거리(keyframes)를 
  구성하여 줄거리 내에서 세부 움직임을 시간 흐름 단위로 제어하여 요소의 움직임을 표현한다.
</p>

* 일반적으로 트랜지션 효과는 요소 프로퍼티값이 다른 값으로 변화할 때 주로 사용하며 요소의 로드와 함께 자동으로 발동되지 않는다.
* anmation 프로퍼티는 하나의 줄거리를 구성하여 줄거리 내에서 세부 움직임을 시간 흐름 단위로 제어 할 수 있고 전체 줄거리의 재생과 정지, 반복까지 제어할 수 있다.
<br>

### Animation 속성

* animation-name: @keyframes 애니메이션 이름을 지정한다.
* animation-duration: 한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다. (0s)
* animation-timing-function: 애니메이션 효과를 위한 타이밍 함수를 지정한다. (ease)
* animation-iteration-count: 애니메이션 재생 횟수를 지정한다. (1)
* animation-fill-mode: 애니메이션 미실행 시 (종료 또는 대기) 요소의 스타일을 지정한다.
* animation-play-state: 애니메이션 재생 상태(재생 또는 중지)를 지정한다. (running)
* animation: 모든 애니메이션 프로퍼티를 한번에 지정한다.
<br>

### @keyframes

<p>
  CSS 애니메이션과 트랜지션 방식의 차이는 @keyframes rule에 있다.<br>
  이 rule을 사용하면 애니메이션의 흐름(sequence)중의 여러 시점(breakpoint)에서 CSS 프로퍼티값을 지정할 수 있다.
</p>

<p>
  @keyframes rule은 시간의 흐름에 따라 애니메이션을 정의한다. 여러 개의 키프레임을 정의하거나 애니메이션 중에 특정 CSS 프로퍼티에 값을 지정하는 지점을 정의할 수 있다.
</p>

```css
@keyframes move {
  from {  /* 애니메이션 시작 지점 */
    left: 0;
  }
  to {    /* 애니메이션 종료 시점 */
    left: 300px;
  }
}
/* from, to 키워드를 사용하여 애니메이션의 시작과 끝 시점을 정의하였다.
   정지 상태에서 오른쪽으로 300px 이동하는 애니메이션이 실행 된다. */
```

```css
  div {
    position: absolute;
    width: 100px;
    height: 100px;
    background-color: red;

    animation-name: move;                   /* @keyframes에 지정한 이름 */
    animation-duration: 5s;                 /* 애니메이션 동작 시간 */
    animation-iteration-count: infinite;    /* 애니메이션 재생 횟수 무한 */
  }
```

<p>
  from, to 키워드 대신 상세한 조작을 위해 퍼센티지(%)도 사용할 수 있다.
</p>

```css
@keyframes move {
  0%   { left: 0 }
  50%  { left: 100px; }
  100% { left: 300px; }
}
```
<br>

### animation-name

<p>
  이름을 animation-name 프로퍼티 값으로 지정하여 사용하고자 하는 @keyframes rule을 선택한다. 하나 이상의 애니메이션 이름을 지정할 수 있다.
</p>

### animation-duration

<p>
  한 싸이클의 애니메이션에 소요되는 시간을 초 단위(s) 또는 밀리 초 단위(ms)로 지정한다.<br>
  animation-duration은 반드시 지정되어야 한다. 지정하지 않은 경우 기본값 0s가 설정되어 어떠한 애니메이션도 실행하지 않는다.
</p>

```css
animation-duration: .5s;
animation-duration: 500ms;
```
<br>

### animation-timing-function

<p>
  애니메이션 효과를 위한 수치 함수를 지정한다.
</p>

### animation-delay

<p>
  애니메이션 실행 대기 시간
</p>

```css
animation-delay: 2s;
```

### animation-iteration-count

<p>
  애니메이션 주기의 재생 횟수를 지정한다. 기본값은 1이며 infinite로 무한반복 할 수 있다.
</p>

```css
animation-iteration-count: 3;
```

### animation-direction

<p>
  애니메이션이 종료된 이후 반복될 때 진행하는 방향을 지정한다.
</p>

* normal: 기본값으로 from (0%) 에서 to (100%) 방향으로 진행한다.
* reverse: to 에서 from 방향으로 진행한다.
* alternate: 홀수번째는 normal로 짝수번째는 reverse로 진행한다.
* alternate-reverse: 홀수번째는 reverse로 짝수 번째는 normal로 진행한다.

```html
<head>
  <style>
    div {
      width: 100px;
      height: 100px;
      background: red;
      position: relative;
      animation: myAnimation 5s infinite;
      /* 홀수 번째는 normal로, 짝수 번째는 reverse로 진행 */
      animation-direction: alternate;
    }
    @keyframes myAnimation {
      0%   { background: red;    left: 0px;   top: 0px; }
      25%  { background: yellow; left: 200px; top: 0px; }
      50%  { background: blue;   left: 200px; top: 200px; }
      75%  { background: green;  left: 0px;   top: 200px; }
      100% { background: red;    left: 0px;   top: 0px; }
    }
  </style>  
</head>
<body>
  <div></div>
</body>
```
<br>

### animation-fill-mode

<p>
  애니메이션 미실행 시(대기 또는 종료) 요소의 스타일을 지정한다.
</p>

|프로퍼티값|상태|설명|
|-----------|----|-----|
|none       |대기|시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기 한다.|
|           |종료|애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.|
|forwards   |대기|시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기한다.|
|           |종료|종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.|
|backwards  |대기|시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.|
|           |종료|애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.|
|both       |대기|시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.|
|           |종료|종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.|
<br>

### animation-play-state

<p>
  애니메이션 재생 상태(재생 또는 중지)를 지정한다. 기본값은 running 이다.
</p>

```css
animation-play-state: paused;
animation-play-state: running;
```
<br>

### animation

<p>
  모든 애니메이션 프로퍼티를 한번에 지정한다. 값을 지정하지 않은 프로퍼티에는 기본값이 지정된다.
</p>

```css
animation: name duration timing-function delay iteration-count driection fill-mode play-state
  기본값   none    0          ease         0          1          normal     none    running
```
<br>
