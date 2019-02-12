# Core ES6 features

## From var to const/let
Declaring a variable with var that means variable can be accessed anywhere within the function. In turn variable with var keyword is function scope.

### var
```javascript
var x = 3;
function f(random){
if(random){
	var x = Math.random(); 
	return x;
}
return x;
}
f(false); // undefined
``` 

What is going here? Why you got undefined in the above code. This is how it breaks down
```javascript
var x = 3;
function f(random){
var x;
if(random){
	x = Math.random();
	return x;
}
return x;
}
f(false); // undefined
```

### let
- let/const is block scoped, variable with let/const can only be accessed within the defined block for ex. if(){let x}.
- Use let whenever the variable values changes in future for ex. in iterations use let.
- Use const when variable values never changes again in future.

```javascript
let y = 3;
function f(random){
if(random){
	let y = Math.random();
	return y;
}
return y;
}
f(false) // 3
``` 

## Summary
- Prefer const over let, when varibale value never changes in future
- Use let when varibale value changes in future
- Avoid using var

## ToDO
Add more examples

