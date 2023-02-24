# <div align="center">✏️ operator 연산자</div>

<br>

### 1. String concatenation

```jsx
console.log("my" + "cat"); // my cat
console.log("1" + 2); // 12
// 리터럴문법
console.log(`string literals: 1 + 2 = ${1 + 2}`); // string literals : 1 + 2 = 3
```

<br>

### 2. Numeric operators

```jsx
console.log(1 + 1); // add 더하기
console.log(1 - 1); // substract 빼기
console.log(1 / 1); // divide 나누기(몫)
console.log(1 * 1); // multiply 곱하기
console.log(1 % 1); // remainder 나누기(나머지)
console.log(1 ** 1); // exponentiation 거듭제곱
```

<br>

### 3. Increment and decrement operators

counter++ 와 counter— 같은 원리라고 생각하면 된다.

```jsx
let counter = 2;
const preIncrement = ++counter;
// counter = counter + 1;
// preIncrement = counter;

const postIncrement = counter++;
// postIncrement = counter -> 이미 3이 postIncrement 에 할당되어있음
// counter = counter + 1; -> 3 + 1 = 4

console.log(preIncrement); // 3
console.log(postIncrement); // 4
```

<br>

### 4. Comparision operators

```jsx
console.log(10 < 6);
console.log(10 <= 6);
console.log(10 > 6);
console.log(10 >= 6);
```

<br>

### 5. Logical operators : ||(or), &&(and), !(not)

```jsx
const value1 = true;
const value2 = 4 < 2;

console.log(`or: ${value1 || value2 || check()}`);
console.log(`and: ${value1 && value2 && check()}`);

function check() {
  for (let i = 0; i < 10; i++) {
    console.log("wow");
  }
  return true;
}

// value1 가 true 이므로 그 반대인 false 를 반환한다
console.log(!value1); // false
```

- or
  - value1 을 맨처음 체크하자마자 true이므로 or 은 value1만 체크하고 바로 true를 반환한다.
  - 그래서 최대한 마지막에 체크할 때 or 연산을 수행하는 것이 좋다.
- and
  - 만약 value1이 false 이면 그냥 바로 뒤에 애들은 체크해보지도 않고 false 를 반환한다.
  - 이것또한 or와 같이 마지막으로 체크할때 사용하는 것이 좋다.
- not
  - true ↔ false 반대로 반환한다

<br>

### 6. Equality

```jsx
const stringFive = "5";
const numberFive = 5;

console.log(stringFive == numberFive); // true
console.log(stringFive != numberFive); // false
console.log(stringFive === numberFive); // false (type까지 같아야해)
console.log(stringFive !== numberFive); // true
```

그래서 equality 로 비교할 때는 === 을 사용하는 것이 좋다.

<br>

객체를 비교할 때가 중요하다!

```jsx
const ellie1 = { name: "ellie" };
const ellie2 = { name: "ellie" };
const ellie3 = ellie1;

console.log(ellie1 == ellie2); // false
console.log(ellie1 === ellie2); // false
console.log(ellie1 === ellie3); // true
```

- ellie1과 ellie2 의 객체 안에 value값이 같다고 해도 각각 다른 것으로 구분된다. (각각의 객체!!)
- 그래서 두개를 == 와 === 로 비교하면 둘 다 false 를 출력한다.
- ellie1 과 ellie3이 true인 이유는 1을 3에게 완전히 할당했기 때문에! 똑같은 것임!

<br>

### 7. Conditional operators : if

if, else if, else

```jsx
const name = "df";

if (name === "ellie") {
  console.log("Welcome, Ellie");
} else if (name === "coder") {
  console.log("You are amazing coder");
} else {
  console.log("unkwnon");
}

// unkwnon
```

<br>

### 8. Ternary operator : ?

위 if 문을 더 간단히 바꿔보자  
condition ? value1 : value2;

```jsx
console.log(name === "ellie" ? "yes" : "no"); // no
```

<br>

### 9. Switch statement

```jsx
const browser = "IE";

switch (
  browser // browser 값이 IE면,
) {
  case "IE":
    console.log("go away!");
    break; // IE 콘솔 내용을 실행하고 끝낸다
  case "Chrome":
    console.log("love you!");
    break;
  default:
    console.log("same all!");
    break;
}

// browser가 IE 기 때문에 IE case 에 있는 콘솔로그가 출력된다.
// go away!
```

하나씩 체크하면서 실행되고, true이면 끝낸다(break)

<br>

### 10. Loops : while, for

`while`

```jsx
let i = 3;

// i 가 3부터 시작해서
// i(3) 0보다 크니? true
// i-- 한번 감소시켜서, i(2) 0보다 크니? true
// i-- 한번 감소시켜서, i(1) 0보다 크니? true
// i-- 한번 감소시켜서, i(0) 0보다 크니? false -> 끝
while (i > 0) {
  console.log(`while : ${i}`);
  i--;
}

// while : 3
// while : 2
// while : 1
```

<br>

`for`

위 while문과 동일한 코드를 for문으로 작성해보자면

```jsx
// for(begin; condition; step)
for (let i = 3; i > 0; i--) {
  console.log(`for: ${i}`);
}
```

<br>

퀴즈~

continue, break 사용해서 반복문 돌려보기  
Q1. from 0 to 10 and print only even(홀수) numbers (use continue)

```jsx
for (let i = 0; i < 11; i++) {
  if (i % 2 !== 0) {
    continue;
  }
  console.log(i); // 1 3 5 7 9
}
```

<br>

Q2. from 0 to 10 and print numbers until reaching 8 (use break) 8 초과되면 끝내기

```jsx
for (let i = 0; i < 11; i++) {
  if (i > 8) {
    break;
  }
  console.log(i); // 12345678
}
```
