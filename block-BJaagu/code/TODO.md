Find the output of the code snippets below:

```js
console.log(numA + numB); //NAN undefined
var numA = 21,
  numB = 30;

// Since variables in Declaration phase are initialized with undefined and in Execution phase we are logging before assigning value to these variables.
```

Find the output of the code snippets below:

```js
console.log(numA + numB); //ReferenceError: numA is not defined
let numA = 21,
  numB = 30;

// Becasuse let does not initialize the variable just creates a box and is empty. So when we logg first during execution phase numA is empty hence it says error its not defined.
```

Find the output of the code snippets below:

```js
let numA = 21,
  numB = 30;
console.log(numA + numB); //51
// This time during execution phase the values are initialized and only then we are logging them so it gives the output.
```

Find the output of the code snippets below:

```js
console.log(sayHello()); // Hello
function sayHello() {
  console.log("Hey");
}
function sayHello() {
  console.log("Hello");
}

// 
```

Find the output of the code snippets below:

```js
let username = "Tyrion";
sayHello(); // Tyrion
function sayHello() {
  console.log(username);
}

// Because username was defined in Global scope so during Execution phase, when sayHello() is called it will log username where value of 'Tyrion' was already initialized during execution in GEC.
```

Find the output of the code snippets below:

```js
sayHello(); // ReferenceError: username is not defined
let username = "Tyrion";
function sayHello() {
  console.log(username);
}

// Since here username is declared using let keyword so it does not initialize the variable just creates a box. Therefore when sayHello() was called before initializing username with a value, henec it throws an error `username is not defined`.
```

Find the output of the code snippets below:

```js
let username = "Tyrion";
sayHello(); // ReferenceError: sayHello is not defined
let sayHello = () => {
  console.log(username);
};

// Since sayHello is a function expression it wont be hoisted on top and will be initially empty because its declared using let keyword. Hence during function call it returns not defined.
```

Find the output of the code snippets below:

```js
sayHello(); // ReferenceError: sayHello is not defined
let username = "Tyrion";
let sayHello = () => {
  console.log(username);
};

// This would not make any difference from the scenario above because sayHello is still a function experession and wont be hoised on top and due to let keyword its empty initialization.
```

Find the output of the code snippets below:

```js
sayHello(); // ReferenceError: sayHello is not defined
var username = "Tyrion";
let sayHello = () => {
  console.log(username);
};

// Here we have used var but still its declared with unidefined during declaration phase. And in Execution phase we are calling sayHello function first which will return not defined because sayHello is a function experession and wont be hoisted on top and is also defined using let keyword so is empty.
```

Find the output of the code snippets below:

```js
var username = "Tyrion";
sayHello(); // ReferenceError: sayHello is not defined
let sayHello = () => {
  console.log(username);
};

// Here username in Global scope will get initialized with value as 'Tyrion' during execution phase, but still since sayHello() is function execution and was declared using let, so it was empty hence it says not defined during function call.
```

Find the output of the code snippets below:

```js
var username = "Tyrion";
let sayHello = () => {
  console.log(username);
  var username = "John";
};
sayHello(); // undefined

// During execution phase Global scope username variable will be initialized with 'Tyrion' inside it.next sayHello function expression will go through Declaration and execution phase. In this username is logged and it cannot access the Global username because of let keyword being function scope and also since the next line username is undefined after declaration phase and has not reached execution phase yot so there wont be John value inside it yet, hence it'll log `undefined`.
```

Find the output of the code snippets below:

```js
var username = "Tyrion";
let sayHello = () => {
  var username = "John";
  console.log(username);
};
sayHello(); // John

// The same procedure will reprate in Global scope as above piece of code. But in sayHello function expression since username will have value John after execution phase and is declared before logging hence during console.log(username) it'll fetch the value John from the FEC's local memory.
```

Find the output of the code snippets below:

```js
var username = "Tyrion";
let sayHello = () => {
  console.log(username);
  let username = "John";
};
sayHello(); // ReferenceError: Cannot access 'username' before initialization

// The same procedure will reprate in Global scope as above piece of code.In execution phase of sayHello function execution it'll not initialize username variable since it is decalared using let keyword. And during logging username it wont be able to access that username since it was empty.
```