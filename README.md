# ECMAScript6 (ECMAScript201)


## ECMAScript 6 란?
- ECMA(European Computer Manufacturers Association 유럽 컴퓨터 제조업체 협회)Script란? ECMA 인터네셔널의 ECMA-262 기술 규격에 정의된 표준화된 스크립트 프로그래밍 언어이며, 그 버전명칭을 줄여서 국내에서 아직까지 널리 사용하고 있는 자바스크립트 버전이 ES5이며, 2015년 6월 개정된 버전이 바로 ES6 또는 ES2015라고도 부릅니다. 
![title](https://github.com/jangmang/pub/blob/master/1.PNG "es6")


## ECMAScript 6 왜?
- 좀더 직관적이고 간결하다.
- 개선된 문법으로 오류가 줄어들었다.
- 해외 대다수 사이트에서 표준으로 자리잡았다.
- Nodejs도 4버전부터는 ES6을 도입하였고, AngularJs, React, Vue.js등도 ES6에 맞춰 개편되었다.

## LET

### ES5
```
function foo(){
	if(true){
		var a = ‘bar’;
	}
	console.log(a);
}

foo();

// bar
```
- 정상적으로 bar 이라는 문자열을 출력하는 모습을 볼 수 있다. 여기서 변수 a 는 foo 함수에서 전역으로 영향력을 같게 된다. 그렇기 때문에 if 문의 scope 안에서 선언된 변수도 밖에서 접근이 가능하다.


### ES6
```
function foo(){
	if(true){
		let a = ‘bar’;
	}
	console.log(a);
}

foo();

// error
```
- 하지만 let 으로 선언한 변수는 if문의 scope 내에서만 유효하기 때문에 해당 scope 밖에서 a 에 접근할때, 오류가 발생한다.

## CONST

### ES6
```
let foo = 1;
foo = 2;
console.log(foo);
// 2 

const bar = 1;
bar = 2;
// error
```
- let 으로 선언된 변수는 오류가 없지만, const 로 선언된 상수는 값을 변경할 수 없다는 오류가 발생한다.

## Arrow Function (화살표 함수)

### ES5
```
var vm = function() {
	console.log(“함수실행”);
}

vm();
```

### ES6
```
const vm = () => {
	console.log(“화살표 함수실행”);
}

vm();
```

## Parameter (파라미터)

### ES5
```
var vm = function(a, b) {
	console.log(a, b);
}

vm(‘값1’);

//값1, undefined
```

### ES6
```
const vm = (a, b=‘값2’) => {
	console.log(a, b);
}

vm(‘값1’);

//값1, 값2
```
- ES6 이전에서는 파라미터의 값이 들어오지 않으면 무조건 undefined 가 됐지만, ES6 부터 그 기본값을 설정할 수 있다.

```
const vm = a => {
	console.log(a);
}

vm(‘값1’);
```
- 파라미터를 1개만 받을때는 괄호를 생략할 수 있다.

## Template literal (템플릿 리터럴)

### ES5
```
var name = “장명호”;
var office = “더브리즈”;

console.log(office + “의” name + “입니다”);

//더브리즈의 장명호입니다
```
- ES6 이전에서는 변수와 문자열을 결합하는 +를 사용하여 가독성이 매우 떨어져 실수가 발생하기 쉬웠다.

### ES6 
```
let name = "장명호";
let office = "더브리즈";

console.log(`${office}의 
${name}입니다.`);

/*더브리즈의
장명호입니다*/
```
- 백틱으로 문자열을 감싸고 그 사이에 ${변수명} 으로 표현해주면, 해당 변수의 값이 그대로 다른 문자열과 같이 출력된다. 템플릿 리터럴은 일반 문자열 리터럴과 다르게 공백과 개행을 그대로 표현해준다.




