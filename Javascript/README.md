# Javascript interview question

### Q1: What is javascript?
> Difficulty : ⭐

**Javascript** is a client-side as well as server side scripting language that can be inserted into HTML pages and is understood by web browsers.

### Q2: What are JavaScript Data Types?
> Difficulty : ⭐

Following are the JavaScript Data types:
- `Number`
- `String`
- `Boolean`
- `Object`
- `undefined`
- `null`

### Q3: What is the use of isNaN function?
> Difficulty : ⭐

`isNan` function returns true if the argument is not a number otherwise it is false.

### Q3: What are undeclared and undefined variables?
> Difficulty : ⭐⭐

Undeclared variables are those that do not exist in a program and are not declared. If the program tries to read the value of an undeclared variable, then a runtime error is encountered.

Undefined variables are those that are declared in the program but have not been given any value. If the program tries to read the value of an undefined variable, an undefined value is returned.

### Q4:  What is DOM? What is the use of document object?
> Difficulty : ⭐⭐

**DOM** stands for Document Object Model. A document object represents the HTML document. It can be used to access and change the content of HTML.

### Q5: What is the difference between == and ===?
> Difficulty : ⭐⭐

The == operator checks equality only whereas === checks equality, and data type, i.e., a value must be of the same type.

### Q6: What is the output of `10+20+"30"` in JavaScript?
> Difficulty : ⭐⭐⭐

<details>
  <summary><b>Answer</b></summary>
  <code>3030</code>
  <p>Because 10+20 will be 30. And 30 + "30" will become string concat so the answer is "3030"</p>
</details>

### Q7: What is the output of "10"+20+30 in JavaScript?
> Difficulty : ⭐⭐⭐

<details>
  <summary><b>Answer</b></summary>
  <code>102030</code>
  <p>Because after a string all the + will be treated as string concatenation operator (not binary +).</p>
</details>

### Q8: What is the difference between undefined value and null value?
> Difficulty : ⭐⭐⭐

**Undefined value**: A value that is not defined and has no keyword is known as undefined value. For example:
```javascript
var undefinedVar;
```

**Null value**: A value that is explicitly specified by the keyword "null" is known as a null value. For example:
```javascript
var nullVar = null;
```

### Q9: How can we detect OS of the client machine using JavaScript?
> Difficulty : ⭐⭐⭐

The `navigator.appVersion` property can be used to detect the operating system on the client machine.

### Q10: Differences between `.forEach` and `.map` in Javascript?
> Difficulty : ⭐⭐⭐

**`forEach`**:
- Base on element from array
- Callback will be called at every loop
- Return void

**`map`**:
- Base on element from array
- Callback will be called at every loop
- Return new array of elements base on return variable of callback function

### Q11: What is Higher order function?
> Difficulty : ⭐⭐⭐

**Higher order function** is a function that take other function as parameter. For example:

```javascript
function execute(callback, num){
    return callback(num);
};

function double(num){
    return num * 2;
}

execute(double,2); // 4
```

### Q12: What is IIFE (Immediately Invoked Function Expression)?
> Difficulty : ⭐⭐⭐

An **IIFE** is a JavaScript function that runs as soon as it is defined. For example: 
```javascript
(function () {
    statements
})();
```

### Q13: Explain asynchronous in Javascript?
> Difficulty : ⭐⭐⭐⭐

JavaScript is a single-threaded programming language which means only one thing can happen at a time. That is, the JavaScript engine can only process one statement at a time in a single thread. By using asynchronous JavaScript (such as callbacks, promises, and async/await), you can perform long network requests without blocking the main thread.

### Q14: What is `Promise` in JavaScript?
> Difficulty : ⭐⭐⭐⭐

The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value.

```javascript
var promise1 = new Promise(function(resolve, reject) {
  setTimeout(function() {
    resolve('foo');
  }, 300);
});

promise1.then(function(value) {
  console.log(value);
  // expected output: "foo"
});

console.log(promise1);
// expected output: [object Promise]
```

