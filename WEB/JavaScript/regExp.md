# 정규표현식 
<br>

## 패턴 만들기
<br>

```
var pattern = /a/;
or
var pattern = new RegExp('a');
```

## 패턴 찾기
<br>

```
var pattern = /a/;
pattern.exec('abcde');
> ['a']
```

```
var pattern = /a/;
pattern.test('abcde');
> true
```

## String 에서 정규 표현식 사용
<br>

```
var pattern = /a/;
var str = "abcdef";
str.match(pattern);
> ["a"]
```

```
var pattern = /a/;
var str = "abcdef";
str.replace(pattern, 'A');
> Abcdef
```

## 정규표현식 대소문자 구분X 옵션
<br>

```
var oi = /a/i   // i 옵션은 대소문자를 구분 하지 않도록 한다.
"Abcdef".match(oi);
> ["A"]
```

## 정규표현식 해당하는 모든 문자 찾기
<br>

```
var og = /a/g;
"abcdea".match(og);
> ["a", "a"]
```

## 캡처
<br>

```
var pattern = /(\w+)\s(\w+)/;  // w는 문자를 의미 하고, +는 하나 이상을 의미 한다.
var str = "coding everybody";
str.replace(pattern, "$2, $1");
> everybody coding
```
