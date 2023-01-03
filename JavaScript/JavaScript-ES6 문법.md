# <div align="center">JavaScript ES6 문법</div>
```
ES란, EXMAScript의 약자이며 자바스크립트의 표준, 규격을 나타내는 용어이다.     
ES6는 2015년에 출시되었다.
```

## 1. let, const 키워드
블록스코프를 가지고 재선언 불가 재할당 가능한 `let` 변수 선언 키워드와 상수 선언 키워드 `const`가 추가되었다.    
기존 var 키워드만 있었을 때 보다 예측 가능한 코드를 작성 할 수 있게 되었다.

> 💡 **블록 스코프**    
블록스코프는 블록( {} ) 내부에서 선언된 변수는 해당 블록에서만 접근 가능한 걸 말한다.    
스코프(scope)는 **변수에 접근할 수 있는 범위를** 말한다.    
전역 스코프(global)는 어디에서든 해당 변수에 접근 가능한 걸 의미한다.    
지역 스코프(local)는 한정적인 범위에서 해당 변수에 접근이 가능하다.    
지역 스코프에는 함수 스코프와 블록 스코프가 있다.


## 2. 템플릿 리터럴
${ } 중괄호 앞 달러 표시를 통해 자바스크립트 표현식 사용이 가능하다.
```javascript
var str1 = ', ';
var str2 = 'World!';

// ES5
var str3 = 'Hello' + str1 + str2;

// ES6
let str3 = `Hello ${str1} ${str2}`;
```    


## 3. 객체 리터럴
* 이전보다 훨씬 간결해진 코드로 객체를 선언할 수 있다.
* 메소드에 더이상 콜론이나 function을 붙히지 않아도 된다.
* 함수명이 겹치는 경우에는 한번만 쓸 수 있다.

```javascript
const myFn = function() {
  console.log('myFn');
};

const text = 'TEXT';

const obj = {
  inside() {
    console.log('객체 안에 바로 함수를 선언');
  },
  myFn,
  [text + 1]: '하나몬'
};

obj.inside(); // 출력값: 객체 안에 바로 함수를 선언
obj.myFn(); // 출력값: myFn
console.log(obj.TEXT1); // 출력값: 하나몬
```


## 4. 화살표 함수
* 함수 표현식을 화살표 함수로 표현할 수도 있다.
* 함수를 간결하게 나타낼 수 있게 되어 가독성 및 유지 보수성이 올라갔다.
* 만약 함수의 본문(body)에 return만 있는 경우 화살표 함수는 **return과 {}를 생략**할 수 있다. (단, 같이 생략해야한다)
* return문에서 소괄호는 사용 가능하다.
```javascript
// ES5
function plusFn(a, b) { 
  return a + b; 
} 

// ES6
// 함수 표현식 - 화살표 함수
const plusFn = (a, b) => {
  return a + b;
}
// 함수 표현식 - 화살표 함수 (생략형)
const plusFn = (a, b) => a + b;
```


## 구조 분해 할당
구조 분해 할당이란 펼치다란 뜻으로 객체나 배열에서 사용한다.    
**값을 해체한 후, 개별 값을 변수에 새로 할당하는 과정**을 말한다.
```javascript
// 배열
const arr = [1, 2, 3];
// 구조 분해 할당을 이용해 one에는 arr[0] / two에는 arr[1] / three에는 arr[2] 를 할당 하였습니다.
const [one, two, three] = arr;

// 배열에 접근하지 않고도 변수로 1,2,3을 사용할 수 있게 됨!
one // 1
two // 2
three // 3


// 객체
const obj = {
 firstName: '양',
 lastName: '혜림'
};

const { firstName, lastName } = obj;
firstName // 양
lastName // 혜림
```

## Promise
* 자바스크립트에서 비동기 처리를 기존에는 콜백 함수를 사용한 콜백 패턴을 사용하였다.
* 결과적으로는 콜백헬을 발생시켰다. (콜백콜백콜백콜백...콜백지옥..)
* 이를 해결하기 위해 프로미스가 도입, 프로미스 후속처림 메소드를 이용해 에러 처리를 효과적으로 할 수 있게 되었다.