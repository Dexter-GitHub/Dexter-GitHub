# React 설치 (create-react-app)
</br>

```
$ npm -g create-react-app
```
</br>

* 작업환경 폴더 생성 후 해당 경로에서 아래 명령어 실행
```
$ create-react-app .
```
</br>

* React 실행 (작업환경 경로)
```
$ npm run start
```
</br>

* Deploy시 빌드 명령어
```
$ npm run build
```
> 명령어 실행시 build 폴더가 생성되고 서비스 시작시 build 폴더에 있는 파일 사용하면 된다.
> build 폴더내에 생성된 파일은 개발시 사용된 리소스양 보다 경량화 된다.
</br>

* 웹서버 실행 serve 설치 및 실행
```
$ npm install -g serve
or
$ npx serve -s build

$ serve -s build
```
