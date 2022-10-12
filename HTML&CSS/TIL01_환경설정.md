*멋쟁이사자처럼_프론트엔드스쿨 2일차*

<br>

## VSCODE 환경설정 및 단축키

오늘부터 본격적으로 수업을 시작하면서 VSCODE를 편리하게 사용하기 위한 환경설정과 단축키에 대해 배웠다. 

<br>

### 1. 코드Snippet

> **Snippet이란?**
>
> Snippet은 작은 조각을 뜻한다. 위키백과에 따르면 사용자가 루틴 편집 조작 중 반복 타이핑을 회피할 수 있게 도와준다고 되어있다.
>
> 쉽게 말하자면 만들어 놓은 템플릿대로 자동완성을 할 수 있게 해주는 것!

<br>

우리는 수업에서 한국어 페이지용 html 템플릿을 만들었다.

`CMD` + `P`로 명령 팔레트를 열고 `>snippet` 입력 -> html.json 파일 열기

아래 파일 삽입

```json
{
	"Print to console": {
		"prefix": "htmlko",
		"body": [
			"<!DOCTYPE html>",
			"<html lang=\"ko\">",
			"<head>",
			"    <meta charset=\"UTF-8\">",
			"    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">",
			"    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">",
			"    <title>$1</title>",
			"</head>",
			"<body>",
			"	$2",
			"</body>",
			"</html>"
		],
		"description": "한국어 페이지용 html 템플릿"
	}
}
```

<br>

### 2. 자주사용하는 Extension

VSCODE에는 많은 확장프로그램이 있지만 주로 사용하는 것만 설치하였다.

* live server : 실시간 서버 구동
* htmltagwrap : text를 wrapping해줌. 원하는 텍스트를 선택하고 `Option` + `W` 를 누르면 기본적으로 p태그로 감싸진다.
* auto rename tage : 태그 닫기 자동 수정(앞 뒤 태그 동시 수정), `CMD` + `D`

<br>

### 3. Emmet 문법

> emmet이란 HTML, XML 문서 등을 편집할 때 빠른 코딩을 위해 사용하는 플러그인이다.

```html
h1{hello world} 
p{hello}*10 <!-- * 반복하기 -->
p>strong <!-- > 자식(하위) 요소 -->
h1+h2+p <!-- + 형제 요소 -->
div#one <!-- 아이디 == #one -->
div.one <!-- 클래스 == .one -->
h1#one.two.three.four
h${hello}*6 <!-- $ 넘버링 -->
div.container-$*6
div.container-$.row-$*5

img <!-- <img src="" alt=""> -->
img:z <!-- <img src="" alt="" sizes="" srcset=""> -->

p[a="value1" b="value2" c=1 d=value3] <!-- [] 속성 -->
a[href="https://www.naver.com"]

table>(tr>td{hello}*10)*5 = table>tr*5>td*10 <!-- () 그룹화 -->

lorem5 <!-- 단어 개수 -->
lorem*5 <!-- 문단 개수 -->
한글입숨 - 검색필요
```



### 4. 기초상식

우리가 이름을 듣고도 모르는 장소는 주소를 찾아서 가는 것처럼 URL에도 주소가 있다.

|                |             |                             |
| -------------- | ----------- | --------------------------- |
| www.naver.com  | 도메인, URL | 이름                        |
| 223.130.195.95 | IP          | 주소 (DNS에 저장되어 있다.) |
| 23, 80, 443... | Port        | 문                          |

- http의 기본 Port는 80, https의 기본 Port는 443이다.
