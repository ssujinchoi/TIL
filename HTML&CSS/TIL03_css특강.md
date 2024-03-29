# 1주차 특강
### CSS
> 마크업 개발을 할 때는 레이아웃 먼저 잡아야 한다.
>
> 큰 덩어리에서 작은 덩어리로 봐야한다.  
>
> 태그, 요소, 셀렉터 등 용어를 공부하자.

- weight, height 등이 지정되지 않았을 때 property값이 무엇인지 확인해야한다.
- property 초기값이 auto일 때 여기서 auto는 무엇을 의미하는지도 확인해 봐야한다.  

***주의할 점**

property마다 auto의 의미가 다르다.  

모든 property의 initial값이 모두 auto는 아니다.  

```
div {
    background-color : orange;
    // width, height가 작성되지 않아도 property의 initial value가 지정되어 있다.
    width: auto; /* 부모 기준 */
    height: auto; /* 자식 기준 */
}
```
### user agent stylesheet

- 브라우저가 제공하는 기본 스타일
- initial value(property의 초기값)와는 다름 
- ex) body요소에 적용되어있는 margin 8px 

### margin : auto

+ margin property의 auto는 사용 가능한 공간을 여백으로 제공
+ margin에서 auto는 상황마다 다름  

+ 웹은 다양한 관점이 있기 때문에 한 작업자가 모든 관점을 파악하긴 어려움
>       전문가(강사)마다 포커스가 다름 CSS, 시맨틱 마크업, 웹 접근성, 검색 엔진 최적화 등  

<br>

### 선택자

#### `전체 선택자`

-  *.header와 같이 사용되며, .header처럼 생략 가능.  

#### `타입선택자`

- 주어진 노드 이름을 가진 모든 요소를 선택.

#### `id선택자`

- id특성에 따라 요소를 선택. 문서 내에는 주어진 id를 가진 요소가 하나만 존재해야 합니다.

#### `class선택자`

- 주어진 class특성을 가진 모든 요소를 선택.

<br>

### 레이아웃을 처음 만든 뒤 user stlye reset을 하는 이유?

>       브라우저가 제공하는 각각의 요소는 우리가 의도한 디자인이 아니며, 브라우저마다 제공하는 요소가 다르기 때문.  
##### <br>

#### inline요소의 특징

- inline element(text-align: center) <-> block level element와는 다르다(margin: 0 auto;) 

- baseline 위에서 움직이지만 baseline을 생성하진 않는다.  

+ inline element는 width와 height 개념이 없다. 
- margin은 좌우로만 가능 -> baceline 때문

<br>

#### marign-left, margin-right의 선행조건

- width값이 먼저 고정되어야 한다. (why?) 이미 가득차 있는 상태이기 때문. 

<br>

#### img요소

+ img 위치를 바꾸고 싶으면 부모 블럭에 text-align을 해야 한다.

<br>

#### 상속

+ 상속이 되지 않는 property가 존재한다.
+ 대부분 텍스트 관련된 요소들이 상속된다.

+ 원래부터 상속이 되는 property들은 inherit로 초기화 해주면 좋다. 

<br>

#### css 선택자

```csv
.header img {} // -한 칸- 띄어쓰면 하위선택이 된다. 

.header > img{} // -꺽쇠-는 직계 자식이 선택된다.

여기서 공백이나 꺽쇠는 combinator
```


#### 약간의 Tip!

+ 보통 header와 footer를 공통 분모로 보고 먼저 완성한 뒤 contents를 진행 

​	=> (why?) contents 내용은 자주 변경되기 때문에

+ 시각적인 요소를 html로 사용하면 용도에 맞지 않는다. 웬만하면 css를 이용하자 

​	=> '안녕'을 '안&nbsp;녕'처럼 공백을 넣기 위해 html요소를 넣기보단 css를 이용

+ display를 이용하면 표시하는 방식을 바꿀 수 있다. 

​	=> display : block or inline-block 

- 한 프로그램 당 보통 1-2가지 폰트 (최대3개)를 사용하는데 특정 부분만 폰트가 다르다면 img파일로 쓰는 경우도 많다.

```html
<h1>
  <img src="" alt="모두의 HTML/CSS">
</h1>
```





