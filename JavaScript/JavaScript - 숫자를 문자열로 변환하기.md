# <div align="center">👩🏻‍💻 JavaScript - 숫자를 문자열로 변환하기</div>

## 1. toString()

toString() 메소드를 호출하여 숫자를 문자열로 변환하여 리턴합니다.

마지막 str3의 경우 3(10진수) 을 2진수로 변환하여 문자열로 리턴한 것입니다.

```javascript
const str1 = (123.1).toString(); // '123.1'
const str2 = (123).toString(); // '123'
const str3 = (3).toString(2); // '11'
```

<br>

## 2. String()

```javascript
const str1 = String(123.1); // '123.1'
const str2 = String(123); // '123'
```

<br>

## 3. Template String (템플릿 문자열)

ES6 문법인 템플릿 문자열을 이용해서 숫자를 문자열로 변환할 수 있습니다.

템플릿 문자열

- 이 구문은 템플릿 문자열을 백틱(`)으로 감싸서 표현하고,
- '${}' 표현 안에 변수를 넣으면 문자열로 변환되어 리턴됩니다.

```javascript
const number1 = 123.1;
const number2 = 123;
const str1 = `${number1}`; // '123.1'
const str2 = `${number2}`; // '123'
```

<br>

## 4. 빈 문자열 이어붙이기

이 방법은 가장 간단하고 많이 사용하는 방식이다.

```javascript
const str1 = 123.1 + ""; // '123.1'
const str2 = 123 + ""; // '123'
```

<br>

---

<br>

참고 https://hianna.tistory.com/491
