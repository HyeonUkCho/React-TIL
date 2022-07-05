1장 리액트 소개
==============

## 파일 저장소
- [깃저장소](https://github.com/moonhighway/learning-react)
- [한글판깃저장소](https://github.com/enshahar/learning-react-kor/tree/seconded)
- 리액트 개발자 도구 (크롬, 사파리 다운로드 필요)

## 설치 및 환경 구성

1. 노드 설치
```bash
node -v 
```

2. npm
- 노드 패키지 관리자.
- 여러 패키지를 설치하기 위해 npm을 사용함.
- package.json 의존성 파일이 있는 디렉토리에서 npm install을 실행하면 의존성을 모두 설치 시켜줌.
- package.json 파일 생성
```bash
npm init -y
```
```bash
npm install [package-name]
```
```bash
npm remove [package-name]
```

3. 대안으로 yarn이 있다.
- npm에 전역 옵션을 주어 yarn 설치한다.
```bash
npm install -g yarn
```
- yarn.lock 파일이 있는 프로젝트가 바로 얀을 사용하는 프로젝트이다.
- npm install 명령과 비슷하게 프로젝트 디렉토리 안에서 yarn을 실행하면 프로젝트의 모든 의존 관계를 설치할 수 있다.