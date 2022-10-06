<script>
</script>는 html다 불러오고 난 다음에 사용 많이 함. 따라서 보통 body태그 끝나는 지점 앞에 사용
1. html 
2. 별도의 js파일 (<script> src="")

document.write(); - 브라우저 화면에 글 쓰기



#### 세미콜론

보통 하나의 명령어가 끝났다를 의미하지만 자스는 유연한 언어라 세미콜론을 안 넣어줘도 된다. 단 한줄에 여러 명령어일땐 세미콜론으로 구분해줘야한다.



#### 주석

컴퓨터가 읽을 수 없는글

1. 코드 설명을 적어줄 때
2. 코드를 동작시키고 싶지 않을 때
3. 자스의 주석은  한줄은 //, 여러줄은 /* */



#### 변수

데이터 담을 수 있는 상자라고 생각하면 됨

var name = '엄준식';

var age = '21'

ES6이후 부터는 아래처럼 바뀜
let 변수명  = 값;

const 변수명 = 값;   // 변하지 않는 상수값



#### 자료형

1. 문자열(String) : "홍길동" , '홍길동'
2. 숫자형(int, float) : 정수형(30) , 실수형(1.2)
3. 불(bool) : true, false (1과 0)
4. typeof 데이터 - 자료형을 알 수 있는 함수



#### 로또번호 추첨기 만들기

Math.random(); => 0이상~1미만 실수(float) 

=> 1이상~46미만 실수가 필요하므로 *45 => 1부터 45가 필요하므로 +1
=> 소수점 버리고 정수가 필요하므로 parseInt(); var

```javascript
var num = Math.random * 45 + 1;
var ball1 = parseInt(num);
```

로또번호는 여러개를 추첨해야한다.

```javascript
var ball1 = 1;
var ball2 = 2;
.... 하나씩 넣어줘도 되지만
필요한 번호가 몇백개씩 된다면 하나하나 변수 지정 해주기 힘들다 
=> 따라서 Array(배열)을 사용한다.
var lotto = [1,2,3,4,5,6];
lotto[index번호] 로 index위치의 값을 가져올 수 있다.
index는 0 부터 시작한다.

lotto.push => 마지막 값 추가


<script>
  var lotto = [];
  lotto.push(parseInt(Math.random() * 45 + 1));
  lotto.push(parseInt(Math.random() * 45 + 1));
  lotto.push(parseInt(Math.random() * 45 + 1));
  lotto.push(parseInt(Math.random() * 45 + 1));
  lotto.push(parseInt(Math.random() * 45 + 1));
  lotto.push(parseInt(Math.random() * 45 + 1));
  document.write(lotto);
</script>
```



#### 반복문(for, while)

for(시작; 끝; 증가) {

​	반복하려는 코드

}

```javascript
var lotto = [];
for(var i=0; i<6; i++) {
	lotto.push(parseInt(Math.random() * 45 + 1));
}

단, 이렇게 되면 중복된 번호가 들어가게된다.
```



#### if 조건문

if(조건) {

​	참일 경우

}

```javascript
우리가 만들어야하는 코드는 만약 중복이 아니라면 lotto배열에 랜덤 값을 넣어주는 것이다.
.indexOf(값) : 값이 있으면 위치, 없으면 -1

var lotto = [];
for(var i = 0; i < 6; i++) {
  var num = parseInt(Math.random() * 45 + 1);
  if(lotto.indexOf(num) == -1) { // 배열안에 값이 없으면...
    lotto.push(num);
  }
 	document.write(lotto);
}
```



#### while 반복문

while(조건) {

​	반복하려는 코드

}

```javascript
.length => 배열의 길이

var lotto = [];
while(lotto.length < 6) {
  var num = parseInt(Math.random() * 45 + 1);
  if(lotto.indexOf(num) == -1) { // 배열안에 값이 없으면...
    lotto.push(num);
  }
 	document.write(lotto);
}

숫자정렬
lotto.sort((a,b)=>a-b); // 오름차순 정렬
lotto.sort((a,b)=>b-a); // 내림차순 정렬
```

