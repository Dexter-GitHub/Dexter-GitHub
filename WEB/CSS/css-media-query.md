# Media query 사용법
<br>

#### 기본 문법
<p>
  미디어 쿼리는 CSS에서 어떤 스타일을 선택적으로 적용하고 싶을 때 사용한다<br>
  다른 프로그래밍 언어의 <code>if</code> 조건문과 비슷한 개념이다.
</p>

<p>
  <code>@media</code> 키워드로 시작하는 미디어 쿼리의 문법 구조는 아래와 같다.
</p>
<br>

```css
@media (조건) {
  스타일
}
```
<br>

```css
@media 미디어-타입 and(미디어-특성) {
  // 해당 미디어 요소에서 적용할 CSS
}
```
<br>

<p>
  미디어 타입이란 화면을 출력할 미디어가 tv인지 스크린인지 등을 말한다.<br>
  종류로는 screen, tv, print, projection 등이 있는데 디스플레이를 가진 미디어 대부분은<br>
  <code>screen</code>에 속하기 때문에 이를 많이 사용한다. 모든 미디어 타입을 일컽는 <code>all</code>을 써도 된다.
</p>

<p>
  미디어 특성에는 width, height, device-width, device-height, orientation 등이 있다.<br>
  orientation은 미디어가 세로모드인지 가로모드인지를 구분한다.
</p>

<p>
  max-width는 화면의 최대 값을 설정하며 min-width는 반대로 화면의 최소값을 설정 한다.
</p>

```css
@media all and (max-width: 2024px) {
  // 브라우저 창 width가 1024px 보다 작아지는 순간부터 적용
  // 태블릿
}

@media all and (max-width: 768px) {
  // 브라우저 창 width가 768px 보다 작아지는 순간부터 적용
  // 모바일
}

@media all and (min-width: 768px) {
  // 브라우저 창 width가 768px 보다 커지는 순간부터 적용
  // 태블릿
}

@media all and (min-width: 2024px) {
  // 브라우저 창 width가 1024px 보다 커지는 순간부터 적용
  // 데스크탑
}
```
<br>









