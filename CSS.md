# CSS > Cascading style sheet

- 화면에 어떻게 렌더링할 것인지를 정의하기 위한 언어

### Selector 선택자

- 스타일을 적용하고자 하는 HTML요소를 선택할 수 있어야 한다.

### Property 속성

- Selector로 HTML요소를 선택하고 {} 내에 Property와 값을 지정하는 것

```CSS
p {
    color: ...;
    font-size: ...;
}
```

### Value 속성값

- Property에 사용할 수 있는 값을 특정단위로 지정하여야 함

```CSS
p {
    color: red;
    font-size: 10px;
}
```

---

### Link style

- HTML과 CSS 연동방법

```HTML
<link rel="stylesheet" href="css/style.css" />
```

### Reset CSS

- 웹브라우저에 따라 default style가 상이하고 지원하는 tag나 style이 제각각 이어서 주의가 필요
- 하나의 스타일로 통일 시켜주는 역할을 Reset CSS가 한다.
  - https://meyerweb.com/eric/tools/css/reset/

---

### 전체 셀렉터 Universal Selector : \*

### ID selector

```html
<div id="div"></div>
```

- #을 이용하여 CSS적용
  - #div{}

### Class selector

```html
<div class="div"></div>
```

- .을 이용하여 CSS적용
  - .div{}

### Combinator 복합 셀렉터

- div안에 있는 p를 선택하기
  - div p {}

#### child combinator 자식 셀렉터

- div > p {}

### 가상클래스 셀렉터 Pseudo-Class Selector

- 마우스가 올라와 있을때, 링크를 방문했을 때와 안했을 때, 포커스가 들어와 있을 때 등 사용
- :link, :hover, :focus, :active 등 있음.

* 참고
  - https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes

### 구조 가상 클래스 Structural

- :first-child : 셀렉터에 해당하는 모든 요소 중 첫번쨰 자식인 요소를 선택
- :last-child : 모든 요소 중 마지막 자식인 요소를 선택
- :nth-child(n) : 앞에서 n번째 자식인 요소를 선택한다
- :nth-last-child(n) : 뒤에서 n번째 자식인 요소를 선택한다.
- :first-of-type : 셀렉터에 해당하는 요소의 부모 요소의 자식 요소중 첫번쨰 등장하는 요소를 선택
- :last-of-type : 부모요소의 자식 요소중 마지막에 등장하는 요소를 선택
- :nth-of-type(n) : 부모요소의 자식 요소중 앞에서 n 번째
- :nth-last-of-type(n) : 부모요소의 자식 요소중 마지막에서 n 번째

### 부정 셀렉터 Negation pseudo-class

- :not(selector) : 셀렉터에 해당하지 않는 모든 요소를 선택

### 가상 요소 셀렉터 Pseudo-Element Selector

- 요소 콘텐츠의 첫글자 또는 첫줄
- 요소 콘텐츠 앞 또는 뒤

  - 가상요소에는 두개의 클론 :: 사용. CSS표준에 미리 정의된 이름이 있기 때문에 임의의 이름 사용 불가

- ::first-letter : 콘텐츠의 첫글자를 선택.
- ::first-line : 콘텐츠의 첫줄을 선택. 블록요소에만 적용
- ::after : 콘텐츠 뒤에 위치하는 공간을 선택. 일반적으로 content property와 함께 사용
- ::before : 콘텐츠 앞에 위치하는 공간을 선택. 일반적으로 content property와 함께 사용
- ::selection : 그래그한 콘텐츠를 선택. (일부 브라우저에서 동작하지 않음)

---

## CSS Property값의 단위

- 키워드

* 각 프로퍼티에 따라 사용할 수 있는 키워드가 존재.
  - ex) display property : block, inline, inline-block, noon
  - mdn참조 : https://developer.mozilla.org/ko/docs/Web/CSS/Reference

- 크기 단위
  - CSS에서 대표적으로 px, em, % 사용
  - px는 절대값, em, % 는 상대값
  - 대부분 브라우저의 font-size는 16px, 1em, 100%이다.

### px

- pixel : px는 디바에스 해상도에 따라 상대적인 크기를 가짐.
  - 요소나 이미지 크기에 대체로 사용.

### %

- 백분률 단위의 상대 단위. 상대적인 사이즈를 설정

### em

- 배수단위로 상대 단위.
  - font-size설정이나 콘텐츠를 포함하는 컨테이너의 크기 설정에 사용하면 상대적인 설정이 가능하여 편리.
  - \*중첩된 자식요소에 em을 지정하면 모든 자식 요소의 사이즈에 영향을 미치기 때문에 주의!

### rem

- rem은 최상위 요소(html)의 사이즈를 기준으로 삼는다. (rem 의 r = root)

### Viewport (vh,vw, vmin,vmax)

- 반응형 웹디자인은 화면의 크기에 동적으로 대응하기 위해 %단위를 자주 사용.

  - 하지만 %는 em과 같이 상속에 의해 부모 요소에 상대적 영향을 받음.

- vw : viewport 너비의 1/100
  - ex) 1vw -> width: 1000px 의 1%인 10px
- vh : 높이의 1/100
- vmin : 너비 또는 높이중 작은 폭의 1/100
- vmax : 너비 또는 높이중 큰 폭의 1/100

### Color

- keyword
  - mdn 참고 : https://developer.mozilla.org/ko/docs/Web/CSS/color_value

---

## Box Model

- 모든 HTML요소는 BOX 형태의 영역을 가지고 있음.

  - BOX는 content, padding, border, margin 으로 구성.

- Content : 요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역.
- Padding : 테두리(border)안쪽에 위치하는 내부 여백 영역. 요소에 적영된 배경의 컬러, 이미지는 패딩 영역까지 적용됨.
- Margin : 테두리(border)바깥에 위치하는 외부 여백 영역. 배경색을 지정할 수 없다.
- Border : 테두리 영역으로 border값은 테두리의 두꼐를 의미.

### width, height

- 요소의 높이와 너비를 지정하기 위해 사용. 콘텐츠 영억을 대상으로 함.
- 만일 width, height로 지정한 콘텐츠 영역보다 실제 콘텐츠가 크면 콘텐츠 영억을 넘치게 된다.

  - 이때 overflow: hidden; 을 지정하면 넘친 콘텐츠를 감출 수 있다.

- 기본적으로 박스 크기는 margin, border, padding 모두 합친 크기임.

  - ex) 전체너비 : width + padding + border + margin

- width, height 를 비롯한 모든 박스모델 관련 프로퍼티는 상속되지 않음.

### margin, padding

- content의 4개방향에 대해 지정이 가능 top,right,bottom,left
  - 시계방향으로 지정됨
    - ex) margin: 10px 15px 20px 25px top right bottom left 순서
