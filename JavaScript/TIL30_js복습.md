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

