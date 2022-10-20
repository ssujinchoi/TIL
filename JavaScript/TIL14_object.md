## Object 타입

- key : value 쌍으로 이루어져있다.
- 이러한 구조체를 해시테이블이라고 한다.

```javascript
// 1. 기본 형태
let newuser = {
  id: 'chany',
  pw: '1234',
  active: true // 이것이 false로 바뀌면 휴면계정으로 바뀜
}

// * key값으로 value값 출력
console.log(newuser['id'])
console.log(newuser.id)
// console.log(newuser.[id]) // error
// console.log(newuser.'id') // error

// 2. 다음과 같은 형태로 많이 사용함
let user = [{
  id: 'chany',
  pw: '1234',
  active: true 
}, {
  id: 'blue',
  pw: '5656',
  active: true 
}]

// * object타입이 배열로 있다면 다음과 같이 값을 가져올 수 있다.
console.log(user[0]['id'])

// 3. 아래와 같이 선언이 가능함
let a = 10
let b = 20
let c = 30
let e = {a, b, c}
console.log(e) // {a: 10, b: 20, c: 30}

// 4. 값 변경
e['a'] = 50
console.log(e) // {a: 50, b: 20, c: 30}
```

<br>

> **유사 배열 객체**

```javascript
// 5. key값으로 문자열 외에 다른 값을 넣었을 경우
let txt = 'hello'
let txt2 = {
  0: 'h',
  1: 'e',
  2: 'l',
  3: 'l',
  4: 'o'
}
console.log(txt[1])
console.log(txt2[1]) // 유사배열 객체로 배열과 다르다 !!

// * 아래 코드는 map에서 가능하다.
console.log(txt2.1) // error - 이게 가능한 것은 map이다.
console.log(txt2.{'one': 1}) // error - map
```

<br>

> **value의 값으로 문자열 외에 다른 값을 넣을 수 있다.**

```javascript
// 다음을 콘솔창에서 테스트해보자
let test = {
  one: 어떤함수이름,
  two: console.log,
  three: window.innerWidth,
  four: [10, 20, 30],
  five: '10',
  six: 30
}
```

<br>

> **key만 value만 뽑아내기**

```javascript
let newuser = {
  id: 'chany',
  pw: '1234',
  name: 'jiny',
 	email: 'blabla@naver.com',
  active: true // 이것이 false로 바뀌면 휴면계정으로 바뀜
}

// key값만 뽑아내기
console.log(Object.keys(newuser))
// value값만 뽑아내기
console.log(Object.values(newuser))
// key와 value값을 한번에 뽑아내기
console.log(Object.entries(newuser))
```

<br>

> **object spread 기법**

```javascript
let userUpdate = {
  name: 'jin',
  email: 'bloblo@naver.com'
}

// Object의 값을 변경하는 기존의 방법
newuser['name'] = userUpdate['name']
newuser['email'] = userUpdate['email']

// * 최근 변경된 방법 - spread기법
newuser = {...newuser, ...userUpdate}

--------------------------------------------------

let newuser2 = newuser
newuser2['id'] = 'hello world'
// 아래 두 코드는 같은 값이 나온다. 왜냐하면 newuser2는 newuser과 같은 주소값을 참조하고있기때문이다.
console.log(newuser) 
console.log(newuser2)

// * 따라서, 다음과 같이 spread 기법을 사용하면 원본을 해치지않고 사용할 수 있다.
let newuser2 = {...newuser}
newuser2['id'] = 'hellow world'
// 아래 두 코드는 값이 다르게 나온다. 즉, 원본 데이터의 값이 변경되지 않았다.
// spread기법은 값을 펼치는 것.
console.log(newuser)
console.log(newuser2)

```

