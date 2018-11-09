ES6 스터디 PPT파일과 소스자료입니다.

<LET>
  
[ES5]
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

[ES6]
```
function foo(){
	if(true){
		let a = ‘bar’;
	}
	console.log(a);
}

foo();

// error

<CONST>
let foo = 1;
foo = 2;
console.log(foo);
// 2 

const bar = 1;
bar = 2;
// error
```


### 박세언 


