2장 자바스크립트
==============

## const 상수 사용
```javascript
var pizza = true;
pizza = false;
console.log(pizza); // false
```
```javascript
var pizza = true;
pizza = false; // Uncaught TypeError
```

## let 구문적인 변수 영역 규칙
```javascript
var topic = "javascript";
if (topic) {
    var topic = "react";
    console.log(topic); // react
}
console.log(topic); // react
```
```javascript
var topic = "javascript";
if (topic) {
    let topic = "react";
    console.log(topic); // react
}
console.log(topic); // javascript
```

## 템플릿 문자열
```javascript
console.log(lastName + ", " + firstname + ", " + middlename);
console.log(`${lastname}, ${firstname}, ${middlename}`);
```

## 함수
```javascript
// 함수 선언, 선언전에 사용해도 무방
function() {
    console.log("잘했어요");
}
logCompliment();

// 함수 표현식, 선언전에 사용하면 에러
const logCompliment = function() {
    console.log("잘했어요");
}
logCompliment();

// 디폴트 파라미터
function logActivity(name="조현욱", activity="테니스") {
    console.log(`${name}은 ${activity}를 좋아합니다.`);
}

//다양한 타입 사용 가능
const defaultPerson = {
    name : {
        first : "현욱",
        last : "조"
    },
    favActivity: "Crossfit"
};

function logActivity(p=defaultPerson) {
    console.log(`${p.name.first}은 ${favActivity}를 좋아합니다.`);
}

// 화살표 함수

```
