## 반복문

### for문

```java
// 기본 구조
for (let i = 0; i < 10; i++) {
  console.log(i);
}

// IE 사용가능
for (const i in ["one", "two", "three"]) {
  console.log(i);
}

// IE에서 사용불가
for (const i of ["one", "two", "three"]) {
  console.log(i);
}

// 앞 뒤 숫자 차이 비교
let data3 = [1, 3, 4, 8, 13, 17, 20];
for (let i = 0; i < data3.length - 1; i++) {
  console.log(data3[i + 1] - data3[i]);
}
// 다른 방법
let data4 = [1, 3, 4, 8, 13, 17, 20];
for (let i = 1; i < data4.length; i++) {
  console.log(data4[i] - data4[i - 1]);
}
```

<br>

> **조건구문 생략**
>
> ```javascript
> // 아래와 같이 세미콜론만 찍으면 for문의 조건구문을 생략할 수 있다.
> let i = 0;
> for (;;) {
>   i++;
>   console.log(i);
>   if (i > 5) {
>     break;
>   }
> }
> 
> for (let i = 0; ; ) {
>   i++;
>   console.log(i);
>   if (i > 5) {
>     break;
>   }
> }
> 
> for (let i = 0; ; i++) {
>   console.log(i);
>   if (i > 5) {
>     break;
>   }
> }
> 
> // 무한루프 - (따라하지마시오!)
> for(;;) console.log('hello')
> ```

<br>

### while문

```javascript
// 기본 구조
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}

// 무한루프 - (따라하지마시오!)
while (true) {
  console.log("무한반복!!");
}
```

<br>

> **break**
>
> ```javascript
> // break는 반복문 하나를 빠져나간다.
> for (let i = 0; i < 10; i++) {
>   console.log(i);
>   if (i > 3) {
>     break;
>   }
> }
> ```

<br>

> **continue**
>
> ```javascript
> // continue는 다음 루프로 갑니다.
> let i = 1;
> let j = 1;
> while (i < 9) {
>   i++;
>   if (i == 4) {
>     continue; // continue로 인해 4단을 뛰어넘고 5단부터 다시 시작됨
>   }
>   while (j < 10) {
>     console.log(`${i} X ${j} = ${i * j}`);
>     j++;
>   }
>   j = 1;
> }
> ```

<br>

### for-of 와 for-in

따로 블로그에 정리하겠습니다.