# <div align="center">✏️ Class VS Object</div>

<br>

> 클래스와 오브젝트의 차이점, 객체 지향 언어 클래스 정리

<br>

## Class 와 Object

클래스를 이용해서 상속과 다양성이 일어날 수 있는데 이런 모든것들이 가능한것이 객체지향 언어이다.

```javascript
class Person {
	name; // 속성
	age; // 속성
	speak(); // 함수
}
```

- Peerson이라는 클래스 안에 name 과 age라는 ‘속성’이 있고, speak() 이라는 함수가 들어있다.
- class 안에는 조금 더 연관있는 데이터들을 묶어 놓은 속성과 메소드가 종합적으로 묶여있는 것을 말한다.

<br>

## Class

- ES6 문법에서 새로 추가된 class
- template
  - Class 자체에는 데이터가 들어있지 않고 틀만 정해놓은 것
  - 이 클래스에는 이런 데이터만 들어올 수 있어~ 라고만 정의해 놓은 것
- 비유하자면, 붕어빵을 만들 수 있는 틀
- 한번만 선언한다

<br>

## Object

- 이 class를 이용해서 실제로 데이터를 넣어서 만드는 것이 바로 object이다.
- 오브젝트는 클래스를 이용해서 굉장히 많이 만들 수 있다.
- 비유하자면, 붕어빵이라는 class를 이용해서 팥,크림,피자 라는 데이터를 붕어빵에 넣으면
  - 붕어빵 자체는 object이고
  - 이 붕어빵을 마들기 위해 우리가 정의한 붕어빵의 틀은 class

<br>

## Class 선언

class가 도입되기 전에는 class를 정의하지 않고 바로 object를 만들 수 있었다.  
우리가 좀 더 간편하게 사용할 수 있도록 문법만 class가 추가된 것이다.

```javascript
class Person {
  constructor(name, age) {
    // 생성자
    // fields(속성)
    this.name = name;
    this.age = age;
  }

  // methods
  speak() {
    console.log(`${this.name} : hello!`);
  }
}

// 새로운 object를 만들 때 new 라는 키워드를 쓴다.
const ellie = new Person("ellie", 20);
console.log(ellie.name); // ellie
console.log(ellie.age); // 20
ellie.speak(); // ellie : hello!
```

- class 키워드를 이용해서 Person이라는 클래스 생성한다.
- constructor(생성자)를 이용해서 object를 만들 때 필요한 데이터를 전달한다.
- 전달받은 데이터를 이 class에 존재하는 name과 age에 전달된 데이터를 할당해주는 것이다.

<br>

## Getter and Setter

**💊 인캡슐레이션(캡슐화)**

- 우리가 자주가는 자판기 커피 머신 = class
- 자판기는 커피가 있다. 자판기 커피 갯수가 있다고 하자 = integer(정수) number of coffee
- 커피머신으로 동전을 넣고 커피를 뽑는다
- 커피머신에는 property가 커피 갯수(number of coffee) / 메소드는 동전 넣고, 커피 뽑기 2개
- number of coffee 가 integer(정수) 인데 -1 이 가능할까? ⇒ 안된다. 그래서 우리가 get,set을 쓰는 것!
- 사용자가 -1원 이라고 설정하면 안되니까 우리는 setter에서 0으로 만들어 주는 것이다.
- 다른사람이 number of coffee 를 설정하는 것은 좋지 않다.
  - 그래서 이 number of coffee 라는 property를 private 로 만드는 것이다.
- 즉 우리가 작성한 class를 옆에 있는 동료가 바보같이 잘못 사용해도 우리가 조금 더 방어적으로 코드를 짜줄 수 있는 것을 getter와 setter 이다

<br>

```jsx
class User {
  constructor(firstName, lasName, age) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
  }

  // user 의 age 가 -1인 건 말이 안되기 때문에 get키워드를 이용해서 값을 return한다
  get age() {
    return this._age;
  }

  // set 키워드를 이용해서 값을 설정할 수 있다. 값을 설정해줘야한다.
  set age(value) {
    this._age = value < 0 ? 0 : value; // 0 미만으로 입력할 경우 0 으로 출력해준다
  }
}

const user1 = new User("Steve", "Job", -1);
console.log(user1.age); // 0
```

<br>

## 상속과 다양성

- 삼각형, 직사각형 등 도형의 공통점은 넓이를 구할 수 있다는 것이다.
- 재사용이 가능하기 때문에 유지보수하기도 쉽다. class Shape 를 생성!
- 상속한다라는 키워드 extends 만 이용해도 Shape 에 있는 모든 것들이 포함될 수 있다.

```jsx
class Shape {
  constructor(width, height, color) {
    this.width = width;
    this.height = height;
    this.color = color;
  }

  draw() {
    console.log(`drawing ${this.color}!`);
  }

  getAreat() {
    return this.width * this.height;
  }
}

// Shape 클래스를 그대로 상속
class Rectangle extends Shape {}

// Shape 클래스를 그대로 상속받아 변경하고 싶은것만 변경해 다양성있게 사용
class Triangle extends Shape {
  draw() {
    super.draw(); // 부모인 Shape 의 draw() 함수도 가져온다.
    console.log("삼각형"); // Triangle 에서 draw()에 새롭게 추가한 내용
  }

  getArea() {
    return (this.width * this.height) / 2; // overwriting
  }
}

const rectangle = new Rectangle(20, 20, "blue");
rectangle.draw(); // drawing blue
const triangle = new Rectangle(20, 20, "red");
triangle.draw(); // drawing red / '삼각형'
```
