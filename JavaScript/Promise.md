# <div align="center">✏️ Promise</div>

<br>

```
자바스크립트는 동기적이다.
호이스팅(변수, 함수 선언이 상단으로 올라감)이 된 이후부터 코드가 내가 작성한 순서대로 동기적으로 실행이 된다.
```

<br>

## Promise란?

- Promise는 자바스크립트 안에 내장되어있는 객체이다.
- 비동기적인 것을 수행할때 콜백함수 대신에 유용하게 쓸 수 있는 오브젝트이다.
- state, producer(정보 제공자) 와 consumer(정보 소비자) 차이를 이해해야한다.

<br>

## 콜백지옥이란?

콜백함수 안에서 다른 콜백함수를 계속 부르는 코드

- 가독성이 떨어짐
- 디버깅 어려움
- 유지보수 어려움

## 1. producer : Promise 만들기

프로미스는 class이기 때문에 new 키워드를 통해 객체를 생성한다.

```jsx
const promise = new Promise((resolve, reject) => {
  setTime(() => {
    resolve("ellie"); // 성공했을 때 resolve 수행
    reject(new Error("no network")); // 실패했다면 reject 수행
  }, 2000);
});
```

- resolve 함수 : 기능을 정상적으로 수행해서 마지막에 최종 데이터를 전달한다.
- reject 함수 : 기능을 수행하다가 중간에 문제가 생기면 호출한다.
- **프로미스가 생성된 순간 executor라는 callback 함수가 바로 실행되기 때문에 이 점에 유의하면서 코드를 작성해야 한다**
  - 만약에 사용자가 요구하는 경우에만 네트워크 요청이 이루어져야하는 경우라면(ex. 버튼 클릭시 네트워크 요청)
    위에처럼 그냥 작성햇을 때는 사용자가 요청하지 않았을 때도 불필요한 통신이 일어날 수 있다.

<br>

## 2. Consumers : Promise 사용하기

then, catch, finally 를 사용해서 값을 받아올 수 있습니다.

```jsx
promise
	// resolve - then
	.then(value => { // then을 사용해서 성공적인 경우를 실행
		console.log(value);
	});
	// reject - catch
	.catch(error => {
		console.log(error); // 실패했을 때 reject 실행해줌
	});
	// finally
	.finally(() => {
		console.log('finally'); //
	});
```

- `resolve - then` : 프로미스가 정상적으로 수행되어서 마지막으로 resolve 콜백함수로 전달된 값이 value 로 들어온다. ⇒ resolve가 ellie 라는 값을 전달하는 것
- `reject - catch` : 프로미스 내부에서 실행되는 일이 실패하였을 때는 reject 를 호출한다.
  - then 만 있으면 바로 에러가 발생한다.
  - catch 로 에러 발생시 어떻게 처리할건지에 대한 콜백함수를 등록해주어야한다.
- `finally` : 성공,실패와 상관없이 finally는 무조건 마지막에 호출된다.

<br>

## 3. Promise 연결하기

- then은 값을 전달할 수도 있고 promise 를 전달할 수도 있다.
- then을 묶어서 여러 비동기적인 애들을 사용할 수 있습니다.

```jsx
const fetchNumber = new Promise((resolve, reject) => {
  setTimeout(() => resolve(1), 1000); // 1초 뒤 resolve 실행
});

fetchNumber
  .then((num) => num * 2) // 1 * 2 = 2
  .then((num) => num * 3) // 2 * 3 = 6
  .then((num) => {
    // 새로운 프로미스 생성
    return new Promise((resolve, reject) => {
      // 여기서 또 1초, 총 2초
      setTimeout(() => resolve(num - 1), 1000); // 6 - 1 = 5
    });
  })
  .then((num) => console.log(num)); // 2초 뒤 5로 출력됨
```

<br>

## 4. Error Handling

```jsx
const getHen = () =>
  new Promise((resolve, reject) => {
    setTimeout(() => resolve("🥚"), 1000);
  });

const getEgg = (hen) =>
  new Promise((resolve, reject) => {
    setTimeout(() => resolve(`${hen} => 🐔`), 1000);
  });

const cook = (egg) =>
  new Promise((resolve, reject) => {
    setTimeout(() => resolve(`${egg} => 🍳`), 1000);
  });

getHen() //
  .then(getEgg)
  .then(cook)
  .then(console.log);
```

result :  
🥚 => 🐔 => 🍳

<br>

```jsx
const getHen = () =>
  new Promise((resolve, reject) => {
    setTimeout(() => resolve("🥚"), 1000);
  });

const getEgg = (hen) =>
  new Promise((resolve, reject) => {
    setTimeout(() => reject(new Error(`error! ${hen} => 🐔`)), 1000);
  });

const cook = (egg) =>
  new Promise((resolve, reject) => {
    setTimeout(() => resolve(`${egg} => 🍳`), 1000);
  });

getHen() //
  .then(getEgg)
  .then(cook) //then으로 전달 받은 value로 다른 함수를 호출할 때는 (egg => cook(egg)) 로 안 써도 됨
  .catch(console.log)
  .then(console.log);
```

result :  
Uncaught (in promise) Error: error! 🥚 => 🐔
at <anonymous>:8:29
