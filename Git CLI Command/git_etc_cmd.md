# GIT 기타 설정 명령어
</br>

## Windows 환경에서 Beyound Compare mergetool 환경설정 (Beyond Compare 4)
</br>

Beyound Compare Dowload Link : <https://www.scootersoftware.com/download>
  
</br>

* GIT golbal config 설정
```
$ git config --global merge.tool bc

$ git config --global mergetool.bc.path "C:/Program Files/Beyond Compare 4/BComp.exe"
```
</br>

* merge 중에 CONFLICT 충돌이 발생한 경우 아래 명령을 통해 Beyound Compare 연동하여 확인할 수 있다.
```
$ git mergetool {file name}
```
</br>

## GIT 원격 저장소 생성 및 remote 등록
</br>

* git 원격저장소 생성 (저장소 폴더)
 ```
$ git init --bare {fold name}
 ```
</br>

* git 원격 저장소 등록 (작업 폴더)
```
$ git remote add origin {저장소 folder name}
```
> origin은 저장소의 별명
</br>

## GIT SSH 접속
</br>

* pc ssh key 생성
```
$ ssh-keygen
```
> 위 명령어 실행시 표시되는 id_rsa/id_rsa.pub 파일의 경로를 참고 한다.   
> private key는 local PC에 사용되고, public key는 원격 저장소 Server PC에 사용된다.
> GitHub 사용시 Setting > SSH and GPG keys에 public key를 등록하여 사용한다.
</br>

