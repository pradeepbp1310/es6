# Core ES6 features

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
function a(x,y){
return ''+x+' and '+y+''; // concatenating using +
}
a(2,3);

### Template literals
function a(x,y){
return `${x} and ${y}` // template literals `${x}`
}
a(2,3);

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
const [, year, month, day] =
    /^(\d\d\d\d)-(\d\d)-(\d\d)$/
    .exec('2999-12-31');
- The empty slot at the beginning of the Array pattern skips the Array element at index zero.