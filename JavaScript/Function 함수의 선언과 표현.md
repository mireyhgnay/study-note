# <div align="center">✏️ Function 함수의 선언과 표현</div>

<br>

## Function

```javascript
function printHello() {
  console.log("hello");
}
printHello();
```

기본적으로 함수는 이런식의 구문으로 쓰이지만,  
위 함수의 경우 hello 만 찍어낼 수 있는 비효율적인 함수이다.

<br>

```javascript
function printHello(message) {
  console.log(message);
}
printHello("hello");
```

이렇게 파라미터(message)를 추가하여 그 값을 받아 유연하게 사용할 수 있다.

<br>

대신 자바스크립트의 단점은 타입을 구분하지 않는다는 것!

```javascript
printHello(1234);
```

1234 라고 적어도 숫자가 잘 출력된다.  
number 와 string 타입에 상관없이 출력이되서 좋을 수도 있지만,  
실제로 사용할 때 타입에 중요도가 높은 함수를 생성할 때 자바스크립트의 단점이 될 수 있다.  
따로 타입을 설정하는 기능이 없기때문에!!

<br>

그래서 **`TypeScript`** 가 등장~~~!!

```typescript
function printHello(message: string) {
  console.log(message);
}
```

이런식으로 파라미터에 타입을 설정해줄 수 있다.

<br>

## Parameters

오브젝트는 레퍼런스로 전달되기 때문에 함수안에서 object 값을 변경하게 되면 그 변경된 사항이 그대로 메모리에 적용이 됩니다.

```jsx
function changeName(obj) {
  obj.name = "coder";
}

const ellie = { name: "ellie" }; // 객체 생성
chageName(ellie); // 함수로 obj.name 을 변경할 수 있다.
console.log(ellie); // name : 'coder'
```

<br>

### Default parameters (added in ES6)

파라미터의 초기값을 설정해주는 것! ES6 에 새로 추가됐다.

```jsx
function showMessage(message, from = "unknown") {
  console.log(`${message} by ${from}`);
}

showMessage("Hi!"); // Hi by unknown
```

from 을 따로 설정해주지 않을 경우 unknown 으로 출력될 수 있도록 초기값을 설정해줄 수 있다.  
예전에는 if 문을 사용해서 `if(from === undefined)` 일 경우 unknown 으로 출력해달라고 구문을 통해서 번거롭게 작성해줘야 했는데 이제는 간단하게 초기값을 설정해 줄 수 있다.

<br>

### Rest parameters (add in ES6)

배열을 파라미터로 넣어서 함수를 생성할 수 있다.

```jsx
function printAll(...args) {
  for (let i = 0; i < args.length; i++) {
    console.log(args[i]);
  }
}

printAll("dream", "coding", "ellie"); // dream coding ellie
```

<br>

## Local scope

```
밖에서는 안이 보이지 않고 안에서만 밖을 볼 수 있다.
```

<br>

```javascript
let global = "global";
function printMessage() {
  let message = "hello";
  console.log(message); // local variable
  console.log(global); // global

  function printAnother() {
    console.log(message);
    let childMessage = "hello";
  }
  console.log(childMessage); // error
}

printMessage();
```

<br>

## Arrow Function

함수 블록 안에 많은 실행 코드가 들어가지 않는 간단한 리턴 코드라면 화살표함수로 적어주면 좋다.

```javascript
const add = (a, b) => a + b;
```

<br>

## IIFE : Immediately invoked Function Expression

함수를 () 로 묶어주고 끝에 (); 를 붙혀주면 따로 함수를 별도로 호출하지 않아도 바로 호출해준다.  
요즘엔 잘 사용하지 않는다:)

```javascript
(function hello() {
  console.log("IIFE");
})();
```
