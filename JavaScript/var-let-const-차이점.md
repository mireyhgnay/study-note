# <div align="center">✏️ var, let, const 차이점</div>

<br>

## 변수 선언 방식

**`var`**  
변수 선언 방식에 있어서 큰 단점을 가지고 있다.

```javascript
var name = "yanghyerim";
console.log(name); // yanghyerim

var name = "hyerim";
console.log(name); // hyerim
```

변수를 한 번 더 선언했음에도 불구하고, 에러가 나오지 않고 각기 다른 값이 출력된다.  
코드량이 많아 진다면 어디에서 어떻게 사용 될지도 파악하기 힘들뿐더러 값이 바뀔 우려가 있다.  
간단한 테스트할 때면 몰라도 쓰지말자:)  
<br>
그래서 ES6 이후, 이를 보완하기 위해 추가 된 변수 선언 방식이 let 과 const 이다.

<br>

**`let`**  
변수 재선언이 되지 않는다.

```javascript
let name = "yanghyerim";
console.log(name); // yanghyerim

let name = "hyerim";
console.log(name);
// Uncaught SyntaxError: Identifier 'name' has already been declared
// name이 이미 선언 되었다는 에러 메세지
```

위 에러는 const 일 경우에도 마찬가지로 나타난다.

<br>

`let` 과 `const` 둘의 차이점은 **immutable(불변)** 여부이다.  
let 은 변수에 재할당이 가능하다.  
그렇지만, const는 변수 재선언, 변수 재할당 모두 불가능하다.

```javascript
let name = "yanghyerim";
console.log(name); // yanghyerim

let name = "hyerim"; // 재선언
console.log(name);
// Uncaught SyntaxError: Identifier 'name' has already been declared

name = "honggildong"; // 재할당
console.log(name); // honggildong
```

<br>

```javascript
const name = "yanghyerim";
console.log(name); // yanghyerim

const name = "hyerim"; // 재선언
console.log(name);
// Uncaught SyntaxError: Identifier 'name' has already been declared

name = "honggildong"; // 재할당
console.log(name);
//Uncaught TypeError: Assignment to constant variable.
```

<br>

## 호이스팅

호이스팅(Hoisting)이란, var 선언문이나 function 선언문 등을 **해당 스코프의 선두로 옮긴 것처럼 동작하는 특성**을 말한다.

자바스크립트는 ES6에서 도입된 let, const를 포함하여 모든 선언(var, let, const, function, class)을 호이스팅한다.

하지만, var 로 선언된 변수와는 달리 **let 로 선언된 변수를 선언문 이전에 참조하면 참조 에러(ReferenceError)가 발생한다.**

`var`

> 변수는 [선언 단계 > 초기화 단계 > 할당 단계] 에 걸쳐 생성되는데  
> var 는 **선언 단계와 초기화 단계가 한번에 이루어진다.**

```javascript
// 스코프의 선두에서 선언 단계와 초기화 단계가 실행된다.
// 따라서 변수 선언문 이전에 변수를 참조할 수 있다.

console.log(foo); // undefined

var foo;
console.log(foo); // undefined

foo = 1; // 할당문에서 할당 단계가 실행된다.
console.log(foo); // 1
```

`let`

> let 로 선언된 변수는 **선언 단계와 초기화 단계가 분리되어 진행된다.**

```javascript
// 스코프의 선두에서 선언 단계가 실행된다.
// 아직 변수가 초기화(메모리 공간 확보와 undefined로 초기화)되지 않았다.
// 따라서 변수 선언문 이전에 변수를 참조할 수 없다.

console.log(foo); // ReferenceError: foo is not defined

let foo; // 변수 선언문에서 초기화 단계가 실행된다.
console.log(foo); // undefined

foo = 1; // 할당문에서 할당 단계가 실행된다.
console.log(foo); // 1
```

<br>

## 정리

- 변수 선언에는 기본적으로 `const`를 사용하고, 재할당이 필요한 경우에 한정해 `let` 을 사용하는 것이 좋다.
- 재할당이 필요한 경우에 한정해 `let` 을 사용한다. 이때, 변수의 스코프는 최대한 좁게 만든다.
- 재할당이 필요 없는 상수와 객체에는 `const` 를 사용한다.
