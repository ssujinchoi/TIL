## This

- this는 이 두 경우에서 객체를 가리키는 자기 참조 변수
- 자신을 호출한 객체
- 자신이 생성할 객체

> 



```javascript
// window객체가 b함수를 가지고 있는 것
function b(){
	console.log('hello world')
}
b() // window.b()
```



