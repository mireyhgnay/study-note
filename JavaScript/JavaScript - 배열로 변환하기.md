# <div align="center">👩🏻‍💻 JavaScript - 문자열을 숫자로 변환하기</div>

<br>

배열로 변환하기 전 체크해야할 것은 변환하고자 하는 것이 문자열인지 확인해야합니다!

문자열이 아닌 숫자를 배열로 변환하고 싶다면?

위에서 설명해둔 문자열로 변환하기 방법 중 한가지를 사용하여 변환후, 배열로 만들어줍니다.

```javascript
const num = 123;
const numToString1 = num.toString();
const numToString2 = String(num);
const numToString3 = `${num}`;
const numToString4 = num + "";

const array = [...numToString1];
```

<br>

### 1. 스프레드 연산자 (Spread Operator)

```javascript
const str = "hello";
const arr = [...str];

// result : [ 'h', 'e', 'l', 'l', 'o' ]
```

<br>

### 2. Array.from()

```javascript
const str = "hello";
const arr = Array.from(str);

// result : [ 'h', 'e', 'l', 'l', 'o' ]
```

<br>

### 3. split(’ ’)

구분자로 문자열을 분리하고 분리된 문자열들을 배열에 저장할 수 있습니다.

문자열을 공백으로 분리하고 분리된 문자들로 배열을 만듭니다.

```javascript
const str = "hello world javascript";
const arr = str.split(" ");

// result: [ 'hello', 'world', 'javascript' ]
```

<br>

쉼표를 구분자로 문자열을 분리하여 배열로 변환합니다.

```javascript
const str = "hello,world,javascript";
const arr = str.split(",");

// result: [ 'hello', 'world', 'javascript' ]
```

<br>

3가지 방법 모두 결과는 같습니다!

각자 원하는 방식으로 선택하여 사용하면 됩니다.

<br>

---

<br>

참고 : https://codechacha.com/ko/javascript-convert-string-to-array/
