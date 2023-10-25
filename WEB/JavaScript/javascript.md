# JavaScript 기본
<br>

<img src="https://1000logos.net/wp-content/uploads/2020/09/JavaScript-Logo.png" width="300px">
<br>

## 값으로서 함수와 콜백
<br>

### 리턴값으로의 함수의 사용법

```
function cal(mode) {
    var funcs = {
        'plus'  : function(left, right) { return left + right; },
        'minus' : function(left, right) { return left - right; }
    }

    return funcs[mode];
};
alert(cal('plus')(2, 1));
alert(cal('minus')(2, 1));
```
<br>

### 배열으로서의 함수의 사용법

```
var process = [
    function(input) { return input + 10; },
    function(input) { return input * input; },
    function(input) { return input / 2; },
];

var input = 1;
for (var i = 0; i < process.length; i++) {
    input = process[i](input);
}

alert(input);
```
<br>

## 콜백

```
var numbers = [20, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1];
var sortfunc = function(a, b) {    
    return a - b;
}

numbers.sort(sortfunc);
console.log(numbers);

> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 20]
```
* sortfunc은 a가 b보다 크면 양수를 반환
* sortfunc은 a가 b보다 작으면 음수를 반환
* sortfunc은 a가 b와 같으면 0을 반환
<br>

## 클로저
<br>

클로저(closure)는 내부함수가 외부함수의 맥락(context)에 접근할 수 있는 것을 가르킨다.
```
function outter() {
    var title = 'coding everybody';
    return function() {
        alert(title);
    }            
}

inner = outter();
inner();
```
외부함수가 종료된 이후에도 내부함수가 외부함수의 변수에 접근할 수 있다. 이러한 메커니즘을 클로저라고 한다.
<br>

### 내부함수
자바스크립트는 함수 안에서 또 다른 함수를 선언할 수 있다.
<br>

```
function outter() {
  function inner() {
    var title = 'coding everybody';
    alert(title);
  }
  inner();
}

outter();
```
위의 예제에서 내부함수는 외부함수위 지역변수에 잡근할 수 있다.
<br>

### 클로저 예제
Example 1)
```
function factory_movie(title) {            
    return {
        get_title : function () {
            return title;
        }, 
        set_title : function (_title) {
            title = _title;
        }
    }            
}

ghost = factory_movie('Ghost in the shell');
matrix = factory_movie('Matrix');

console.log(ghost.get_title());
console.log(matrix.get_title());

ghost.set_title('공각기동대');

console.log(ghost.get_title());

> Ghost in the shell
> Matrix
> 공각기동대
```
Example 2)
```
var arr = [];

for (var i = 0; i < 5; i++) {
    arr[i] = function(id) {
        return function () {
            return id;
        }
    }(i);
}

for (var index in arr) {
    console.log(arr[index]());
}

> 0
> 1
> 2
> 3
> 4
```
<br>

## arguments
<br>

함수에는 arguments라는 변수에 담긴 숨겨진 유사 배열이 있다. 이 배열에는 함수를 호출할 때 입력한 인자가 담겨있다.

```
function sum() {
    var i, _sum = 0;

    for (i = 0; i < arguments.length; i++) {
        document.write(i + ' : ' + arguments[i] + '<br />');
        _sum += arguments[i];
    }

    return _sum;
}

document.write('result : ' + sum(1, 2, 3, 4));
```
> 0 : 1  
> 1 : 2  
> 2 : 3  
> 3 : 4  
> result : 10
<br>

### 매개변수의 수
<br>

```
function one(arg1) {
    console.log(
        'one.length', one.length,           // 1 함수 정의시 인자 개수
        'arguments', arguments.length       // 2 함수 호출시 입력한 인자 개수
    );
}
one('val1', 'val2');
```
<br>

## apply 사용법
<br>

```
o1 = {val1:1, val2:2, val3:3};
o2 = {v1:10, v2:50, v3:100, v4:25};
function sum() {
    var _sum = 0;

    for (name in this) {
        _sum += this[name];     // var this = o1 or o2
    }

    return _sum;
}

alert(sum.apply(o1));           // 6
alert(sum.apply(o2));           // 185
```
<br>

## 생성자와 new
<br>

### 객체
<p>
객체란 서로 연관된 변수와 함수를 그룹핑한 그릇이라고 할 수 있다. 객체 내의 변수를 프로퍼티(property) 함수를 메소드(method)라고 부른다.
</p>

```
var person = {};

person.name = "Dexter";
person.introduce = function() {
    return 'My name is ' + this.name;
}

document.write(person.introduce());

> My name is Dexter
```

```
var person = {
    'name' : 'Dexter',
    'introduce' : function() {
        return 'My name is ' + this.name; 
    }
};

document.write(person.introduce());

> My name is Dexter
```
<br>

### 생성자
<p>
생성자(constructor)는 객체를 만드는 역할을 하는 함수다.
</p>

```
function Person() {}
var p = new Person();
p.name = 'Dexter';
p.introduce = function() {
    return 'My name is ' + this.name; 
};        

document.write(p.introduce());

> My name is Dexter
```
함수를 호출할 때 new을 붙이면 새로운 객체를 만든 후에 이를 리턴한다.
<br>

## 전역 객체
<p>
전역객체(Global object)는 특수한 객체다. 모든 객체는 이 전역객체의 프로퍼티다.
</p>

```
function func() {
    alert('Hello?');
}
`
func();
window.func();
```

```
var o = {'func':function() {
            alert('Hello?');
        }};

o.func();        
window.o.func();
```
자바스크립트에서 모든 객체는 기본적으로 전역객체의 프로퍼티임을 알 수 있다.
<br>

## this
<p>
함수를 호출했을 때 this는 전역객체인 window와 같다.
</p>

```
function func() {
    if (window === this) {
        document.write("window === this");
    }
}

func();
```
<br>

### 메소드의 호출
<p>
객체의 소속인 메소드이 this는 그 객체를 가르킨다.
</p>

```
var o = {
    'func':function() {
        if (o === this) {
            document.write("o === this");
        }
    }
}

o.func();
```
<br>

### 생성자와 this
<br>

```
var funcThis = null;

function Func() {
    funcThis = this;
}

var o1 = Func();
if (funcThis === window) {
    document.write('window </br>');
}

var o2 = new Func();
if (funcThis === o2) {
    document.write('o2 </br>');
}

> window
> o2
```
<br>

### apply와 this
<br>

```
var o = {};
var p = {};

function func() {
    switch (this) {
        case o:
            document.write('o<br />');
            break;

        case p:
            document.write('p<br />');
            break;

        case window:
            document.write('window<br />');
            break;
    }
}

func();
func.apply(o);
func.apply(p);

> window
> o
> p
```
<br>

## 상속(inheritance)
<p>
상속은 객체의 로직을 그대로 물려 받는 또 다른 객체를 만들 수 있는 기능을 의미한다.
</p>

```
function Person(name) {
    this.name = name;
}

Person.prototype.name = null;
Person.prototype.introduce = function() {
    return 'My name is ' + this.name;
}

function Programmer(name) {
    this.name = name;
}
Programmer.prototype = new Person();
Programmer.prototype.coding = function() {
    return "hello world";
}

var p1 = new Programmer('Dexter');
document.write(p1.introduce() + "<br />");
document.write(p1.coding() + "<br />");

> My name is Dexter
> hello world
```
<br>

