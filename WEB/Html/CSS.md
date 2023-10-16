# CSS
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

