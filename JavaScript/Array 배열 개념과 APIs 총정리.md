# <div align="center">✏️ Array 배열</div>

## 자료구조

비슷한 종류의 데이터들을 한곳에 묶어서 담아놓는 것을 “자료구조”라고 한다.

<br>

오브젝트도 데이터를 담는 거라고 했는데 자료구조와 차이점은?
<img width="943" alt="자료구조1" src="https://user-images.githubusercontent.com/111990266/222152887-faaf74d1-acca-490b-8760-2ffefac3791e.png">
토끼처럼 행동이 있는 애들이 있다면, 데이터 중에서는 행동은 따로 없고 속성 정도로만 이루어진 애들도 있다.

<br>

자료구조는 토끼는 토끼끼리 당근은 당근끼리 바구니에 담아놓는 걸 생각하면된다.
<img width="938" alt="자료구조2" src="https://user-images.githubusercontent.com/111990266/222153311-86f38c58-0578-4591-a174-15559f4b0245.png">

<br>
<br>

## Array

### 1. Declaration

새로운 배열 생성하기

```jsx
const arr1 = new Array();
const arr2 = [1, 2];
```

<br>

### 2. Index position

```jsx
const fruits = ["사과", "바나나"];
console.log(fruits); // ['사과', '바나나']
console.log(fruits.length); // 2
console.log(fruits[0]); // 사과
console.log(fruits[1]); // 바나나
console.log(fruits[2]); // undefined

// array.length 에 -1을 해주면 마지막 요소를 출력한다.
console.log(fruits[fruits.length - 1]); // 바나나
```

<br>

### 3. Looping over an array

`for`

```jsx
const fruits = ["사과", "바나나"];
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]); // 사과. 바나나
}
```

<br>

`for … of`

for 보다 간단한 방법!

순차적으로 배열안 요소들을 할당하면서 출력한다.

```jsx
const fruits = ["사과", "바나나"];
for (let fruit of fruits) {
  console.log(fruit); // 사과, 바나나
}
```

<br>

`forEach()`

for 보다, for … of 보다 더더 간단한 방법

```jsx
const fruits = ["사과", "바나나"];
// 3개의 인자
fruits.forEach(function (fruit, index, array) {
  console.log(fruit, index, array);
});
```

콘솔창 결과  
배열요소, 인덱스번호, 배열 모두 출력된다.
<img width="264" alt="console" src="https://user-images.githubusercontent.com/111990266/222153738-c418b9c3-3731-43fd-881c-6c63912b5fd9.png">

```jsx
// 화살표 함수로 변경
// 배열안에 들어있는 value들 마다 내가 전달한 함수를 출력하는구나!
fruits.forEach((fruit, index) => console.log(fruit, index));
fruits.forEach((fruit) => console.log(fruit)); // Index, Array는 필요없으니 제거
```

<br>

### 4. Addition, deletion, copy

- `push` : 배열 뒤에 추가

  ```jsx
  fruits.push("딸기", "바나나");
  ```

- `pop` : 배열 뒤에서부터 제거

  ```jsx
  fruits.pop();
  fruits.pop();
  console.log(fruits); // 딸기, 바나나 뒤에 추가됐던것이 모두 제거되서 출력됨 => 사과, 바나나
  ```

- `unshift` : 배열 앞에서부터 추가됨

  ```jsx
  fruits.unshift("딸기", "망고");
  console.log(fruits); // 딸기, 망고, 사과, 바나나
  ```

- `shift` : 배열 앞에서부터 제거됨

  ```jsx
  fruits.shift();
  console.log(fruits); // 망고, 사과, 바나나
  ```

push 와 pop 에 비해 unshift 와 shift 는 세상 느리다.  
인덱스 번호도 바뀌면서 미루면서 추가 및 제거가 되기 때문에 느리다.

<br>

### 5. splice()

```jsx
fruits.splice(1);
// slice(시작하는 인덱스, 지울 갯수)
console.log(fruits); // 1번부터 다 지워짐. [사과, 망고, 바나나, 딸기] 가 있다면 '사과'만 나음

fruits.splice(1, 1); // 1부터 한개만 지울거야
console.log(fruits); // 사과 바나나 딸기 (1번인 망고만 지워진 것)

fruits.splice(1, 1, "수박", "체리"); // 1부터 1개만 지우고, 그 자리에 수박, 체리를 넣어줘
console.log(fruits); // 사과 수박 체리 바나나 딸기
```

<br>

### 6. concat()

배열 합치기

```jsx
const fruit1 = ["사과", "망고"];
const fruit2 = ["두리안", "바나나"];
const newFruits = fruit1.concat(fruit2);
console.log(newFruits); // 사과 망고 두리안 바나나
```

<br>

### 7. Searching

- indexOf : 인덱스 번호 찾기

  ```jsx
  // 사과 인덱스 넘버 찾기
  console.log(fruits.indexOf("사과")); // 0
  ```

- includes : 배열에 포함/미포함 (boolean)

  ```jsx
  console.log(fruit.includes("사과")); // true
  console.log(fruit.includes("배")); // false
  ```

- lastIndexOf : 마지막 인덱스 찾기

  ```jsx
  const fruit = ["사과", "배", "사과"];
  console.log(fruit.indexof("사과")); // 0
  console.log(fruit.lastIndexof("사과")); // 2
  ```

indexOf 는 **발견한 맨 처음에 있는 있는 인덱스 번호를 반환**한다.  
lastIndexOf 는 **발견한 마지막 인덱스 번호를 반환**한다.  
동일한 것이 있을때 인덱스넘버로 추출할떄 유용하게 사용할 수 있다.
