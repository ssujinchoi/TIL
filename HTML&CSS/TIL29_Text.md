## Text의 특징과 속성들

### 서체의 기준선

![스크린샷 2022-11-11 오후 11.12.48](/Users/choisujin/Library/Application Support/typora-user-images/스크린샷 2022-11-11 오후 11.12.48.png)

- 위 이미지에서는 어센더와 디센더가 여백없이 이상적으로 글씨를 감싸고 있지만, 일반적으로는 아래 이미지 처럼 어센더와 폰트, 그리고 디센더 사이에 공간이 조금 남아 있는 편 
- 폰트를 디자인하는 디자이너가 제작할때 여유 공간을 주기 때문에 폰트의 종류마다 여백의 크기가 모두 다름



### 1. line-height

- leading 영역이 폰트의 위 아래로 존재. line-height 1은 이 leading 영역을 없앰(폰트 높이에 딱 붙게됨), leading 영역까지 포함하여 normal

```html
...
<style>
  p {
    margin: 0;
    padding: 0;
    line-height: normal; /*기본 값. 폰트의 font-family에 따른 글자의 기본 높이로 font-family마다 다름*/
    line-height: 2; /*숫자로 값을 설정. font-size의 배수. 소수점 지원*/
    line-height: 100px; /*px로 고정된 값을 적용. 폰트사이즈가 변할 경우 대비하지 못하므로 잘 사용하지 않음*/
    line-height: 2em; /*em은 부모요소의 font-size에 비례한 값을 적용. 동일하게 폰트사이즈가 변하면 대비x*/
    line-height: 50%; /*요소 자신의 폰트 사이즈를 기준으로 값을 설정*/
  }
</style>
...
<body>
  <p>hello world</p>
  <p>hello world</p>
</body>
```



```html
...
<style>
  	.container {
        width: 300px;
        height: 300px;
        font-size: 16px;
        border: solid 1px black;
        /* 1. 고정 값 : two, three 확인 */
        /*line-height: 10px;*/

        /* 2. em : 역시나 two, three 확인, 더 큰 font를 자식 요소에서 사용했을 경우 UI가 깨짐 */
        /*line-height: 1em;*/

        /* 3. leading 영역이 폰트의 위 아래로 존재. line-height 1은 이 leading 영역을 없앰(폰트 높이에 딱 붙게됨), leading 영역까지 포함하여 normal */
        /*line-height: 1;*/
      }
    .one {
      font-size: 10px;
    }
    .two {
      font-size: 20px;
    }
    .three {
      font-size: 30px;
      /* font-size의 2배가 된다. */
      /*line-height: 2;*/
    }
</style>
...
<body>
    <h1>hello world</h1>
    <div class="container">
        <div class="one">hello world</div>
        <div class="two">hello world</div>
        <div class="three">hello world</div>
    </div>
</body>

```



### 2. letter-spacing

- 글자 사이의 간격을 조절
- normal : 현재 폰트의 기본 간격
- px, em, rem : 기본 간격에 사용하는 유닛 단위만큼 간격을 추가 (%는 사용하지 않습니다.)

```html
...
<style>
  	button:hover {
      background-color: cadetblue;
      border: 1px solid black;
      /*button의 width값을 지정해주지 않아서 자간에 따라 크기가 늘어남*/
      letter-spacing: 10px;
  	}
</style>

...
<body>
    <p>hello world</p>
    <button>Click Me!</button>
</body>
```

<br>

### 3. text-align

- 블록레벨 요소안의 텍스트 정렬인 text-align과 관련 있는 속성값은 4가지가 존재

| 속성 값 | 설명                                             |
| ------- | ------------------------------------------------ |
| left    | 기본값. 텍스트를 왼쪽에 정렬합니다.              |
| right   | 텍스트를 오른쪽 정렬                             |
| center  | 텍스트를 가운데 정렬                             |
| justify | 마지막 라인을 제외하고 텍스트를 양쪽 끝으로 정렬 |



### 4. vertical-align

- **인라인 요소**의 수직정렬을 맞추기 위해 사용

| 속성 값     | 설명                                                         |
| ----------- | ------------------------------------------------------------ |
| baseline    | 베이스라인을 부모의 베이스 라인에 맞추어 정렬                |
| sub         | 베이스라인을 부모의 subscript(아래첨자)-baseline 에 맞추어 정렬 |
| super       | 베이스라인을 부모의 superscript(윗첨자)-baseline에 맞추어 정렬 |
| top         | 상단의 위치를 라인(인라인 박스를 감싸고 있는 공간)의 상단으로 정렬 |
| text-top    | 상단의 위치를 부모 요소 폰트의 상단으로 정렬                 |
| bottom      | 하단의 위치를 전체 라인의 하단으로 정렬                      |
| text-bottom | 하단의 위치를 부모 엘리먼트 폰트의 하단으로 정렬             |
| middle      | 폰트의 중간 위치를 부모의 baseline + x-height의 절반에 해당하는 위치로 정렬 (x-height는 소문자x의 높이) |

> ❗️ **img 태그의 바깥쪽 공백을 없애기 위하여 자주 사용합니다. (이미지도 기본적으로 인라인 요소이기 때문에 vertical-align 속성의 영향을 받습니다.)**



### 5. text-decoration

- 텍스트에 붙는 라인을 꾸며주는 속성

- 텍스트의 상단, 하단에 라인을 그려줄 수 있고, 라인의 종류와 색상도 지정할 수 있음.

```css
p{
	text-decoration: none;
  text-decoration: underline dotted;
  text-decoration: underline dotted red;
  text-decoration: green wavy underline;
  text-decoration: underline overline #FF3028;
	text-decoration: line-through;
}
```



> 하지만 글씨의 font-family, 텍스트의 형태에 따라 라인이 잘리는 경우가 있기 때문에 스타일링의 용도로는 잘 사용하지 않음. **대신 <a> 태그의 기본 스타일을 제거할때 가장 자주 쓰이는 속성**

```html
<style>
    a {
      text-decoration:none;
    }
</style>

<a href="https://www.naver.com/">go naver</a>
```



#### 그 외

- text-indent : 텍스트 라인에서 텍스트가 시작하기 전의 빈 공간을 설정. 쉽게 말해 들여쓰기 공간 설정
- text-overflow : 부모 컨테이너를 넘어간 컨텐츠가 어떻게 보여질지 결정하는 속성.