
# HTML 자주쓰는 태그 모음
<img src="https://github.com/Dexter-GitHub/Dexter-GitHub/assets/31064322/6190ab8c-1bb6-4732-b7a7-46b7b2edf1eb"
  width=150>

## HTML 기본
<br />

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    ...meta data
  </head>
  <body>
    ...content
  </body>
</html>
```
<br />

## 링크
<br />

```
<a href="url" title="설명" target="문서가 로드될 대상">컨텐츠</a>
```
* href: 링크이름과 연결되어 있는 리소스(resource)의 주소
* title: 연결되어 있는 리소스에 대한 설명, 롤오버 했을 때 툴팁으로 표시된다.
* target: 문서가 로드될 대상으로 아래와 같은 것들이 있다.
  
  * _self: 현재의 문서가 로드된 프래임, 현재 문서 사라짐
  * _blank: 새로운 창(탭)을 띄우고 거기에 문서를 로드
  * _parent: 현재 문서가 frame나 iframe에 로드된 경우 현재 문서를 로드한 프래임에 문서를 로드
  * 프래임의 이름
<br />

## 문단 (paragraph)
<br />

```
<p>문단</p>
```
<br />

## 줄바꿈 (line break)
<br />

```
문장<br />
```
<br />

## 띄어쓰기
<br />

> 스페이스 키를 누르면 눈에 보이지 않지만 space 문자가 입력된다.  
> HTML에서는 스페이스 문자는 한번만 인정된다. 이럴 때 &amp;nbsp; 기호를 사용한다.
```
문장&nbsp;문장
```
<br />

## 이미지 삽입
<br />

```
<img src="URL" alt="대체텍스트" width="폭" height="높이" longdesc="링크" />
```
* src: source의 약자로 이미지가 위치하는 URL을 기술한다.
* alt: alternative의 약자로 한국어로는 대체 텍스트라고 부른다. 이미지가 로딩되기 전이나,  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;이미지를 로딩할 수 없는 경우 이미지의 위치에 텍스트가 표시된다.  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;시각장애인을 위한 장치와 검색엔진에서도 사용된다.
* width, heiht: 이미지의 크기
* longdesc: 이미지와 관련된 링크

#### 설명
* 이미지를 로드해서 화면에 표시함
* alt는 대체 텍스트를 활용해서 시각장애인, 저사양, 저속도 사용자, 이미지가 유실되는 상황에 대비해야 함.
<br />

## 목록
<br />

순서가 없는 리스트(Unordered List)
```
<ul>
  <li>항목</li>
</ul>
```

순서가 있는 리스트(Ordered List)
```
<ol>
  <li>항목</li>
</ol>
```

#### 설명
* 연관되어 있는 항목들을 나열할 때 사용
* 순서가 없는 항목은 ul(unordered list), 순서가 있는 항목은 ol(ordered list)를 사용한다.
* CSS와 함께 사용해서 메뉴로도 사용된다.
<br />

## iframe
<br />
페이지안에 페이지를 삽입한느 방법이며, 예를들어 홈페이지 내용에 유튜브를 삽입하고자 한다면  
iframe을 이용하는 것이다.
<br />

```
<iframe src="URL" scrolling="스크롤링 허용여부(yes|no|auto)">
iframe를 지원하지 않는 브러우저인 경우 대체정보를 제공
</iframe>
```
* src: 불러올 페이지의 URL
* scrolling: 아이프래임 안에서 스크롤링을 허용할 것인지를 지정
  * auto: 스크롤이 필요한 경우만 스크롤 바를 노출 (기본 값)
  * yes: 스크롤링 허용, 스크롤이 필요 없는 경우도 스크롤 바를 노출
  * no: 스크롤 하지 않음
> 참고: width, height, frameborder(프래임의 테두리 사용여부) 등의 속성이 더 있지만, 디자인에 대한 부분은 CCS를  
> 통해서 제어하는 것이 권장된다.
<br />

## 이스케이핑
<br />
HTML 코드는 브라우저에 의해서 해석되는 약속된 문자들이다. 예를들어 줄바꿈을 의미하는 &lt;br /&gt; 태그를 줄바꿈의 용도가  
아니라 화면에 표시하려면 ?

```
<!DOCTYPE html>
<html>
  <body>
    <br />은 줄바꿈을 의미하는 태그입니다.
  </body>
</html>
```

&lt;br /&gt; 태그는 줄바꿈으로 해석되기 때문에 화면에 표시되지 않을 것이다. 이럴 때 사용하는 방법이 이스케이핑(escaping)이다.  

```
<!DOCTYPE html>
<html>
  <body>
    &lt;br /&gt;은 줄바꿈을 의미하는 태그입니다.
  </body>
</html>
```

```
주요한 이스케이코 코드는 아래와 같다. (출처: 위키피디아)

* &amp; -> & (ampersand, U+0026)
* &lt;  -> < (less-than sign, U+003C)
* &gt;  -> > (greater-than sign, U+003E)
* &quot; -> " (quotation mark, U+0022)
* &apos; -> ' (apostrophe, U+0027)
```
<br />

## 표
<br />
table, 표는 데이터를 일복요연하게 표현하기 위한 방법이다.


```
<table>
  <tr>
    <th>제목</th>
  </tr>
  <tr>
    <td>데이터</td>
  </tr>
