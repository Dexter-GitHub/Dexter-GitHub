# GIT 자주쓰는 명령어 모음
</br>

* GitHub를 사용할 경우 GitHub에서 새로운 repository를 생성한 후 repository의 https URL을 이용한다.
</br>

### 초기화 및 GitHub repository 연결
```
$ git init
$ git clone {REPO URL} {DIR}
```
📌 DIR은 생략 가능하다.
</br>

### Staged area로 관리될 파일(수정 또는 생성) 이동
```
$ git add {file name}
  or
$ git add . (전체파일)
```
</br>

### branch
<br>

branch 생성
```
$ git branch {name}
  or
$ git checkout -b {name}
```
</br>

branch 간의 이동
```
$ git checkout {branch}
  or
$ git switch {branch}
```
</br>

branch 이름 변경
* local 저장소
```
$ git branch -m [OLD_BRANCH] [NEW_BRANCH]
```
* GitHub 저장소
```
$ git push origin [NEW_BRANCH]
$ git push origin --delete [OLD_BRANCH]

or

$ git push origin :[OLD_BRANCH]

or

$ git push origin :[OLD_BRANCH] [NEW_BRANCH]    /* 삭제와 동시에 생성 */
```

### stash (tracked 파일에 대해서만 적용 되는 특성을 가지고 있다)
* commit전 작업내용은 branch 이동시 작업내용이 공유 됨으로 작업중인 상태를 저장하는 용도로 사용된다.
```
$ git stash
  or
$ git stash save
```
</br>

* stash 목록 확인 (가장 최근 Stash 항목이 0번이다)
```
$ git stash list
```
</br>

* stash된 작업내용을 복구
```
$ git stash apply  
```
</br>

* stash된 항목 삭제 (가장 최근 Stash 항목이 삭제 된다)
```
$ git stash drop
```
</br>

* Stash된 작업내용을 복구와 동시에 항목 삭제
```
$ git stash pop
```
</br>

### pull or fetch
> fetch는 원격저장소의 최신내역을 가져오지만 로컬저장소의 log 히스토리는 업데이트 하지 않는다.
> 이점은 로컬저장소와 원격저장소의 차이점을 확인하는데 도움이 된다.
```
$ git fetch
```
> fetch 명령어 이후 merge하여 커밋 히스토리를 원격저장소와 로컬저장소가 병합될 수 있도록 해야한다.
</br>

```
$ git pull
```
> pull은 fetch와 같이 원격저장소의 최신내역을 가져오고 커밋 히스토리 merge까지 해준다.
</br>

### tag
> tag는 현재버전의 release 버전을 만들거나 특정한 태그를 커밋버전에 등록할 수 있다.
</br>

* light weight tag
```
$ git tag {branch|hash}
```
</br>

* annnotated tag
```
$ git tag -a -m "message string" {branch|hash}
```
</br>

* 원하는 tag로 커밋 이동하기
```
$ git checkout {tagName}
```
</br>
