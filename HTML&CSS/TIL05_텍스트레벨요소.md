### 텍스트 레벨 요소의 특징



* 요소안의 컨텐츠 크기 만큼만 영역 점유, block레벨 요소는 한줄을 다 차지함 - 가용(사용)가능 범위

* 자식으로 sections와 grouping contents를 배치할 수 없다.

```html
<span>
	<div></div>
	<section></section>
	<article></article> 등은 배치할 수 없다. 직계든 자손이든 안된다!! 문법 오류다.
</span>
```



```html
<br> // 줄바꿈을 위한 태그
<wbr> //  텍스트 박스에서 한 줄로 모두 표시가 안될 때에만 줄바꿈이 일어나게 하는 역할을 합니다.

css 속성으로 줄 바꿈됨 :
CJK언어의 [word-break : normal] - 기본 줄 바꿈 규칙을 적용(단어와 단어 단위로 줄바꿈이 된다. 한글은 한글자한글자 바뀐다.)

white-space속성 : 요소가 공백 문자를 처리하는 법을 지정 wbr기준으로 단어가 줄바꿈됨
white-space: pre == <pre></pre>
html에서는 공백으로 문자인지 단어인지 구분함 g는 문자 gdddd 는 하나의 단어
```



#### 주석

* 코드 보류, 코드에 대한 설명/의도 공유하기 위해 사용된다.
* 실무에서는 코드를 취소하는데 잘 쓰지않고, 주석을 웬만하면 잘 남기지 않는다. 



#### ```<a>``` 태그

- HTML은 ```<a>```태그를 통해 연결된 거대한 책이다.
- ```<a href="경로"></a> ```: href 속성을 통해 경로를 지정.
    (자바스크립트로 경로를 지정할 수도 있지만 이는 웹 접근성에 위배됨으로 href 속성을 사용해주는게 좋다.)
  1) 브라우저가 해석할 때 href를 통해 a태그가 어디로 이동하는지 보는데, href가 없으면 확인할 수 없기에 문법적 오류. (웹 표준에 위배됨)
  2) 검색엔진이 읽을 때 판단이 안됨

- html 문법상 sections, grouping content 요소들은 텍스트 레벨 요소의 자식으로 사용되지 않지만, 앵커 태그만 **예외적**으로 sections, grouping content 요소를 자식으로 허용. 
- ```<a>``` 요소안의 자식으로는``` <a>``` 요소나 ```<button>``` 과 같이 사용자와 인터렉션이 가능한 요소를 자식으로 두지 않기 때문에 주의가 필요!

```html
<a href="https://www.naver.com">click</a>
<a href="https://www.naver.com" target="_blank">click</a>
<a href="./index.html">click</a>
<a href="#three">click</a> <!-- 해쉬 링크 --> html에 scroll-behavior속성 적용하면 부드럽게 가능
<a href="./index.html" download>click</a>
<br>
<a href="./hello.hwp">hwp click</a>
<br>
<a href="./hello.hwp" download="a.hwp">hwp download click</a> a.hwp 저장명 정해줌
<br>
<a href="./hello.pdf">pdf click</a>
<br>
<a href="./hello.pdf" download="a.pdf">pdf download click</a>
<a href="tel:+82027777777">(02)777-7777</a> /
<a href="mailto:hello@gmail.com">hello@gmail.com</a>

  * Internet Explorer 는 download 속성을 지원하지 않습니다.
 
  
```

<br>

#### ```<b>``` 태그 & ```<strong>``` 태그

- ```<b>```태그는 굵은 글꼴을 표현하고 싶을 때 사용. 
- 별 다른 의미는 없으며(시맨틱하지않음, 단순 스타일을 위한 태그) 오직 텍스트를 굵은 글씨로 표현하기 위한 용도이기 때문에 더 이상 사용하지 않는 요소.  
- ```<strong>``` 태그는 굵은 글꼴에 중요도를 더해 강조할 때 사용합니다. 중요도를 더 강조하고 싶을 때에는 strong을 중첩하기도 한다.

```html
<p>
    <strong>공지사항</strong> 
    adipisicing <b>elit</b>. 
</p>
  
  => html에 스타일 관련한 내용이 들어있으면 더러워?진다. 그래서 스타일만을 위한 CSS가 생김            
```

<br>

#### ```<i>``` 태그

- ```<i>``` 태그는 기울임 글꼴을 나타낸다. 
- HTML5에서는 전문 용어, 문단에서 주 언어와 다른 언어로 표현된 부분(주 언어가 한글이지만 영어로 표기되었을 경우), 소설이라면 등장인물의 생각이 표기되어 있는 부분 등 어떤 이유로 주위와 구분해야 하는 부분을 표현하기 위해 사용. 
- ```<em>``` 태그는 같은 기울임 글꼴로 표현되지만 강조의 의미가 있습니다.

<br>

#### ```<span>``` 태그 

- 별다른 의미가 없다. 보통 줄 바꿈 없이 영역을 묶는 용도로 사용합니다. div와 용도가 같다.(줄바꿈 되냐 안되냐 차이)
- 여러 요소를 묶어 컨트롤하기 위한 영역으로 id를 주거나 클래스를 사용
- div와 마찬가지로 최후 수단으로 사용
