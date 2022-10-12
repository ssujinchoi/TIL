### 생성자함수

```javascript
// 객체를 생성하는 방법 - 객체 리터럴
let user = {
    name: 'Bruse',
  	age: 28,
  	birthday: '95-03-02'
}

let newUser = {}
// 예를 들어 form에서 입력 받은 값이라고 생각하면 이렇게 넣어줘야한다.
newUser['name'] = 'Hani'
newUser['age'] = '30'
newUser['birthday'] = '93-02-01'
```

> **그런데 개발을 하다보면 비슷한 객체를 여러번 만들어야하는 경우가 있다. 예를 들면, 회원이나 상품과 같은 경우이다.**

```javascript
// 위에걸 좀 더 편리하게 -> 생성자 함수
// 생성자 함수의 첫 글자는 대문자
function User(name, age, birthday) {
    this.name = name
    this.age = age
    this.birthday = birthday
}

// let user1 = User('Hani', 24, '99-10-11')  // console에 찍으면 undefined - return이 없어서

// 코드 깔끔,prototype을 이용해 메모리적으로도 효율
// 동일한 프로퍼티를 가지는 객체를 반복적으로 쉽게 생성하기 위해
let user1 = new User('Hani', 24, '99-10-11') 
let user2 = new User('Sony', 23, '20-10-11') 
```



> **new 키워드 사용시 생성자 함수의 동작방식**

```javascript
function User(name, age, birthday){
   	// 2. 빈 객체를 만들고 this에 할당 - 실제 코드는 아님
    this = {}
  	// 3. this에 프로퍼티들을 추가
    this.name = name
    this.age = age
    this.birthday = birthday
  	// 4. this를 반환 - 실제 코드는 아님
  	return this
}

new 함수명(); // 1. 실행하면
```



> **사용예시**

```javascript
function User(name, age, birthday) {
    this.name = name
    this.age = age
    this.birthday = birthday
  	this.sayName = function(){
      console.log(this.name)
    }
}

let user3 = new User('Meri', 30, '93-01-01')
user3.sayName(); // 호출했을 때 this는 .앞의 user3 => 'Meri'가 출력됨
```





