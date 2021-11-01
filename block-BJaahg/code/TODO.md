## Understanding Scope and the difference between var, let and const

Watch this video before doing the exercise: https://www.youtube.com/watch?v=XgSjoHgy3Rk

1. Guess the output:

```js
let firstName = 'Arya';
const lastName = 'Stark';
var knownAs = 'no one';

console.log(
  window.firstName, // undefined
  window.lastName, // undefined
  window.knownAs // 'no one'
);
```

2. Guess the output:

```js
let firstName = 'Arya';
const lastName = 'Stark';
var knownAs = 'no one';

function fullName(a, b) {
  return a + b;
}

console.log(window.fullName(firstName, lastName)); // AryaStark
// Since inside function's block scope let and const and var can all be accessed. 
```

3. Make a Execution Context Diagram for the following JS and write the output.

```js
fucntion addOne(num){
  return num + 1;
}
var one = addOne(0);
var two = addOne(1);
console.log(one, two); // 1 2
![Pic-3](./img/Pic-3.jpeg)
```

<!-- Pic 4 5 6 7 together ahead -->
4. Make a Execution Context Diagram for the following JS and write the output.

```js
var one = addOne(0);
fucntion addOne(num){
  return num + 1;
}
var two = addOne(1);
console.log(one, two); // 1 2
```

5. Make a Execution Context Diagram for the following JS and write the output.

```js
console.log(addOne(0)); // 1
fucntion addOne(num){
  return num + 1;
}
var two = addOne(1);
console.log(two); // 2
```

6. Make a Execution Context Diagram for the following JS and write the output.

```js
var one = addOne(0); // Uncaught ReferenceError: Cannot access 'addOne' before initialization
const addOne = (num) => {
  return num + 1;
console.log(two);
};
var two = addOne(1);
```

7. Make a Execution Context Diagram for the following JS and write the output.

```js
console.log(addOne(0)); //Uncaught ReferenceError: Cannot access 'addOne' before initialization. Defined using const so its empty during declaration phase.
const addOne = (num) => {
  return num + 1;
};
var two = addOne(1);
console.log(two);
```
![Pic-4567](./img/Pic-4567.jpeg)

8. What will be the output of the following

```js
function isAwesome() {
  var awesome;
  if (false) {
    awesome = true;
  }
  console.log(awesome); //undefined
}
isAwesome(); // undefined
```

9. What will be the output of the following

```js
function isAwesome() {
  let awesome;
  if (true) {
    awesome = true;
  }
  console.log(awesome); //true
}
isAwesome(); //undefined
```

10. What will be the output of the following

```js
function isAwesome() {
  let awesome;
  if (false) {
    awesome = true;
  }
  console.log(awesome); //undefined
}
isAwesome();//undefined
```

11. What will be the output of the following

```js
let firstName = 'Arya';
const lastName = 'Stark';
var knownAs = 'no one';

function fullName(a, b) {
  return a + b;
}
const name = fullName(firstName, lastName); //undefined
console.log(name); // Arya Stark
```

12. Guess the output of the code below with a reason.

```js
function sayHello() {
  let name = 'Arya Stark';
}
sayHello(); //undefined

console.log(name); //undefined
```

13. Guess the output of the code below with a reason.

```js
if (true) {
  var name = 'Arya Stark';
}
console.log(name); // "Arya Stark"
// Because var is not block scoped hence can be accessed from outside.
```

14. Guess the output of the code below with a reason.

```js
if (true) {
  let name = 'Arya Stark';
}
console.log(name); //"Arya Stark"
// name is on GEC memory and can be fetched by console.log()'s FEC.
```

15. Guess the output of the code below with a reason.

```js
for (var i = 0; i < 20; i++) {
  //
}
console.log(i); // 20
// i can be accessed outside the loop bec of var keyword. loop runs 19 times and then outside its value will be 20.
```

16. Guess the output of the code below with a reason.

