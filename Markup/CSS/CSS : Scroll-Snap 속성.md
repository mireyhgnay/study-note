# <div align="center">🧚🏻 CSS : Scroll-Snap 속성</div>

<br>

```
마크업팀 작업 당시에도 swiperJS 라이브러리를 사용하느라 잘 몰랐던 CSS 속성이였는데 새로 알게되어 공부하게 되었습니다.
```

<br>

대부분 프로젝트에서는 [SwiperJS](https://swiperjs.com/) 라이브러리를 통해 여러 슬라이드 UI를 스와이프 할 수 있도록 구현합니다.

공식문서 가이드에 따르면 Scroll-snap API를 통해 Swiper를 동작시킬 수 있다고 하여 테스트 해보기로 했습니다.

간단한 이미지 캐러셀을 Scroll-Snap 과 Vanilla JS 를 사용하여 적용하기 위해 해당 API를 공부합니다.

<br>

## **`Scroll Snap`**

Scroll snap 을 사용하면 사용자가 터치, 휠 스크롤 조작을 마쳤을 때 오프셋을 설정할 수 있습니다.

미리 설정한 위치로 이동한다면 자연스러운 스크롤 움직임과 함께 사용자 경험은 더욱 향상될 수 있습니다.

JavaScript 사용을 줄일 수 있고, 하드웨어 가속을 사용하기 떄문에 브라우저에서 원활한 동작과 성능 향상을 기대할 수 있습니다.

<br>

**Scroll Container : 스크롤 스냅 동작이 발생하는 영역**

사용자가 터치, 휠 마우스를 조작하여 스크롤링하면 Scroll Container에서 Scroll snap이 동작합니다.

<br>

**snap area : Scroll Container 내부의 각 요소**

스크롤링 시 타겟이 되는 오브젝트이며, snap area에 snap position 을 지정할 수 있습니다.

<br>

## **`Scroll Snap` 속성**

- scroll-snap-type
- scroll-snap-align
- scroll-padding
- scroll-margin

<br>

## **`scroll-snap-type`**

아래 두가지를 설정해주어야 합니다.

- **scroll snap axis : snap position 을 지정할 수 있는 축을 결정**
  - `x`: 수평(가로) 축으로 snap position 지정
  - `y`: 수직(세로) 축으로 snap position 지정
  - `block`: snap area의 block 축으로 지정
  - `inline`: inline 축으로 지정
  - `both`: 두 축의 위치를 개별적으로 스냅. 잠재적으로 각 축의 다른 요소에 스냅이 가능.

<br>

- **scroll snap strictness : 스냅의 엄격도를 지정**
  - `none`: 스냅하지 않음.
  - `proximity`: snap position을 지정하였다면 해당 설정에 맞춰 스냅하고, 미지정 상태라면 유저 에이전트에 따릅니다.
  - `mandatory`: 항상 스냅.
    - mandatory 값 선언시 주의해야할 점!!
      콘텐츠 간의 간격이 넓을 때 강제로 스냅을 하게 되면 중간콘텐츠를 건너 뛰고 다음 콘텐츠로 이동하는 경우가 발생할 수 있습니다. 주의햐아합니다.
      스냅 엄격도를 보다 정확히 position과 함께 사용하는 것이 좋습니다.

<br>

## **`scroll-snap-align`**

snap area 안에서 원하는 정렬 방식을 설정할 수 있습니다.

`scroll-snap-type`에서 지정한 축을 기준으로 snap area의 정렬을 정합니다.

- `start`: 축을 기준으로 snap area의 시작 부분에 맞춰 정렬
- `end`: snap area의 끝에 맞춰 정렬
- `center`: snap area의 가운데에 맞춰 정렬

⇒ center 로 할 경우, 처음 그리고 마지막 요소는 start, end 라인에 맞춰지고, 두번째 요소부터 snap area의 가운데에 맞춰 정렬되는 것

<br>

## **`scroll-padding`**

해당 요소의 `padding` 값이 변경되는 것이 아니고, 해당 뷰포트의 `padding` 이 적용됩니다.

스크롤 할 수 있는 영역이 줄어들고 레이아웃, 스크롤 원점, 요소의 위치, 실제로 보여지는 것에는 영향을 주지 않습니다.

아래 이미지처럼 스크롤시 50px의 여백이 생기는 것입니다.

![scroll-padding](https://user-images.githubusercontent.com/111990266/233097220-7f91aa34-a507-4973-b484-cf804bb8527d.png)

<br>

## **`scroll-margin`**

`scroll-padding`과 동일하게 실제 요소에 영향을 미치지 않습니다.

```css
.snap-area:nth-of-type(2) {
  scroll-margin: 100px;
}
```

<br>

두번째 요소에만 scroll-margin을 적용하면 아래와같이 2번요소로 스크롤 이동시 여백이 생김

![scroll-margin](https://user-images.githubusercontent.com/111990266/233097737-78880bc4-abfe-4cba-af94-5e68582735b1.png)

<br>

그럼 실제로는 거의 `scroll-padding` 과 `scroll-margin` 은 사용하는 경우가 거의 없을텐데..?

라고 생각이 들었는데,

`scroll-padding`, `scroll-margin` 의 사용 예시로는!

이전 혹은 다음 콘텐츠에 대한 예상 시나리오를 사용자에게 제공할 수 있다고합니다!!!👍

<br>

---

<br>

**Reference**

- https://wit.nts-corp.com/2018/08/28/5317 ⭐제일 이해에 도움이 된 사이트
- https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type
- https://fe-developers.kakaoent.com/2023/230119-scroll-snap/
