# json

## 코어 json
데이터 티입, 값의 타입으로 구성된다. 
- 키-값
- 객체
- 배열

값의 타입은 아래와 같다. 
- ojbect
- array
- string
- number
- boolean
- null

json에는 특별히 주석이 없다.

## json 스타일 가이드
대표적으로 google json 스타일 가이드가 있다.

[구글코딩가이드](https://google.github.io/styleguide/jsoncstyleguide.xml)

## json 설계
json을 작성할 때 좀더 손쉽게 작성할 수 있는 웹사이트들이 있다.  
[json editor](https://jsoneditoronline.org/#right=local.terapi&left=local.defidi)  
[json-gernerator](https://json-generator.com/)


## api 배포하기
back-end 서버가 없이 api를 테스트하고 설계할 수 있는 많은 tool들이 존재한다.

### json-sever
설치는 npm을 이용해서 설치한다. 
```bash
npm install json-server
```
사용방법은 테스트 할 json을 만들고 아래과 같이 서버를 실행한다.
```bash
npx json-server -p 5000 speakers.json
```
### postman
api를 쉽게 개발하고 관리할 수 있는 툴  
*api를 개발하게 된다면 사용법을 습득해야겠다.*

- [ ] npx에 대해 알아볼 것