</table>
```
<br />

## HEAD
<br />

&lt;head&gt; 태그는 문서를 설명하는 태그들이 위치하는 태그다. &lt;body&gt; 태그가 웹페이지가 담아내려는 정보  
그 자체라면 head 태그는 body 태그의 정보를 설명하는 메타 정보라고 할 수 있다.

### Meta ?
문서에 대한 정보를 기술하는 태그

```
<meta name="" content="" />
<meta http-equive="" content="" />
```
<br />

### title ?
문서의 제목을 정의하는 마크업. 제목을 표시줄에 출력해서 문서를 찾는데 도움을 준다. 검색엔진에서  
중요한 정보로 취급된다.

```
<!DOCTYPE html>
<html>
    <head>
        <title>제목</title>
    </head>
    <body>
    내용....
    </body>
</html>
```
<br />


## 폼 (form)
<br />
폼이란 사용자의 데이터를 서버에 전송하는 방법이다. 일반적으로 아래와 같은 작업을 하기 위해서는 폼을 이용한다.
* 로그인을 위해서 아이디/비밀번호를 입력할 때
* 회원가입을 하기 위해서 개인정보를 입력할 때
* 블로그나 게시판에 글을 작성하거나, 파일을 전송할 때

```
<form action="서버로 전송한 데이터를 수신할 URL" method="데이터를 전송하는 방법">
  텍스트 필드, 라디오 버튼, 체크 박스와 같은 컨트롤을 생성하는 태그
</form>
```
* action: 사용자가 입력한 데이터를 전송할 서버의 URL
* method: 사용자가 입력한 데이터를 전송하는 방법으로 아래와 같은 방식이 있다.
  * get: action에 입력한 URL에 파라미터의 형태로 전송
  * post: header의 body에 포함해서 전송
<br />

### GET
  * URL에 정보가 담겨서 전송된다.
  * 전송할 수 있는 정보의 길이가 제한되어 있다.
  * 퍼머링크로 사용될 수 있다.
<br />

### POST
  * header의 body에 담겨서 전송된다.
  * URL 상에 전달한 정보가 표시되지 않는다.
  * GET에 비해서 보안상 약간의 우위에 있다. (사실상 동일하다)
  * 전송할 수 있는 데이터의 길이 제한이 없다.
  * 서버 쪽에 어떤 작업을 명령할 때 사용한다. (데이터의 기록, 삭제, 수정 등)
<br />

## 텍스트 필드
<br />
사용자로부터 텍스트를 입력 받는다. 한줄 정도의 단문에 적당하고 긴 줄의 텍스트는 <textarea>를 이용한다.

```
<input type="text" name="값의 이름" value="값" disabled="disabled" readonly="readonly" />
```
* type: text를 사용해야 텍스트 필드가 된다.
* name: 입력한 데이터의 이름
* value: 데이터의 값. 입력한 데이터의 기본 값으로 이 값이 기본적으로 텍스트 필드에 표시된다.
* disabled: 값으로 disabled을 지정하면 텍스트 필드가 불능 상태가 된다. 서버로 전송해도 이 속성이 설정된 컨트롤의 데이터는
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;서버로 전송되지 않는다.
* readonly: 값으로 readonly를 지정하면 텍스트 필드에 값이 입력되지 않는다. 서버로는 데이터가 전송된다.
<br />

### 비밀번호 
보안이 중시되는 데이터의 입력을 받는다.

```
<input type="password" name="password" />
```
<br />

### hidden data
화면상에 표시되지 않는 컨트롤을 생성한다. 서버로 전달할 데이터이지만 사용자에게는 노출될 필요가 없는 데이터인 경우 사용한다.

```
<input type="hidden" name="language" />
```
<br />

## textarea
<br />

여러줄의 텍스트 입력 할 때 사용한다.
```
<textarea name="값의 이름" rows="행의 수" cols="열의 수" disabled="disabled" readonly="readonly">값</textarea>
```
* rows: 입력한 행위 수 만큼 높이가 정해진다.
* cols: 입력한 열의 수 만큼 폭이 정해진다.
<br />

## 선택
<br />

### 라디오 버튼
<br />

여러개의 항목 중에서 하나만의 선택 할 수 있도록 제한하는 컨트롤
```
<input type="radio" name="값의 이름" value="값" checked="checked">
```
<br />

### 콤보박스
<br />

여러개의 항목 중에서 원하는 것을 하나만 선택하는 컨트롤로 흔히 콤보박스라고 부른다.
```
<select name="값의 이름" multiple="multiple">
  <option value="선택될 경우 name의 값이 됨" selected="selected">값에 대한 표시값</option>
  ...option 반복
</select>
```
* multiple: 이 속성의 값을 multiple로 지정하면 여러개의 항모을 선택할 수 있는 컨트롤이 된다.
<br />

### 체크 박스
<br />

여러개의 항목 중에서 원하는 것을 복수로 선택할 수 있게 하는 컨트롤로 체크박스라고 부른다.
```
<input type="checkbox" name="값의 이름" value="값" />
```
* checkbox는 여러개늬 값을 같은 이름으로 전송해야 하기 때문에 연관된 항목들의 name 값을 같은 이름으로 지정한다.
* name의 이름 끝에 '[]'를 붙이면 서버 쪽에서 실행되는 언어가 이 값을 배열로 인지한다.
<br />

## 파일 전송
<br />

업로드할 파일을 선택할 수 있는 커트롤을 생성
```
<input type"file" name="서버쪽에서 파일을 식별하기 위한 이름" />
```
<br />


