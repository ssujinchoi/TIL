### 콜백함수 (callback function)

- 함수(이름)를 아규먼트로 전달해서 코드 어딘가에서 호출하는 것. 나중에 부르는 함수라고 할 수 있다.
- 함수에 파라미터로 들어가는 함수
- 용도 : 순차적으로 실행하고 싶을 때

```javascript
function sum(x, y, 콜백함수) {
  	// 1000줄
    콜백함수(x + y)
  	// 1000줄
    return x + y
}

function documentWriter(s) {
    document.write('콜백함수', s)
}

// 함수(이름)를 아규먼트로 전달해서 코드 어딘가에서 호출하는 것
sum(10, 20, documentWriter)

// 다음과 같은 형태들
document.querySelector('.button').addEventListener('click', 함수명)
setTimeout(function 함수명(){}, 1000)

function first(파라미터){
  console.log(1)
  파라미터()
}

function second(){
  console.log(2)
}

first(second) // ! first함수안의 코드를 실행 시켜라. 근데 파라미터에 second를 집어넣어서
```

<br>

> 그런데 그냥 이렇게 해도 순차적으로 실행되는데 왜 콜백함수를 사용하는걸까?

```javascript
first()
second()
```

> **가정상황** 
>
> first()함수가 여기저기 자주 쓰이는 것.
>
> 팀원 1 : first()후에 바로 console.log(2) 하고싶다.
>
> 팀원 2 : first()후에 바로 console.log(4) 하고싶다.

```javascript
first()
console.log(2)

first()
console.log(4)
// 이런식으로 해도 되지만 콜백함수를 사용하는 이유
// 1. 만약, first가 비동기처리를 하는 함수라던가... 등등의 이유로 순차적으로 실행되지 않을 수도 있다.
// 2. 유연한 동작을 하는 함수를 만들 수 있다.
// 3. 안정적으로 순차적 실행이된다.
function first(파라미터){
  console.log(1)
  파라미터()
}

function second(){
  console.log(2)
}

first(second)
```



> **콜백함수의 여러 형태**

#### 1) Map

```javascript
// https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map
// 구문 : arr.map(callback(currentValue[, index[, array]])[, thisArg])
// callback - 새로운 배열 요소를 생성하는 함수로 다음 세 가지 인수를 가짐. 단, 여기서 대괄호는 optional을 뜻함
// 	1. currentValue - 처리할 현재 요소
//	2. index - 처리할 현재 요소의 인덱스
//	3. array - map()을 호출한 배열

// 제곱 만들어주는 함수 - 해당 함수는 arr.map(제곱) 밑에 있어도 실행된다! 호이스팅으로 인해서!
function 제곱(x){
  return x ** 2
}

// 배열 선언
let arr = [10, 20, 30, 40, 50]

// map사용. 함수의 이름을 아규먼트로 넣어준다.
arr.map(제곱)


// --- 화살표 함수 사용 ---
x => x ** 2 or x => {return x ** 2}

arr.map(x => x ** 2)
```



#### 2) forEach

```javascript
// https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach
// arr.forEach(callback(currentvalue[, index[, array]])[, thisArg])
// https://caniuse.com/mdn-api_nodelist_foreach // 노드에서의 forEach는 IE에서 작동하지 않습니다.

function 두배(x){
	console.log(x * 2);
}
let arr = [10, 20, 30, 40, 50]
arr.forEach(두배)
```



> **문제 : 화살표 함수를 사용해서 아래 map과 동일한 기능을 하는 forEach문을 작성해보자**

```javascript
let arr = [10, 20, 30, 40, 50]
arr.map(x => x * 2)


// 풀이
let result = []

arr.forEach(x => {
  result.push(x * 2)
})

console.log(result)
```



> **주의! NodeList의 forEach는 IE에서 작동하지 않는다.**

```html
<!DOCTYPE html>
<html lang="ko">
    ...
    <body>
        <ul>
            <li>hello</li>
            <li>hello</li>
            <li>hello</li>
            <li>hello</li>
            <li>hello</li>
        </ul>
        <script>
            let e = document.querySelectorAll("li");
            e.forEach((e) => console.log(e)); // 주의! IE에서 작동하지 않는다.
        </script>
    </body>
</html>
```

