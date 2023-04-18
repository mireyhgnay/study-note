# <div align="center">👩🏻‍💻 JavaScript - 문자열을 숫자로 변환하기</div>

### 1. Number()

인자로 전달된 문자열을 Number 로 변환합니다.

숫자가 아닌 문자나 undefined 등을 인자로 전달하면 NaN(Not A Number) 를 리턴합니다.

(NaN은 숫자로 표현이 안되지만 객체의 타입은 Number라고 보면 된다)

```javascript
const num1 = Number("1234"); // 1234 (type of Number)
const num2 = Number("1234.5"); // 1234.5 (type of Number)
const num3 = Number(undefined); // NaN (type of Number)
const num4 = Number("abcd"); // NaN (type of Number)
```

<br>

### 2. parseInt()

인자로 전달된 문자열을 정수 Number로 변환합니다.

소수는 정수로 변환하기 떄문에 이 부분은 고려해야합니다.

```javascript
const num1 = parseInt("1234"); // 1234 (type of Number)
const num2 = parseInt("1234.5"); // 1234 (type of Number)
const num3 = parseInt(undefined); // NaN (type of Number)
const num4 = parseInt("abcd"); // NaN (type of Number)
```

<br>

### 3. parseFloat()

소수를 문자열로 그대로 반환하고 싶을 때는 parseFloat() 를 사용해야합니다.

```javascript
const num1 = parseFloat("1234"); // 1234 (type of Number)
const num2 = parseFloat("1234.5"); // 1234.5 (type of Number)
const num3 = parseFloat(undefined); // NaN (type of Number)
```

<br>

### 4. Math()

Math 의 ceil(올림), round(반올림), floor(버림) 메소드들로 인자로 문자열을 받아 숫자로 변환합니다.

모두 올림/반올림/버림 으로 변환되기 떄문에 모든 숫자가 정수로 반환됩니다.

```javascript
const num1 = Math.ceil("1234.1"); // 1235
const num2 = Math.floor("1234.6"); // 1234
const num3 = Math.round("1234.5"); // 1235
```

<br>

추가로 문자열이 아닌 숫자도 인자로 받을 수 있는데, 결과는 동일합니다.

```javascript
const num1 = Math.ceil(1234.1);
const num2 = Math.floor(1234.6);
const num3 = Math.round(1234.5);
```

<br>

---

<br>

참고 : https://codechacha.com/ko/javascript-convert-string-to-number/
