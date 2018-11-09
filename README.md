# ECMAScript6 (ECMAScript201)


## ECMAScript 6 란?
- ECMA(European Computer Manufacturers Association 유럽 컴퓨터 제조업체 협회)Script란? ECMA 인터네셔널의 ECMA-262 기술 규격에 정의된 표준화된 스크립트 프로그래밍 언어이며, 그 버전명칭을 줄여서 국내에서 아직까지 널리 사용하고 있는 자바스크립트 버전이 ES5이며, 2015년 6월 개정된 버전이 바로 ES6 또는 ES2015라고도 부릅니다. 

## ECMAScript 6 왜?
- 좀더 직관적이고 간결하다.
- 개선된 문법으로 오류가 줄어들었다.
- 해외 대다수 사이트에서 표준으로 자리잡았다.
- Nodejs도 4버전부터는 ES6을 도입하였고, AngularJs, React, Vue.js등도 ES6에 맞춰 개편되었다.

## LET

###ES5
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

###ES6
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


