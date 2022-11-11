### DOM? : 문서를 객체화해 모델링한다.

HTML 문서의 내용을 트리형태로 구조화해 웹페이지와 프로그래밍 언어를 연결시켜주는 역할. 이때 각각의 요소와 속성, 콘텐츠를 표현하는 단위를 '노드(node)'라고 한다.

![스크린샷 2022-10-14 오전 9.21.58](/Users/choisujin/Library/Application Support/typora-user-images/스크린샷 2022-10-14 오전 9.21.58.png)

‼️주석도 노드로 인식한다.

<br>

### DOM 트리에 접근해야한다!! 

document 객체를 통해 HTML 문서에 접근이 가능. document는 브라우저가 불러온 웹페이지를 나타내며, DOM 트리의 **진입점 역할**을 수행

```html
<!DOCTYPE html>
<html lang="ko">
<head>
...
</head>
<body>
  <!-- id는 예시를 위해 여러개 지정 -->
	<div id="myDiv">div입니다.</div>
	<div id="myDiv">div입니다.</div>
	<div id="myDiv">div입니다.</div>
  <div class="myDiv-2">div입니다.</div>
	<div class="myDiv-2">div입니다.</div>
	<script>
    // id로 접근
    console.log(document.getElementById('myDiv'));
		// 변수에 담아놓고 그 변수로 조작한다. 즉, 찾아서 저장하고 사용
		const myDiv = document.getElementById('myDiv');
    
    // 해당하는 모든 요소에 접근
    // Element>s<를 조심한다. HTMLCollections = 유사배열객체 
    document.getElementsByTagName("div");
    
    // 클래스로 접근
    document.getElementsByClassName("myDiv-2");
	</script>
</body>
</html>
```