```js
for (let i = 0; i < 20; i++) {
  //
}
console.log(i); // ERROR i is not defined.
// Here bec of let keyword i cannot be accessed outside the - for block scope.
```

17. Guess the output and the reason behind that.

```js
function sample() {
  if (true) {
    var username = 'John Snow';
  }
  console.log(username); // "John Snow"
}
sample(); // undefined
```

18. Guess the output and the reason behind that.

```js
function sample() {
  if (true) {
    let username = 'John Snow';
  }
  console.log(username); // ERROR username is not defined. Because of let keyword which is block scoped.
}
sample();
```

19. Guess the output and the reason behind that.

```js
function sample() {
  var username = 'Arya Stark';
  if (true) {
    var username = 'John Snow';
    console.log(username); // John Snow. Because of scope first immediate username will be accessed.
  }
  console.log(username, 'second'); // John Snow second
}
sample();
```

20. Guess the output and the reason behind that.

```js
function sample() {
  let username = 'Arya Stark';
  if (true) {
    let username = 'John Snow';
    console.log(username, 'first'); // John Snow first
  }
  console.log(username, 'second'); // Arya Stark second
}
sample();
```

21. Guess the output and the reason behind that.

```js
function sample(...args) {
  for (let i = 0; i < args.length; i++) {
    let message = `Hello I am ${args[i]}`;
    console.log(message);
  }
}

sample('First', 'Second', 'Third');
// Hello I am first
// Hello I am Second
// Hello I am Third
```

22. Guess the output and the reason behind that.

```js
function sample(...args) {
  for (let i = 0; i < args.length; i++) {
    const message = `Hello I am ${args[i]}`;
    console.log(message);
  }
}

sample('First', 'Second', 'Third');
// Hello I am first
// Hello I am Second
// Hello I am Third
```

23. Guess the output and the reason behind that.

```js
if (true) {
  const myFunc = function () {
    console.log(username, 'Second'); 
  };
  console.log(username, 'First'); // Uncaught ReferenceError: Cannot access 'username' before initialization
  let username = 'Hello World!'; // initialization is done only later
  myFunc();
}
```

24. Guess the output and the reason behind that.

```js
function outer() {
  let movie = 'Mad Max: Fury Road';
  function inner() {
    console.log(
      `I love this movie called ${movie.toUpperCase()}` // I love this movie called MAD MAX: FURY ROAD
    );
  }
  inner();
}

outer();
```

25. Guess the output and the reason behind that.

```js
function outer() {
  let movie = 'Mad Max: Fury Road';
  function inner() {
    let movie = 'Before Sunrise';
    console.log(
      `I love this movie called ${movie.toUpperCase()}` // I love this movie called BEFORE SUNRISE
    );
  }
  inner();
}

outer();
// As per scope the first inner ring is travelled then goes outside.
```

26. Guess the output and the reason behind that.

```js
function outer() {
  let movie = 'Mad Max: Fury Road';
  function inner() {
    let movie = 'Before Sunrise';
    function extraInner() {
      let movie = 'Gone Girl';
      console.log(
        `I love this movie called ${movie.toUpperCase()}` // I love this movie called GONE GIRL
      );
    }
    extraInner();
  }
  inner();
}
outer();
// As per scope the first inner ring is travelled then goes outside.
```

30. Using reduce find the final value when the initial value passed is `100`. You have to pass the output of one function into the input of next function in the array `allFunctions` starts with `addOne` ends with `half`.

```js
const addOne = (num) => {
  return num + 1;
};
const subTwo = (num) => {
  return num - 2;
};
const multiplyThree = (num) => {
  return num * 3;
};
const half = (num) => {
  return num / 2;
};

let allFunctions = [
  addOne,
  subTwo,
  multiplyThree,
  addOne,
  multiplyThree,
  half,
];

allFunctions.reduce((acc,cv) => {
  acc = cv(100);
  return acc;
},100)
// Answer is: 447
```
