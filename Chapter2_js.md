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
```
```javascript
// 함수 표현식, 선언전에 사용하면 에러
const logCompliment = function() {
    console.log("잘했어요");
}
logCompliment();
```
```javascript
// 디폴트 파라미터
function logActivity(name="조현욱", activity="테니스") {
    console.log(`${name}은 ${activity}를 좋아합니다.`);
}
```
```javascript
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
```
```javascript
// 화살표 함수
const lordify = firstname => `캔터베리의 ${firstname}`;
```
```javascript
// param 여러개 전형적인
var lordify = function(firstname, land) {
    return `${land}의 ${firstname}`;
}

// param 여러개 화살표 함수
var lordify = (firstname, land) => `${land}의 ${firstname}`;
console.log(lordify("조현욱", "브리즈번")); // 브리즈번의 조현욱
```

```javascript
// 객체반환, 괄호로 둘러싸야하는 것을 잊지말자
const person = (firstname, lastname) => ({
    first: firstname,
    last: lastname,
});
```

```javascript
// 레거시 자바스크립트에서의 클래스
function Vacation(destination, length) {
    this.destination = destination;
    this.length = length;
}

Vacation.prototype.print = function() {
    console.log(this.destination + "은(는) " + this.length + " 일 걸립니다.);
}

const maui = new Vacation("Maui", 7);
maui.print(); // Maui은(는) 7 일 걸립니다.
```
```javascript
// ES2015 이후
class Vacation {

    constructor(destination, length) {
        this.destination = destination;
        this.length = length;
    }
    
    print() {
        console.log(`${this.destination} 은(는) ${this.length} 일 걸립니다.`);
    }
}

const trip = new Vacation("Maui", 7);
trip.print(); // Maui은(는) 7 일 걸립니다.

// 상속

class Expedition extends Vacation {

    constructor(destination, length, gear) {
        super(destination, length);
        this.gear = gear;
    }

    print() {
        super.print();
        console.log(`당신의 ${this.gear.join("와(과) 당신의 ")}를 가져오십시오.`);
    }
}
```

```javascript
export const print(message) => log(message, new Date());
export const log(message, timestamp) => console.log(`${timestamp.toString()} : ${message}`);

const freel = new Expedition("freel mountain", 2, ["식수","간식"]);
export default freel;


//사용
import {print, log} from './text-helpers';
import freel from './mt-freel';

print('메시지를 print');
log('message log');

freel.print();
```