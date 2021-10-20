1. Convert the function below into different forms of function expression.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}

// Your code goes here
// Function Expression
let percent = function percentage(marks,total){
  return (marks * 100) / total;
}
// Arrow Function
let percent = (marks,total) => {
  return (marks * 100) / total;
}
// Arrow function with Implicit return
let percent3 = (marks,total) => (marks * 100) / total;
```

2. Write Function Declaration or Function Expression next to the function.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}
// Function Declaration
```

```js
let percentage = function percentage(marks, total) {
  return (marks * 100) / total;
};
// Function Expression
```

```js
let percentage = function (marks, total) {
  return (marks * 100) / total;
};
// Function expression
```

```js
let percentage = (marks, total) => {
  return (marks * 100) / total;
};
// Function expression Arrow function
```

```js
let percentage = (marks, total) => (marks * 100) / total;
// Function Expression Arrow function with implicit return
```

3. Why is a function definition an expression in JavaScript? Give one example of function expression.
A function definition is a way of writing a function where we use the 'function' keyword while creating the function, whereas a function expression is storing the function in a variable. This can be done because in JS, a an object is a value and can be stored in a variable and a function is a type of object in JS.
Example of function expression:
```js
let percentage = function (marks, total) {
  return (marks * 100) / total;
};
```

4. Why is a function call an expression in JavaScript?
A function expression is when we store the function in a variable and when we call this variable it return a value. Since an expression is anything that returns a value, so we can say that a function call is an expression in JS.  

5. Write VALID and INVALID next to each example below with the reason.

```js
function add(a, b) {
  return a + b;
}

let five = add(2, 3); // 5. VALID because variable five has stored the result of add function.
five = add; // Will return the function itself. i.e reference. VALID
five = five(10, 11); // VALID. Since we can use any name for the function and it can be same as the variable it is stored in. The variable will return 21.

five = function () {
  return 'Hello';
}; // VALID. 'five' variable returns the function itself. i.e reference. We can store any value in a variable and since function is a variable its acceptable. 
```

6. What is the difference between function definition and function call? Explain with an example.
A function definition is different ways you can define a function i.e different ways/steps you can define in order for the expected task to get executed. And to execute these steps you call the function know as function call/execution. 
A vague example: Making Tea!
Function definition - Boil water, Add milk, ingredients etc steps.
Function call - oredering to make me some tea.

7. What is the similarities between function definition and function call?
We have parentheses while defining a function as well as calling a fuction. 
We can use the same name of variable of function expression to call a function. 
For example:
```js
let percentage = (marks, total) => {
  return (marks * 100) / total;
};
percentage(60,100);
```

8. Is the code below valid or invalid. Explain with reason.

```js
function hello() {
  console.log('Hello World!');
}

hello.user = 'Sam'; // VALID. Function is an object in JS so we can add a value to a key user called sam. Also the function hello when called will print 'Hello World' in the console but since no return statement is used it will return undefined when called.
```

9. What is higher order function explain with an example.
A higher order function is:
(a) When you pass a function definition as a parameter to another function then the later function becomes a higher order function.
OR
(b) When a function returns another function, then the prior function will be called a Higher Order Function.

Example:
```js
function isOdd(num){
  return num%2!==0;
}
function filterOdd(arr,fn){
    console.log(fn(10))
    return arr;
}
filterOdd([1,2,4,6,8],isOdd) // OUTPUT is false...because in the HOF filterOdd we have passed 10 which gets passed to the isOdd Function and since 10 is not an odd number it returns false. 

//OR HOF is
function filterOdd(arr){
  return function abc(){
    //some code
  }
}
```


10. Explain what is callback function. Why you can pass a function inside a function?
When you pass a function reference as argument during a function call then its called a call back function. i.e from where the function's call started.
eg:
```js
filterOdd([1,3,5,6],isOdd) //Here filterOdd is a callback function and isOdd function is passed a its argument.
``` 