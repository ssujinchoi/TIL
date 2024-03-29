## Array 타입

- 여러 개의 값을 리스트 형태로 나열한 자료구조
- 배열의 각 값은 원소(element) 혹은 요소 라고함
- 인덱스로 참조되는 요소, 배열의 요소란 배열을 구성하는 각각의 값
- 다른 언어와 다르게 JavaScript의 배열은 배열 타입이 아닌 객체 타입으로 존재. 즉, 메모리 상의 연속 배치의 배열이 아님
- 인덱스와 배열의 크기를 나타내는 length 프로퍼티가 존재함.
- 배열의 생성자 함수에 숫자를 한개만 넣으면 인스턴스의 길이를, 여러 원소를 넣으면 배열의 원소를 뜻함.
- 배열에도 리터럴 표현은 대괄호 ```[]```
- 리터럴 생성과 동시에 원소에 접근 가능  ```[1,2,3,][0] === 1``` 

```javascript
// 1. 배열 기본 선언 방법
// 대부분 동일한 자료의 형태가 반복됨
let fruits = ['사과', '수박', '복숭아', '딸기']
// 다른 자료형도 들어갈 수는 있음
function sum(x, y){
  return x + y
}
let test = [1, 2, 3]
let obj = {'one': 1, 'two': 2}
let data = [console.log, sum, test, obj]

// 2. 배열의 또 다른 선언 방법
let fruits = new Array('사과', '수박', '복숭아', '딸기')
```

<br>

> **2차원 배열**

```javascript
let array = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]

console.log(array[1][2]) // 6이 출력됨
```

<br>

> **원본 수정 없이 값을 수정하고 싶을 때**

```javascript
let x = [10, 20, 30]
let y = [...x]
y.pop()
console.log(y)
```

<br>

### 배열의 메서드

> **배열 요소의 삽입 및 제거**

```javascript
let fruits = ['사과', '수박', '복숭아', '딸기', '바나나']

// 1. 배열의 맨 뒤 요소 제거
let 꺼낸과일 = fruits.pop();
console.log(fruits); // ['사과', '수박', '복숭아', '딸기']

// 2. 배열에 맨 뒤에서 요소 추가
fruits.push("멜론");
console.log(fruits); // ['사과', '수박', '복숭아', '딸기', '멜론']
fruits.push(꺼낸과일);
console.log(fruits); // ['사과', '수박', '복숭아', '딸기', '멜론', '바나나']

// 3. 기존의 요소를 삭제하거나, 교체하거나, 새 요소를 추가
fruits.splice(3, 1) // 3번 인덱스 요소 하나만 삭제
fruits.splice(3) // 3번 인덱스부터 전부 삭제
fruits.splice(3, 0, '한라봉') // 특정 인덱스에 요소 추가
fruits.splice(3, 1, '제주감귤') // 특정 인덱스에서 지정한 개수만큼 제거후 요소 추가
fruits.splice(3, 0, ['포도', '체리]') // 배열안에 배열 넣기
```

