# <div align="center">✏️ 제주코딩베이스캠프 - 넓고 얕은 IT 지식</div>

<br>

## 🔗 넓고 얕은 IT 지식 재생목록

[제주코딩베이스캠프 - 넓고 얕은 IT 지식](https://www.youtube.com/watch?v=KpTyl6gjsrw&list=PLkfUwwo13dlXSXc3A_uCC1HSL5U-VA7M2)

<br>
<br>

## Server

코드 작업한 여러 파일들을 저장하고 실행시켜서 사용자에게 화면을 보여준다.

이러한 일들을 하는 것이 서버!!

<br>
<br>

## JSON (Javascript Object Notation)

자바스크립트에서 객체를 만들 때 사용하는 표현식으로 자바스크립트 구문 형식을 따르는 언어 독립형 데이터 포맷입니다.

<br>

**json 데이터 형식으로 입력**

```json
var date = [
	{
		"name" : "라이켓",
		"age" : "10",
		"language" : "Python"
	},
	{
		"name" : "빙키",
		"age" : "11",
		"language" : "JavaScript"
	}
];
```

<br>

**원하는 데이터 출력하기**

```
console.log(data[0]); // 라이켓 데이터 전체 가져옴
console.log(data[0]["name"]); // "라이캣"
```

<br>

**JSON Generator**

JSON Generator 사이트는 제이슨 파일을 자동으로 만들어주는 프로그램이다. 즉, 가짜 데이터!

임시로 만들어서 프로그래밍 할 때 개인적으로 연습할 수 있다.

추가로, API서버도 가짜로 만들 수 있는데, 제너레이터에서 만든 JSON데이터를 받아서 API로 뿌려줄 수 있는 것이다.

<br>

**이 JSON 데이터를 서버에서 서빙하게되면 API서버가 되는 것이다.**⭐

<br>
<br>

## API, API Server

> Application Programming Interface(응용 프로그래밍 인터페이스)

<br>

사용자 요청에 따라 원하는 데이터를 Serving 해주는 서버를 말합니다.

어떤 기능을 미리 만들어 두고 필요할 때 제공하는 것을 **API 서버**라고 합니다.

우리는 이 API를 통해 소셜로그인(카카오, 네이버, 페이스북 등)과 카카오 맵, 네이버 지도 등의 기능들을 이용할 수 있게 됩니다.

<br>

API 서버에서는 JSON 파일을 받을 수도 있고, 사진을 받을 수도 있습니다.

직접 구축할 수도 있고 남이 제공해주는 API를 활용할 수도 있습니다.

<br>

쉽게 말하자면, 내가 원하는 기능이나 데이터를 이미 잘만들어진 전문가에게 위임하는 것!

그래서 API에서 원하는 기능이나 데이터를 받아 쓰는 것!

<br>

**공공데이터 포털에서 OPEN API를 이용해서 각종 데이터에 접근 할 수도 있습니다.**

🔗 https://www.data.go.kr/tcs/dss/selectDataSetList.do
