# Core ES6 features

## 0. From var to let/const
* ["From var to let/cons"](var-let-const.md)

## 1. From IIFEs to blocks
Restrict scope of a variable to blocks

### IIFE (Immediately Invoked Function Expression)
```javascript
(function(){ // open IIFE
	var x = 3;
}()) // close IIFE
console.log(x); // ReferenceError
```

### Using block and let/const
```javascript
if(true){ // open block
	let x = 3;
} // close block
console.log(x); // ReferenceError: x is not defined 
```
In the above example x can not be accessed outside if block.

## 2. From concatenating strings to template literals
### String concatenation
```javascript
function a(x,y){
return ''+x+' and '+y+''; // concatenating using +
}
a(2,3);
```

### Template literals
```javascript
function a(x,y){
return `${x} and ${y}` // template literals `${x}`
}
a(2,3);
```
Also template can span mulitple lines  using literals
```javascript
const a = `this is multiple line strings,
this can be achieved wit the help of teplate literals
`;
```

## 3. From function expressions to arrow functions
```javascript
var arr = [1, 2, 3];
var squares = arr.map(function (x) { return x * x });
```
to
```javascript
const arr = [1, 2, 3];
const squares = arr.map(x => x * x);
```

## 4. Destructuring 
Handling multiple return values
```javascript
var matchObj =
    /^(\d\d\d\d)-(\d\d)-(\d\d)$/
    .exec('2999-12-31');
var year = matchObj[1];
var month = matchObj[2];
var day = matchObj[3];
```

Handling multiple return values via destructuring
```javascript
const [, year, month, day] =
    /^(\d\d\d\d)-(\d\d)-(\d\d)$/
    .exec('2999-12-31');
```
- The empty slot at the beginning of the Array pattern skips the Array element at index zero.

## 5. From for loop to forEach to for-of
### for loop
```javascript
// pros: break and continue
// cons: initialisation var i = 0; Condtion i<arr.length; end point i++
var arr = ['a','b','c','d'];
for(var i =0; i<arr.length; i++){
	console.log(arr[i]);
}
```
### forEach
```javascript
// pros: concise, less code, pass function as parameter
arr.forEach(el=>console.log(el));
```

Pass function as parameter to forEach
```javascript
const num = [1,2,3,4,5,6];
let sum = 0;
function addNumber(number){
	sum+=number;
}
num.forEach(addNumber); // Passing addNumber function as parameter to forEach
console.log(sum); //21
```

### for-of
// for-of combines both advantages
```javascript
var arr = ['a','b','c','d'];
for(const ele of arr){
	console.log(ele);
}
```

Get both index and values using array.entries() and destructuring
```javascript
// to get both index and values using array.entries() and destructuring
	for(const[index, ele] of arr.entries()){
		console.log(index, ele);
	}
```
