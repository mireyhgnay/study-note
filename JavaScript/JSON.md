# <div align="center">✏️ JSON</div>

<br>

## JSON 개념

브라우저 위에서 동작하는 웹사이트 또는 웹 어플리케이션

즉, 클라이언트들이 어떻게 서버와 통신할 수 있는지를 정의한 것이 바로 HTTP이다.

HTTP는 클라이언트가 서버에게 데이터를 request(요구),

서버는 클라이언트의 요구에 맞게 그에 따른 response(응답)하는 것을 의미합니다.

HTTP를 통해 서버에게 데이터를 받아올 수 있는 방법은 바로 AJAX이다.

<br>

웹페이지에서 동적으로 데이터를 받아올 수 있는 기술을 의미합니다.

대표적으로는 XMLHttpRequest라는 Object가 있다.

이것은 브라우저 API에서 제공하는 Object중 하나로 이 Object는 서버에게 간단하게 데이터를 요청하고 받아오는 것이 가능합니다.

또한 최근에 추가된 fetch() 브라우저API를 이용하면 간편하게 데이터를 주고 받을수도 있습니다.

<br>

## JSON의 특징

최근에는 XML을 대신해서 JSON 을 사용하고 있습니다.=

1. 데이터를 주고 받을 수 있는 가장 간단한 데이터 포맷이다.
2. 텍스트로 기반으로 이루어져 가벼우며
3. 일기(가독성) 또한 좋다.
4. 키와 쌍으로 구성되었으며
5. 데이터를 주고 받을 때 그리고 Serialize를 위해 사용됩니다.
6. 가장 중요한 점은 프로그래밍 언어나 플랫폼에 상관없이 쓸 수 있다는 것입니다.

## 우리가 알아야 할 것!

우리가 JSON에 대해서 알아야 할 것은 Object를 어떻게 Serialize 해서 JSON 파일로 변환할 것인지

그리고 다른 하나는 Serialize 된 JSON을 다시 어떻게 Deserialize 해서

Object 파일로 변환할 것인지에 대해 알아야 합니다.

## Object to JSON

JSON이라는 Object를 통해 간단하게 변환할 수 있습니다.

```javascript
let json = JSON.stringify(true); // Object를 JSON으로 변경할 수 있음
console.log(json);

json = JSON.stringify(["apple", "banana"]);
console.log(json);

const rabbit = {
  name: "tory",
  color: "white",
  size: null,
  symbol: Symbol(id),
  birthDate: new Date(),
  jump: () => {
    console.log(`${this.name} can jump!`);
  },
};

json = JSON.stringify(rabbit);
console.log(json);
json = JSON.stringify(rabbit, ["name", "color"]);
console.log(json);
```

## JSON to Object

JSON.parse는 어떠한 String을 받아서 Object로 변환할 수 있습니다.

```javascript
json = JSON.stringify(rabbit);
let obj = JSON.parse(json);
console.log(obj);
rabbit.jump();
obj.jump();

console.log(obj.birthDate.getDate());
```
