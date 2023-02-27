# <div align="center">✏️ Object</div>

## Object

- 자바스크립트 타입의 일종
- 관련있는 데이터나 함수의 묶음
- `{ key : value }` ⇒ key와 value 의 집합체

<br>

## Literals and properties

- object literal ⇒ {} 증괄호 사용
  ```jsx
  const obj1 = {};
  ```
- object constructor : new 키워드 사용
  ```jsx
  const obj2 = new Object();
  ```
- 나중에 property 추가 가능
  ```jsx
  obj.plus = "+";
  ```
- 나중에 property 삭제도 가능
  ```jsx
  delete obj.plus;
  ```

<br>

## object 안의 값을 접근하는 방법

```jsx
console.log(me.name); // value 값 출력
console.log(me["name"]); // key는 string type으로 지정해야됨
```

<br>

## property value shorthand

key와 value 의 이름이 동일하면 생략 가능하다

```jsx
function makePerson(name, age) {
  return {
    name, // name: name
    age, // age: age
  };
}
```

<br>

## Constructor Function

```jsx
function Person(name, age) {
  this.name = name;
  this.age = age;
}
```

<br>

## for .. in VS for .. of

- for … in 은 object 에서 사용
- for … of 는 Array 에서 사용

```jsx
for (key in objects) {
  console.log(key);
}

const array = [1, 2, 3];
for (val of array) {
  console.log(val); // 1 2 3
}
```

<br>

## Object clone

Object.assign 을 통해 Cloning하기

```jsx
const user3 = {};
Object.assign(user3, user);
user3.name = "choi";
console.log(user);
// {name: "hyun", age: "20"}
console.log(user3);
// {name: "choi", age: "20"}
```
