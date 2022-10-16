## Map 

- Object 자료형의 단점들을 해결하기 위해서 나옴.

- Key - Value 쌍을 가지는 객체 자료형의 한 종류

- [참고하면 좋은 블로그 글](https://shanepark.tistory.com/220)

```javascript
let m = new Map() // 여기서 new는 생성자

m.set('하나', 1)
    .set('둘', 2)
    .set(true, '트루')
    .set([1, 2], '리얼리?')

console.log(m) // 아래 사진 처럼 출력됨.
```

![스크린샷 2022-10-16 오후 8.12.21](/Users/choisujin/Library/Application Support/typora-user-images/스크린샷 2022-10-16 오후 8.12.21.png)

<br>

```javascript
console.log(m.get('하나')) // 1 출력
console.log(m.get(true)) // 트루 출력
console.log(m.get([1, 2]))  // 각 객체는 다른 주소값을 가지므로 [1, 2]로 불러올 수 없다.
// JavaScrip
// [1, 2] === [1, 2] //false
// [1, 2] == [1, 2] // false
// let x = [1, 2]
// let y = [1, 2]
// x == y // false
// x === y // false
```

<br>

> **map은 객체 포함한 모든 값을 키로 사용할 수 있다 알고있는데...?**

```javascript
let m2 = new Map()
let test = [1, 2]

m2.set('하나', 1)
    .set(true, '트루')
    .set(test, '리얼리?') 

console.log(m2.get(test)) // 이렇게는 호출가능. 메모리 주소가 같은 곳을 바라보고있기 때문.
```

<br>

> **Map 메서드**

```javascript
let m3 = new Map()

m3.set('하나', 1)
    .set('둘', 2)

// Map에 해당 key값이 있는지 확인하기
m3.has('하나') // true
m3.has('아홉') // false

// Map에서 값을 제거하기
m3.delete('하나')

// Map의 크기 구하기
m3.size
```

- 위와 같은 메서드를 기존 Object자료형에서 구현하려면 복잡하다. 아래 사진을 보면 length가 없다.

<img src="/Users/choisujin/Library/Application Support/typora-user-images/스크린샷 2022-10-16 오후 8.36.25.png" alt="스크린샷 2022-10-16 오후 8.36.25" style="zoom:50%;" />

<br>

> **Object - Map 간의 형변환**

```javascript
// 다음은 실행되는 코드이다.
let m = new Map([['one', 1], ['two', 2]])
let m = new Map(Object.entries({'one': 1, 'two': 2}))

// map은 순회가 가능한 객체에서만 작동가능하다. 따라서 다음 코드는 되지 않는다.
let data = new Map({'one': 1, 'two': 2})
let data = new Map('hello world')
let data = new Map([10, 20, 30, 40]) 
```

<br>

> **Map - Object 간의 형변환**

```javascript
let obj = Object.fromEntries(m)
```

<br>

### 직접 순회가 가능한 Map (중요)

```javascript
let data = {'one': 1, 'two': 2}

// 기존 Object자료형은 순서가 없기 때문에 for-of문으로 순회할 수 없다.
for(const i of data) {
  console.log(i);
}

// 순회하려면 이렇게 해줘야한다.
for(const i of Object.entries(data)) {
  console.log(i);
}

// Map 직접 순회
let m = new Map()
m.set('하나', 1)
    .set('둘', 2)
    .set('셋', 3)

for(const i of m) {
  console.log(i)
}
// Map 직접 순회 - 구조분해할당
for(const [i, j] of m) {
  console.log(i, j)
}

m.keys()
m.values()
m.entries()
```

<br><br>





❗️ 참고! Map과 Set은 IE10이하 환경에서는 지원하지 않는다.