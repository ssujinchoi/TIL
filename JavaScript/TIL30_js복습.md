## js 중요개념 복습



###  조건문

```js
const result = Math.floor(Math.random() * 10) + 1;
console.log('현재 랜덤값 :', result)

// 조건문: 여러 값들이 주어지고 그 값의 종류에 따라 처리방법을 달리 해야할 경우 사용
if (result > 5) {
    console.log('값이 5보다 크다.');
} else if (result < 5) {
    console.log('값이 5보다 작다.');
} else {
    console.log('5입니다.');
}

// switch - if문에 비해 가독성이 좋다.
// 표현식: 값으로 평가될 수 있는 식
switch (true) {
    case result > 5:
        console.log('5보다 큽니다.');
        break;
    case result < 5:
        console.log('5보다 작습니다.');
        break;
    default:
        console.log('5입니다.');
        break;
}

// 삼항연산자
result > 5 ? console.log('5보다 큽니다.') : result < 5 ? console.log('5보다 작습니다.') : console.log('5입니다.')
```

<br>

### 반복문

```js
// 반복문!!
// for in : 객체를 순환하고 싶을 때
const snack = {새우깡: 1000, 짱구: 1500, 홈런볼: 2000};
// prototype : 모든 인스턴스들이 공유할 수 있는 공간
//Object.prototype.꼬북칩 = 3000;
//Object.prototype.costr = function() {console.log('꼬북칩 3천원')};

//const drink = {콜라: 1000, 사이다: 1500};

// item은 프로퍼티의 key값
for (const item in snack) {
  // hasOwnProperty: 객체가 특정 프로퍼티를 가지는지 확인. 프로토타입에 등록된 프로퍼티는 제외
 	if(snack.hasOwnProperty(item))
		console.log(`${item}의 가격은 ${snack[item]}원 입니다.`);
}


// for of : 순환 가능한것 모두 순환 시킬 수 있다.
// 순환 가능한것 : array, string, arguments, nodeList, set, map. 단, object는 순환할 수 없다.

const heros = ['spiderman', 'blackwidow', 'batman', 'ironman'];

for (const hero of heros) {
    heros[heros.indexOf(hero)] = hero + "!!";
}
console.log(heros);

for (const item of heros[0]) {
    console.log(item);
}

function test(a, b, c) {
    for(const arg of arguments) {
       console.log(arg);
    }
}

test(1, 3, 5);

const mySet = new Set([1, 2, 3, 4, 5]);
console.log(mySet);

for (const item of mySet) {
    console.log(item);
}

mySet.add(10);
console.log(mySet);

const testArr = [1, 2, 3, 3, 4, 4, 5, 6, 7, 7];
const mySet2 = new Set(testArr);
console.log(Array.from(mySet2));

// 콜백 함수 : 매개변수로 전달하는 함수 -> 신기한 기능! 오직 자바스크립트에만 존재하는 기능
// forEach(), map()

const list = [
    {name: '장미', age: 10},
    {name: '강미', age: 9},
    {name: '상미', age: 11},
    {name: '방미', age: 12},
]

// 데이터에 있는 나이를 일괄적으로 1씩 올리고 싶다면
// 단 이렇게 쓰면 원본데이터가 손상된다.
list.forEach((item) => {
    item.age += 1;
})

// 새로운 객체 배열로
const newList = [];
list.forEach((item) => {
    const newObj = {name: item.name, age: item.age += 1};
    //newObj['age'] = item.age += 1;
    newList.push(newObj);
})
console.log(list)
console.log(newList);

// map은 새로운 배열을 반환한다.
let newList = list.map((item) => {
    const newObj = {name: item.name, age: item.age += 1};
    return newObj;
})

console.log(newList);
```

<br>

### 스코프

- 변수의 유효 범위를 말함

```js
// 1. 블록 스코프 : 변수의 생존가능한 범위한 중괄호안에서 끝나는 것.

// 2. 전역 스코프 : 전역변수
let val = 1;

// 3. 함수 스코프 : 함수안에서 선언된 변수는 함수 밖에서 접근할 수 없다.
function test (){
    let a = 1;
    let b = 2;
    return a + b;
}
console.log(test());

let a = 20; // 함수안의 a와는 별개의 변수
console.log(test());

// 함수 밖에서 함수안 변수에 접근할 수 없다. - error
console.log(b); 

// 함수안에 정의된 변수는 외부에서는 접근할 수 없고, 함수안에서는 어디든 접근이 가능
// 스코프 아래에서 위로 탐색을 하면서 값이 있는지 확인하는것을 스코프 체이닝이라고 한다.
const myFunc = function (){
    g = 10 // 키워드 없이 선언하면 무조건 전역변수가 된다.
    let a = 1;
    let b = 2;

    const myFunc2 = function (){
        let b = 5;
        let c = 6;

      	// b와 c는 myFunc2에 있으므로 각각 5, 6이고 a는 스코프 체이닝으로 인해 myFunc의 1이 된다.
        a = a + b + c; 
        console.log(a); // 12출력
    }

    myFunc2();
}
myFunc();
```

<br>

### 클로저

- 외부에서 접근할 수 없는 공간을 만드는 테크닉

```js
const myFunc = function (){
    // 클로저 공간
    let a = 1;
    let b = 2;

    // 클로저 함수 - 클로저 공간에 접근할 수 있는 함수. 
    const myFunc2 = function (){
        let b = 5;
        let c = 6;

        a = a + b + c;
        console.log(a);
    }
		
    // myFunc()2; 함수를 실행하지 않고 아래와 같이 리턴하여 밖으로 뺀다.
    return myFunc2; // myFunc2()로 하면 함수가 실행된 결과가 return되므로 ()를 뺀다.
}
// innerFunc에는 myFunc2가 들어있다.
// 함수가 종료되면 함수안에 있는 데이터들은 메모리에서 사라지는데,
// myFunc2함수 return을 통해 함수를 변수에 저장하여 myFunc2는 살아있다.
// 참조카운팅 - 참조하고있는 무엇인가 남아있으면 없애지않고 메모리 어딘가에 남겨둔다. 그것이 클로저 공간
const innerFunc = myFunc();

innerFunc();

// return 키워드를 만남으로서 myFunc는 메모리에서 지워집니다. 그렇다면 이때 myFunc2에서 참조하고 있던 a는 어떻게 될까요?
// 자바스크립트에서 메모리 관리는 참조 카운팅이라는 방법으로 이루어 집니다. a를 여전히 myFunc2에서 참조하고 있기 때문에 myFunc2의 b는 사라지지만 a는 여전히 남아있습니다.
```



> **클로저 사용 예시**

```js
// 클로져 공간을 만드는 함수입니다.
function makeClosure() {

    // 여기 선언된 변수들이 클로져(폐쇠된) 공간에 있게된다.
    const val1 = 100;
    const val2 = 200;

    // 리턴 키워드를 통해 함수의 변수(val1, val2)를 밖에서 사용할 수 있도록 함수에 담아 반환
    return {
        getVal1: function () { return val1 },
        getVal2: function () { return val2 }
    }
}

// 이제 result 변수 안에는 makeClosure 함수안에 있던 val1, val2 값이 참조되어있게 된다. 그리고 여기에 접근하는 방법은 오직 getVal1, getVal2 함수만 가능
let result = makeClosure();
console.log(result.getVal1());
console.log(result.getVal2());
```

