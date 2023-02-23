# <div align="center">✏️ async와 defer</div>

<br>

## Script 태그의 문제점

> 스크립트를 다운받고 실행하는 동안 화면이 로딩되지 않고 멈춘다.  
> 스크립트는 아직 파싱되지 않은 DOM요소에 접근할 수 없다.

<br>

### 1. head 태그 안에 script 추가

- html 파싱하다가 script 가 보이면 다운받아서 실행시킨다.
- 그래서 head 에다가 추가하는건 좋은 방법이 아니다.

<br>

### 2. body 태그 맨 하단에 script 추가하는 것

- html 파싱 다 완료되고,
- 스크립트 다운받아 실행시킨다.
- 하지만 이건 스크립트에 의존적인 웹사이트라면 스크립트를 다운받고, 실행시키는 것에 시간이 오래걸려서 베스트인 방법은 아니다.
  ![1](https://user-images.githubusercontent.com/111990266/220898121-77065882-91b5-4624-b609-961504facc39.png)

<br>

### 3. head + async

```html
<head>
  <script async src="main.js"></script>
</head>
```

- html 파싱과 스크립트 다운로드를 병렬로 진행한다.
- 스크립트 실행이 될 때 파싱을 잠시 멈추고 스크립트 실행시키고 다시 html을 파싱한다.
- 이 방법은 html 파싱되기 전에 스크립트가 실행이되고 사람들이 페이지를 보려면 또 기다려야하므로 best까지는 아니다. html파싱이 중지되기때문에!
  ![2](https://user-images.githubusercontent.com/111990266/220898432-18749d38-6d29-49f2-aecd-272ebe5411be.png)

<br>

### 4. head + defer

```html
<head>
  <script defer src="main.js"></script>
</head>
```

- defer 가 있으면 script 를 일단 스크립트를 다운 받자! 명령만 시켜놓고
- 나머지 html 을 끝까지 파싱하고
- 파싱이 다 되고 바로 다운로드 된 스크립트를 실행시킨다.
- 가장 best~
  ![3](https://user-images.githubusercontent.com/111990266/220898675-f57a09f9-7032-4e34-b9a6-cfc0e413e896.png)
