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

<img src=../images/googleJsonsStyleGuide.png width=700>

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



## json schema
json 문서의 내용, 구조, 형식을 규정하기 위한 것이다.  
단순하게 문법적 유효성을 검사하는 것이 아니라 의미를 검사할 수 있다.  
schma를 사용하는 이유는 아래와 같다. 
- 보안성
- 메시지 설계: 발신측과 수신측이 완전히 분리되어 있는 메시징 시스템
- API 설계: 구조를 결정하면서 API의 규약을 정의할 수 있다.
- 프로토타이핑

## ujs-jsonvalidate
local에서 json schema를 이용해서 json의 유효성을 검사하는 툴이다.  
nmp을 통해 설치 가능하다.
```bash
npm inatsll -g ujs-jsonvalidate
```
사용방법은 아래와 같다. 
```bash
validate basic.json schema.json 
```

## 예제
*```배열```, ```열거형```, ```객체``` 등 다양한 방법으로 schema를 구성할 수 있다.  
필요시 찾는 방향으로 하고 본 예제의 설명은 생략한다.*
```json
{
    "speaker": {
        "email": "yes.chung89@gmail.com",
        "firstName":"chung",
        "lastName":"yoon",
        "postedSlides":true,
        "rating": 2,
        "tags":["Java"]
    }
}
```
```json
{
    "$schema": "http://json-schema.org/draft/2019-09/schema",
    "type": "object",
    "properties": {
        "speaker": {
            "type": "object",
            "properties" :{
                "email": {
                    "type": "string"
                },
                "firstName": {
                    "type": "string"
                },
                "lastName": {
                    "type": "string"
                },
                "postedSlides": {
                    "type": "boolean"
                },
                "rating": {
                    "type": "number",
                    "minimum":0.0,
                    "maximum":5.0
                },
                "tags": {
                    "type": "array",
                    "minItems":1,
                    "maxItems":4,
                    "items": {
                        "enum": [
                            "Open Source", "Java", "JSON"
                        ]
                    }
                }
            },
            "required": [ "email", "firstName", "lastName", "postedSlides", 
                "rating", "tags" ],
            "additionalProperties": false
        }
    },
    "required" :["speaker"],
    "additionalProperties": false
}
```