### Q15: What is `Promise.all()` method in JavaScript for?
> Difficulty : ⭐⭐⭐⭐

Promise.all is actually a promise that takes an array of promises as an input (an iterable). Then it gets resolved when all the promises get resolved or any one of them gets rejected.

### Q16: Write a function to compare 2 objects in JavaScript
> Difficulty : ⭐⭐⭐⭐⭐

```javascript
let a = {
  name: "a",
  age: 15,
  classRoom: {
    size: 15
  }
}

let b = {
  name: "a",
  age: 15,
  classRoom: {
    size: 15
  }
}

function compareObject(o1, o2){
  for(key in o1){
    if(o2[key] === undefined){
      return false;
    }
    if(typeof o1[key] !== 'object'){
      if(o1[key] !== o2[key]){
        return false;
      }
    }
    else{
      let compareObj = compareObject(o1[key],o2[key]);
      if(compareObj === false){
        return compareObj;
      }
    }
  }
  return true;
}

compareObject(a,b); // true
```

### Q17: What is the result of this code:
```javascript
const a = [1, 2, 3]
const b = [1, 2, 3]
const c = "1,2,3"

console.log(a == c)
console.log(a == b)
```
> Difficulty : ⭐⭐⭐⭐⭐

<details>
  <summary><b>Answer</b></summary>
  <code>
  true 
  <br>
  false
  </code>
</details>

### Q18: What is the result of this code:
> Difficulty : ⭐⭐⭐

```javascript
console.log(typeof typeof 0);
```

<details>
  <summary><b>Answer</b></summary>
  <code>string</code>
</details>

### Q18: What is the result of this code:
> Difficulty : ⭐⭐⭐⭐⭐

```javascript
var a = [1,2,3];

a[10] = 99;

console.log(a);
console.log(a[6]);
```
<details>
  <summary><b>Answer</b></summary>
  <code>
    <p>[ 1, 2, 3, <7 empty items>, 99 ]</p>
    <p>undefined</p>
  </code>
</details>

### Q19: What is the result of this code:
> Difficulty : ⭐⭐⭐⭐⭐

```javascript
var x = 1;
var output = (function () {
  delete x;
  return x;
})();

console.log(output);
```
<details>
  <summary><b>Answer</b></summary>
  <code>
    <p>1</p>
  </code>
</details>

### Q20: What is hoisting in JavaScript?
> Difficulty : ⭐⭐⭐

<details>
  <summary>Answer</summary>
  <p>
  Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution. Inevitably, this means that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local.
  </p>
</details>

**Example:**
```javascript
function hoist() {
  a = 20;
  var b = 100;
}

hoist();

console.log(a);
/*
Accessible as a global variable outside hoist() function
Output: 20
*/

console.log(b);
/*
Since it was declared, it is confined to the hoist() function scope.
We can't print it out outside the confines of the hoist() function.
Output: ReferenceError: b is not defined
*/
```

### Q21: What's the difference between using “let” and “var”?
> Difficulty : ⭐⭐



<details>
  <summary>Answer</summary>
 <p>
    Refference this stackoverflow' s <a href="https://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var">answer</a>
  </p>
</details>

### Q22: The differences between require and import in Node.js?
> Difficulty : ⭐⭐⭐

1. When using `import ... from ...`, the module path must be a string literal. When using `require`, the module path can be dynamic.
```javascript
// This work
const name = "module2";
const obj = require(`./${name}`);


// result in a syntax error.
const name = "module2";
const obj = require(`./${name}`);
```
2. `require` run synchronically when `import` run asynchronically

3. You can leave out a `.js` extension when importing a local module with `require`, but cannot do the same when using `import`.

>Furthermore, **webpack** has an option that changes this behavior. Specifically, if `resolve.enforceExtension` is true, then extensions are required. This option is set to false by default, which explains why in many frameworks (like **Next.js**, which uses webpack behind the scenes) you can use `import` without specifying file extensions.