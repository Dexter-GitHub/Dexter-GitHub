# GIT 경고 케이스별 해결법
<br>

## LF will be replaced by CRLF the next time Git touched it
<br>

> 번역: 다음에 Git이 LF를 건드릴 때 LF는 CRLF로 대체 됩니다.

### LF (Line-Feed)

* Mac, Linux(Unix 계열) 줄바꿈 문자열 = \n
* 커서 위치는 그대로 두고 종이의 한라인 위로 올리는 동작
* 현재 위치에서 바로 아래로 이동

### CR (Carriage-Return)
* Mac 초기 모델 줄바꾼 문자열 = \r
* 커서 위치를 맨앞으로 옮기는 동작
* 커서 위치를 앞으로 이동

### CRLF (Carriage-Return+Line-Feed)
* Windows, DOS 줄바꿈 문자열 = \r\n
* CR(\r) + LR(\n) 두동작을 합침
* 커서를 다음라인 맨앞으로 옮겨주는 동작
<br>

## 해결 방안
<br>

<p>
  <code>core.autocrlf = true</code><br><br>
  LF > CRLF 변경
  <br>
  
  <code>core.autocrlf = false</code><br><br>
  OS에 상관없이 줄바꿈에 대한 문자열 그대로 인식해 저장
</p>

#### Windows, DOS 명령어

```
$git config --global core.autocrlf true(or false)  /* 시스템 전체 적용 (--global) */
```

#### Linux, Mac 명령어

```
$git config --global core.autocrlf input  /* 시스템 전체 적용 (--global) */
```
