*멋쟁이사자처럼_프론트엔드스쿨3기 DAY3*

<br>

## 프론트엔드 개발자는요...

- HTML + CSS + JavaScript를 이용해 페이지를 만든다.
- 페이지와 서버의 연결작업
- 고려해야 할 점
  - 해상도
  - 크로스 브라우징
  - 성능측정
  - 웹 렌더링
  - 접근성(스크린 리더, 웹 에이전트 고려)
  - 웹 표준 준수
  - 검색엔진 최적화(SEO)
  - 레거시 브라우저 대응 

> 고려해야하는 부분이 이렇게나 많았다니...! 그리고 디자이너, 기획자, 백엔드 개발자와의 소통도 중요하다는 것을 알았다.

<br>

## HTML 요소


### Sections

- `<body>` : 실제 사용자에게 보여지는 문서의 컨텐츠를 나타내는 요소

- `<article>` : **독립적으로 구분되는 구역**. 어떤 페이지에 붙여도 독립적 사용 가능, **heading요소와 함께 사용 권장**
- `<section>` : **연관성 있는** 문서의 구획을 나누고자 할 때 사용. **heading요소와 함께 사용 권장**
- `<header>` : 특정한 컨텐츠의 시작 부분을 나타내는 요소
- `<h1>~<h6>` : 제목을 지정하기 위해 사용. h1~h6는 중요도에 따라 사용됨. **`<h1>` 요소는 페이지당 한 번만 사용권장**
- `<nav>` : 현재 페이지 내, 또는 다른 페이지로의 링크들의 집합을 정의할 때 사용. 메뉴, 목차 등에 사용됨.
- `<aside>` : 문서의 주요 흐름을 따라가지 않는 별개의 구획을 만들 때 사용. 보통은 광고 영역
- `<footer>` : 웹 페이지의 하단 영역. 작성자 정보, 저작권, 회사명, 정책, copyright 등이 위치함.

<br>

### Grouping content

- `<ol>, <ul>, <li> ` 
  - `<ol>` : ordered list의 약자로, 순서가 있는 목록을 뜻함. **직계 자식 요소로는 `<li>` 요소만 사용되어야 한다.**
  - `<ul>` : unordered list의 약자로 순서가 없는 목록을 뜻함. **직계 자식 요소로는 `<li>` 요소만 사용되어야 한다.**
  - `<li>` : 각 항목들을 나열하는 태그로 **`<ol>`혹은 `<ul>`요소 안에서만 사용되어야함. **

- `<dl>, <dt>, <dd>` : **사전처럼 어떠한 것을 정의**할 때 쓰이는 목록
  - `<dl>` : 정의 목록. `<dt>`, `<dd>` 만 자식 요소로 사용가능. 단, 예외적으로 `<div>`는 올 수 있다.
  - `<dt>` : 정의할 용어
  - `<dd>` : 용어를 설명
- `<div>` : 레이아웃을 나눌 때 사용. 하위에 있는 여러 요소를 묶어 스타일을 변경시킬 수 있다. 남발하지 말 것 -> 시맨틱 하게 코드를 짜자!
- `<figure>, <figcaption>` : 이미지와 캡션이 연결되도록 `<figure>`요소를 사용. 이미지의 설명 및 자막
- `<p>` : 단락을 표시. 하나의 완결된 문단을 의미하기 때문에 `<p>`태그 안에 자식으로 또 `<p>`를 사용하지 않음. 줄바꿈의 용도로 사용해서도 안됨
- `<nav>` : 현재 페이지 내, 또는 다른 페이지로의 링크들의 집합을 정의할 때 사용. 메뉴, 목차 등에 사용됨.
- `<main>` : 문서의 주요 콘텐츠를 나타냅니다. 메인 요소안에 들어가는 내용은 문서의 유일한 내용이어야함. IE 에서는 지원하지 않음
- `<pre>` : HTML에 작성한 내용 그대로 화면에 표현.
- `<blockquote>` : 인용 블록. 
- `<hr>` : 원래는 가로줄을 표현하기 위해 사용했으나 HTML5에 오면서 의미가 생김. 
  - 이야기에서의 장면 전환 혹은 문단 안에서 주제가 변경되었을 때 구별을 위해 사용
  - 단락을 구분할 때 사용하므로 `<p>`태그 내 사용은 웹 표준에 어긋남.

> 실습을 해보면서 HTML표준 명세만 잘 따른다면 어떤 구획마다 100% 정해진 태그는 없다고 생각된다. 태그의 목적에 맞게 잘 사용하면 되지않을까...



