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

## 커밋 메시지 수정
<br>

* 아래 명령을 사용하여 가장 최근의 커밋 메시지를 변경할 수 있다.

```
  $ git commit --amend
```

* VI 에디터에서 커밋 메시지를 편집하고 커밋을 저장한다.
* 변경 내용을 GitHub로 푸시할 준비가 되면 아래 명령을 사용하여 이전 커밋을 강제로 푸시한다.

```
  $ git push --force origin {branch name}
```
<br>

## Window terminal 에서 git bash 사용
</br>

* windows terminal 설치
```
C:\> winget install --id=Microsoft.WindowsTerminal -e
```
> windows terminal 실행 명령어는 Win+R wt 이다.
</br>

* windows terminal 설정
> Ctrl + , 를 입력하여 설정탭을 열고 Json 파일 열기를 선택한다.
> settings.json 파일내용중 "profiles" 리스트에 아래 코드를 추가한다.
```
"profiles":
{
  "defaults": {},
  "list":
  [
    ...
    {
        "guid": "{124fc1da-dadc-4276-9c4e-f0524ba57a49}",
        "name": "Git Bash",
        "commandline": "\"%PROGRAMFILES%\\git\\usr\\bin\\bash.exe\" -i -l",
        "icon": "%PROGRAMFILES%\\git\\mingw64\\share\\git\\git-for-windows.ico",
        "startingDirectory": "%USERPROFILE%",
        "cursorShape": "filledBox",
        "hidden": false
    }
  ]
},
```
</br>

* 우클릭 숏컷 생성
> sttings.json 파일에 아래와 같이 "startingDirectory"를 추가한다.
```
"profiles":
{
    "defaults":
    {

    },
    "list":
    [
        {
            // Make changes here to the powershell.exe profile.
            "guid": "{61c54bbd-c2c6-5271-96e7-009a11ff44bf}",
            "name": "Windows PowerShell",
            "commandline": "powershell.exe",
            "hidden": false,
                            // Here!!!
            "startingDirectory": "."
        }
    ]
},
```
</br>

> wt.reg 파일을 생성한 후 아래 코드를 삽입하고 저장 한다.
> wt.reg 파일을 우클릭하여 병합을 선택 한다.
```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt]
 @="Open Windows Terminal here"

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt\command]
 @="C:\\Users\\{UserName}\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe"
```
</br>
