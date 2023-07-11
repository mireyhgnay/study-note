# <div align="center">✏️ 30분 JS 요약 1부</div>

[🔗 제주코딩베이스캠프 - JS 요약 1부](https://www.youtube.com/watch?v=5eZUgvaSjXY&list=PLkfUwwo13dlWsZAdz1dFojuuYVbRynuFS)

<br>

```
기초를 까먹지 않기 위해 다시 요약하여 공부하기
```

<br>

## document 이리저리 굴려보기

`index.html`

```html
<p id="one">hello world</p>
```

<br>

`main.js`

```jsx
document.getElementById("one").innerHTML = "hong<strong>gildong</strong>";
```

one 이라는 id 를 가져와서 거기다가 html로 작성해서 추가하겠다.

**result :**

hong**gildong**

<br>

`main.js`

```jsx
document.getElementById("one").innerHTML = "hong<strong>gildong</strong>";
document.write("hello world");
```

**result :**

hong**gildong**

hello world

<br>

`main.js`

```jsx
window.alert("hello alert!");
```

알럿창 띄우기

<br>
<br>

## 변수 이리저리 굴려보기

`main.js`

```jsx
var 변수하나 = 100;
document.write(변수하나);
```

**result :**

100

<br>

`main.js`

```jsx
var 변수하나 = 100;
변수하나 = 200; // 변수값 변경됨
document.write(변수하나);
```

**result :**

200

<br>

`main.js`

```jsx
var 변수하나 = 100;
변수하나 = 200; // 변수값 변경됨
document.write(변수하나 + 변수하나); // 200+200 으로 연산도 가능
```

**result :**

400

<br>

`main.js`

```jsx
var 변수하나 = "100"; // 문자열로 인식
document.write(변수하나 + 변수하나); // 문자열100 끼리 더한 것
```

**result :**

100100

⇒ 숫자가 아닌 문자열끼리 합친것이므로 200이 아니라 100100 이라는 문자로 찍힌다.

<br>

`main.js`

```jsx
var 변수하나 = "100"; // 문자열로 인식
document.write(typeof 변수하나); // 변수의 타입 확인
```

**result :**

string

<br>

`main.js`

```jsx
var name = "honggildong";
document.write(name[0]); // 0번째 인덱스를 출력
```

대괄호[] 안에 있는 것은 인덱스 넘버를 의미한다.

**result :**

h

<br>
<br>

## 함수

`main.js`

```jsx
function f(x, y) {
  var z;
  z = x + y;
  return z;
}

document.write(f(3, 6));
```

**result :**

9

<br>
<br>

## 내장함수

`main.js`

```jsx
var txt = "honggildong jjang";
document.write(txt.lenght);
```

**result :**

17

⇒ 띄어쓰기 까지 모두 포함된다.

<br>

`main.js`

text 내장함수

```jsx
var txt = "honggildong jjang";
document.write(indexOf(jjang)); // result : 12
document.write(slice(0, 7)); // result : honggil
document.write(txt.replace(jjang, jjangjjang)); // result : honggildong jjangjjang
document.write(txt.toUpperCase()); // result : HONGGILDONG JJANGJJANG
```

- indexOf() : 해당 문자가 몇번째 인덱스부터 시작하는지
- slice() : 0번째 인덱스부터 시작해서 7번쨰 인덱스는 제외한 문자 (결론, 0~6 index)
- replace() : 대체하기
- toUpperCase() : 대문자로 변경

⇒ 이거 외에도 많음

<br>

`main.js`

number 내장함수

```jsx
var num = 10;
document.write(num.toFixed(6)); // 10.000000
document.write(num.toString()); // '10'
document.write(num.toString() + num.toString()); // 1010 (문자열이기 때문에 20으로 안나옴)
document.write(Math.max(10, 20, 30)); // 30
```

- toFixed() : 설정한 숫자 자리수 만큼 추가되서 출력된다. 뒤에 0이 6개 붙음
- toString() : 문자열로 변경
- Math.max() : 최댓값 구하기

⇒ 이거 외에도 많음
