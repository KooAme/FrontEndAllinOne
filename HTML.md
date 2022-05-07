## HTML 5

- HyperText Markup Language
  - ウェブページの内容と仕組みを担当。

### 요소 Element

- 시작태그와 종료태그, 그리고 태그 사이에 위치한 content로 구성.

#### 요소의 중첩 Nested Element

- 요소는 중첩될 수 있음. 요소는 다른 요소를 포함할 수 있다. 이때 부자관계가 성립.

#### 빈 요소 Empty Element

- content를 가질 수 없는 요소. attribute만 가질 수 있음
  - br, hr, img, input, link, meta

### Attribute

- 요소의 성질, 특징을 정의하는 명세.

```html
<img src="koo.img" width="100" height="100" />
```

- 이 정보를 사용하여 화면에 출력

#### 글로벌Attribute

- 모든 HTML요소가 공통으로 사용할 수 있는 어트리뷰트임. (몇몇 제외)
  - id, class, hidden, lang, style, tabindex, title 자주 사용.

### 주석 Comments

```html
<!--HTML주석-->
```

### semantic tag

- 브라우저, 검색엔진, 개발자 모두에게 콘텐츠의 의미를 명확히 설명하는 역할을 함.

  - header, nav, aside, section, article, footer

- non-semantic
  - div, span, {...}

### html tag

- 웹페이지에 단 하나만 존재. 즉, 모든 요소는 html 내부에 기술해야 함

### head tag

- 메타데이터를 포함하기 위한 요소이며 단 하나만 존재. HTML문서의 title,style,link, script등에 대한 데이터로 화면에 표시되지 않음.

#### title tag

- 브라우저의 탭 제목을 정의

#### style tag

- style 정보를 정의

#### link tag

- 외부 리소스와의 연계정보를 정의.

#### meta tag

- 기본 메타데이터 정의에 사용.
- 메타데이터는 브라우저, 검색엔진(keywords) 등에 의해 사용됨. charset 어트리뷰트는 브라우저가 사용할 문자셋을 정의.
- 검색엔진 최적화(SEO)를 위해 keywords를 정의

```html
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript" />
```

---

#### body tag \*중요하지 않는 태그는 빼도록 하겠습니다.

- HTML문서의 내용을 나타내며 웹페이지에 단 하나만 존재.

#### 제목 태그 headings

- h1~ h6 이 있으며, semantic web의 의미를 살려서 제목 이외에는 사용하지 않는 것이 좋음.

#### p tag

- 단락을 지정 Paragraphs

#### br tag

- 줄바꿈. line break
- empty element로 종료태그가 없음.
- 연속적 공백을 삽입하는 방법

```html
&nbsp; &nbsp;
```

#### hr tag

- 수평줄을 삽입

---

## hyperlink

### a tag

```html
<a href="kooAme.github.com"> gogo </a>
```

### href Attribute

- 이동하고자 하는 파일의 위치(경로)를 값으로 받음.

### Directory

    - 루트 디렉터리 : 파일 시스템 계층 구조 상의 최상위 디렉터리
    unix : /
    windows : C:\

    - 홈 디렉터리 : 시스템의 사용자에게 각각 할당된 개별 디렉터리이다.
    unix : /Users/id
    windows : C:\Users\id

    - 작업 디렉터리 : 작업중인 파일의 위치
    ./

    - 부모 디렉터리 : 작업 디렉터리의 부모 디렉터리
    ../

### target Attribute

- \_self : 링크를 클릭했을 때 연결문서를 현재 윈도우에서 오픈 (기본값)
- \_blank : 새로운 윈도우나 탭에서 오픈

```html
<a href="kooAme.github.com" target="_blank" rel="noopener noreferrer">gogo</a>
```

- 여기서 target="\_blank"를 사용해서 외부 페이지를 오픈하는 경우,
  이동한 외부 페이지에서 js코드를 사용해 악의적인 페이지로 리다이렉트할 수 있는 보안취약점이 있다 !!.
  따라서 rel="noopener noreferrer"을 추가해서 피싱공격에 대비할 것을 권장.

