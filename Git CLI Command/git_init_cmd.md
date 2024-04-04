# GIT 초기 설정 with GitHub

* GitHub 리포지토리 생성
* 프로젝트 폴더에서 Git 초기화

```
  $ git init
```
<br>

* GitHub 리모트 저장소 추가

```
  $ git remote add origin {HTTPS or SSH URL}
```
<br>

> <code>orgin</code> 키워드는 저장소 이름 정도로 해석될 수 있다.<br>
> GitHub에서 default 설정으로 origin 키워드가 많이 사용되며, 다른 키워드로 변경해서 사용할 수 있다.

* GitHub에서 생성된 README.md 파일 또는 초기 설정한 파일을 프로젝트 폴더에 pull 한다.

```
  $ git pull origin main
```
<br>

> main은 GitHub에서 default 설정으로 생성된 branch 이며,<br>
> 예전에는 master 키워드로 많이 사용되었지만, 인종차별적인 단어이므로 main을 주로 사용한다.
