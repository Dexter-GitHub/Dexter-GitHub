# GIT 자주쓰는 명령어 모음
</br>
GitHub를 사용할 경우 GitHub에서 새로운 repository를 생성한 후 repository의 https URL을 이용한다.

* 초기화 및 GitHub repository 연결
```
$ git init
$ git clone origin {REPO URL} 
```
</br>

* Staged area로 관리될 파일(수정 또는 생성) 이동
```
$ git add {file name}
  or
$ git add . (전체파일)
```
</br>

* branch 생성
```
$ git branch {name}
  or
$ git checkout -b {name}
```
</br>

* branch 간의 이동
```
$ git checkout {branch}
  or
$ git switch {branch}
```
</br>

* Stash (tracked 파일에 대해서만 적용 되는 특성을 가지고 있다)
> commit전 작업내용은 branch 이동시 작업내용이 공유 됨으로 작업중인 상태를 저장하는 용도로 사용된다.
```
$ git stash
  or
$ git stash save
```
</br>

> Stash 목록 확인 (가장 최근 Stash 항목이 0번이다)
```
$ git stash list
```
</br>

> Stash된 작업내용을 복구
```
$ git stash apply  
```
</br>

> Stash된 항목 삭제 (가장 최근 Stash 항목이 삭제 된다)
```
$ git stash drop
```
</br>

> Stash된 작업내용을 복구와 동시에 항목 삭제
```
$ git stash pop
```
</br>
