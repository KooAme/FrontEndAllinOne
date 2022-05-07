## CSS > Cascading style sheet

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
- :link, :hover, :focus, :active 등 있음. mdn참고

### 구조 가상 클래스 Structural

- :first-child : 셀렉터에 해당하는 모든 요소 중 첫번쨰 자식인 요소를 선택
- :last-child : 모든 요소 중 마지막 자식인 요소를 선택
- :nth-child(n) : 앞에서 n번째 자식인 요소를 선택한다
- :nth-last-child(n) : 뒤에서 n번째 자식인 요소를 선택한다.
- :first-of-type : 셀렉터에 해당하는 요소의 부모 요소의 자식 요소중 첫번쨰 등장하는 요소를 선택
- :last-of-type : 부모요소의 자식 요소중 마지막에 등장하는 요소를 선택
- :nth-of-type(n) : 부모요소의 자식 요소중 앞에서 n 번째
- :nth-last-of-type(n) : 부모요소의 자식 요소중 마지막에서 n 번째