---

## List

#### ul tag (Unordered List) 순서없는 목록

- 순서없이 점만나옴

#### ol tag (Ordered List) 순서있는 목록

- 1.2.3. 순서나옴
- type를 사용해 문자를 지정가능
- 1 : 숫자 기본값
- A : 대문자 알파벳
- a : 소문자 알파벳
- I : 대문자 로마숫자
- i : 소문자 로마숫자

```html
<ol type="I">
  <li></li>
</ol>
```

- start 어트리뷰트로 리스트의 시작값 지정가능
- 결과 : 3부터 시작

```html
<ol start="3"></ol>
```

- reversed 어트리뷰트는 리스트의 순서값을 역으로 표현

---

## table 표

- table tag : 표를 감싸는 태그
- tr : 표 내부의 행(row)
- th : 행 내부의 제목 셸(table heading)
- td : 행 내부의 일반 셸(table data)

#### table tag Attribute

- border : 표 테투리 두께 지정 , CSS사용이 더 나은 방법
- rowspan : 행의수 지정 (병합)
- colspan : 열의수 지정 (병합)

---

### img tag

- src : 이미지 파일 경로

### audio

- 웹페이지마다 음악 파일 형식이 다르니 참고.

---

### form

- 사용자가 입력한 데이터를 수집하기 위해 사용되며, input, button 등의 입력 양식 태그를 포함할 수 있다.
- action : 값은url 이며, 입력데이터가 전송될 url 지정
- method : 값은get/post 이며, 입력데이터 전달 방식 지정

        - GET 과 POST는 HTTP 프로토콜을 이용해서 데이터를 서버에 전달하는 방식 (HTTP request method)

        GET
        - 전송 URL에 입력데이터를 '쿼리스트링'으로 보내는 방식
            - ex: http://kooAme.github.com/posts?useris=11&id=1
        - 전송 URL바로 뒤에 ? 를 통해 데이터의 시작을 알려주고, key-value형태의 데이터를 추가. 1개이상의 전송 데이터는 &로 구분
        - URL에 전송데이터가 모두 노출되기 때문에 보안에 문제가 있음. 데이터의 한계도 있음.
        - REST API에서 GET 메소드는 모든 또는 특정 리소스의 조회를 요청함.

        POST
        - Request Body에 담아 보내는 방식
            - ex: http://kooAme.github.com/posts
        - URL에 전송데이터가 모두 노출되지 않지만 GET에 비해 속도가 느림
        - REST API에서 POST메소드는 특정 리소스의 생성을 요청

```html
<form action="http://kooAme.github.com/users" method="get">
  ID: <input type="text" name="id" value="1" />
  <input type="submit" value="submit" />
</form>
```

- submit이 되면 input에 입력된 데이터가 action에 지정된 서버측의 처리 로직에 전달

### input

- form 태그 중에서 가장 중요한 태그. 사용자로부터 데이터를 입력받기 위해 사용
- form 태그 안에 있어야 데이터를 전송할 수 있으나 ajax를 사용할 시에는 바깥에 있어도 상관없다.
- 서버에 전송되는 데이터는 key=value형태로 전송됨
  - type 어트리뷰트값 참고
    - https://developer.mozilla.org/ko/docs/Web/HTML/Element/Input

### select

- 복수개의 리스트에서 복수개의 아이템을 선택할 때 사용.
  - select, option, optgroup 함께 사용가능한 태그

### button

- 클릭할 수 있는 버튼생성
  - input type="button"과 유사하지만 다름.
    - button은 텍스트나 이미지같은 콘텐츠 사용 가능!

---

## div , span

- div 대그는 어떠한 의미도 가지고 있지 않기 때문에 시맨틱 태그를 사용하는 편이 좋다.
  - block 요소와 inline 요소를 완벽히 이해해야 하기에 CSS에서 정리해 보겠다.
