# ECMAScript6 (ECMAScript201)


## ECMAScript 6 란?
- ECMA(European Computer Manufacturers Association 유럽 컴퓨터 제조업체 협회)Script란? ECMA 인터네셔널의 ECMA-262 기술 규격에 정의된 표준화된 스크립트 프로그래밍 언어이며, 그 버전명칭을 줄여서 국내에서 아직까지 널리 사용하고 있는 자바스크립트 버전이 ES5이며, 2015년 6월 개정된 버전이 바로 ES6 또는 ES2015라고도 부릅니다. 

![title](https://github.com/jangmang/pub/blob/master/1.PNG "es6")


## ECMAScript 6 왜?
- 좀더 직관적이고 간결하다.
- 개선된 문법으로 오류가 줄어들었다.
- 해외 대다수 사이트에서 표준으로 자리잡았다.
- Nodejs도 4버전부터는 ES6을 도입하였고, AngularJs, React, Vue.js등도 ES6에 맞춰 개편되었다.

![title](https://github.com/jangmang/pub/blob/master/2.PNG "es6")

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

## Destructuring assignment(비구조화 할당)

### ES5
```
var numbers = [1, 2, 3];

var a = numbers[0];
var b = numbers[1];
var c = numbers[0];
var d = numbers[2];

console.log(a + ", " + b);  // "1, 2"
console.log(c + ", " + d);  // "1, 3"
```

### ES6
```
let numbers = [1, 2, 3];

let [a, b] = numbers;
let [c, , d] = numbers;

console.log(`${a}, ${b}`); // "1, 2"
console.log(`${c}, ${d}`); // "1, 3"
```
- 비구조화할당이란? 간단히 말하자면 배열이나 객체의 요소를 해체하여 별개의 변수로 추출할 수 있도록 하는 것입니다.
- 길이가 일치하지 않아도 남는부분은 무시하고 할당하거나, c와 d사이의 빈값을 둠으로 할당할 배열에서 해당 위치의 값은 제외하고 할당할 수도 있다.

## Spread operator (전개 연산자)

### ES5
```
var a = [1, 2, 3];
var b = "전개연산자";

var c = a.concat(b);

console.log(c);

// [1,2,3,”전개연산자”]
```

### ES6
```
const a = [1,2,3];
const b = [...a].reverse();

console.log(`a : ${a} 
b : ${b}`);

// a는 변화없음
```
- 전개연산자를 이용하면 코드가 간결해질뿐만 아니라, 특히 배열은 push, reverse 와 같은 여러가지 메서드를 가지고 있는데 이런 메서드들은 기존 배열을 바꿔버리는 단점이 존재한다. 하지만 전개연산자를 이용하면 기존의 배열은 유지하면서 새로운 변수를 추가할 수 있다.
- 앞에서 설명한 비구조화 할당 방식에 이용하여 배열의 나머지요소를 할당 받을 수도 있다.

## Enhanced object literals(향상된 객체 리터럴)

### ES5
```
var name = ＂장명호";
var job = ＂더브리즈";

var inf = {
  name: name,
  job: job
}

console.log(inf);
//{name: ＂장명호＂, job: ＂더브리즈"}
```
- ES6 이전에는 객체를 생성할 때, 필드명과 대입할 변수명이 같은 상황에서 다음과 같이 코드를 작성하였다.

### ES6
```
const name = “장명호";
const job = ＂더브리즈";

const inf = {
  name,
  job
}

console.log(inf);
//{name: ＂장명호＂, job: ＂더브리즈"}
```
- ES6에서는 단순히 변수명만 작성해주면 변수명과 동일한 필드가 생성되며, 그 변수값이 대입된다.

## 간결한 메서드

### ES5
```
var person = {
  name: "장명호",
  getName: function() {
    return this.name;
  }
}

console.log(person.getName());
//장명호
```
- ES6 이전에는 객체 메서드를 정의하기 위해 function 키워드를 사용하였다.

### ES6
```
var person = {
  name: "장명호",
  getName() {
    return this.name;
  }
}

console.log(person.getName());
//장명호
```
- ES6에서는 function 키워드가 없어지고, 더욱 간결해진 객체 리터럴을 사용 할 수있다.

## For-of(for-in과 의 차이점)

### For-in
```
let list = ["a", "b", "c"];

for (let i in list) {
	console.log(i); //"0", "1", "2"
}
```
- 객체의 요소들을 순회하기 위한 구문으로 index값이 문자로 반환된다.

### For-of
```
let list = ["a", "b", "c"];

for (let i of list) {
	console.log(i); //"a", "b", "c"
}
```
- 객체의 속성 또는 배열의 요소를 순회하기 위한 구문으로 for-in문의 단점을 보완하여 간결하고 직접적으로 접근이 가능하도록 추가되었다


## Class

### ES5
```
function Person(name, job) {
  this.name = name;
  this.job = job;
}

Person.prototype.print = function() {
  console.log(this.job + "의 " + this.name + " 대리");
}

var result = new Person("장명호", "더브리즈");
result.print();

//더브리즈의 장명호 대리 
```
- ES6 이전에는 공식적으로 클래스라는 개념이 존재하지 않았으며, 함수를 사용하여 객체를 정의했다. 그리고 객체의 메서드를 정의할때는 prototype 안에 직접 정의해줬다.

### ES6
```
class Person {
  constructor(name, job) {
    this.name = name
    this.job = job
  }
  print() {
    console.log(`${this.job}의 ${this.name} 대리`);  
  }
}

var result = new Person("장명호", "더브리즈");
result.print();

//더브리즈의 장명호 대리 
```
- ES6에서는 class가 등장하여, 그안에 메서드를 정의할 수 있게 되었다. constructor는 인스턴스를 생성하고 클래스 프로퍼티를 초기화하기 위한 특수한 메소드이다. 클래스 내에 한 개만 존재할 수 있으며, 파라미터에 전달한 값은 클래스 프로퍼티에 할당한다. 


## Es6 browser support (브라우저 지원)

https://kangax.github.io/compat-table/es6/

- Internet Explorer를 제외하고는 대체로 커버가 되고 있다.
- 브라우저별 지원율이 상이하고, 특히 국내에서는 상대적으로 IE 브라우저의 점유율이 높기 때문에 아직까지는 그대로 사용 할 수가 없다.
- Babel이라는 transpiler를 이용하여 es6에서 es5로 변환시켜 줄 수 있다.

![title](https://github.com/jangmang/pub/blob/master/1.PNG "es6")

## Babel 설치

공식사이트 : https://babeljs.io/

1. 먼저 작업하고자 하는 프로젝트 폴더를 지정한다.
2. npm init -y // package.json 생성
3. npm install babel-cli babel-preset-env --save-dev // 바벨 & 프리셋(특정기능을 지원하는 플러그인 모음) 설치
4. package.json 수정
```
"scripts": {
	"start": "npm run watch", //실시간 감시하여 변경사항이 있으면 웹페이지를 새로고침
	"babel": "node_modules/.bin/babel source -d dist", // 바벨경로 지정
	"watch": "npm run babel -- -w",  // 파일을 수정할때마다  내보냄
	"build": "babel source -w -d dist"  // "build": "babel {소스디렉토리} -w -d {출력디렉토리}”
}
```
5. .babelrc 파일을 만들어 안에 내용 넣기
```
{
   "presets" : ["env"] // 공식 스펙에서 지원하지 않는 기능들을 플러그인 옵션으로 추가
}
```
6. npm run build // 트랜스파일링 실행

- npm i –g live-server //라이브서버설치
- live-server //라이브서버실행

Thank you






