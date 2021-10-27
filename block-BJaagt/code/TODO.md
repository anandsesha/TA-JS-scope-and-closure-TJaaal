Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

Example:

```js
function hello() {
  var username = 'Arya';
}
console.log(useranme); // Error: usernme is not Defined
// In declaration phase hello is defined as a function and console.log() is skipped. But in Execution phase, the function hello() is not called and then we are trying to access username variable which will be created only when hello() is called inside its FEC's declaration phase. Hence throws error while trying to access from outside.
```

In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside the function named `hello` and we can't access the variable defined inside a function from outside.

The above code will throw an error `Reference Error username is not defined`.

2. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
{
  const username = 'Arya';
}
console.log(useranme); // Here we are looking for a variable `username` and its was declared inside the block scope by using const keyword. As we know const is both block and functional scoped so it will throw error while logging username `ReferenceError: useranme is not defined`. 
```

3. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  let username = 'Arya';
}
console.log(useranme); // ReferenceError: username is not defined
// Because we are trying to access username which is inside if block and declared using let keyword which is block scoped.
```

4. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  var username = 'Arya';
}
console.log(useranme); // Arya
// We are trying to access username variable which is decared using var and var is not block scoped hence we can access it from outside the scope.
```

5. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  var username = 'Arya';
}
console.log(useranme); // SyntaxError: Identifier 'username' has already been declared
// Since let created a variable username in Global scope and using var we created another variable username and since var is not block scoped it'll give access to username outside the scope. Therefore, while logging the username it'll throw error as we cannot declare two variables in global scope with same name.
```

6. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  let username = 'Arya';
}
console.log(useranme); // John
// Abthough the variable username inside block scope is created by let variable and is block scoped but still since there is a variable declared in global scope, therefore we can access it while logging.
```

7. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
function sayHello() {
  let username = 'Arya';
}
sayHello();
console.log(useranme); // John
// sayHello() when called will not return anything as there is not return statement used. console.log(username) will print the value John which is declared in the Global scope using let keyword in variable username.
```

8. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (var i = 0; i < 10; i++) {
  console.log(i, 'First'); 
//  0 "First"
//  1 "First"
//  2 "First"
//  3 "First"
//  4 "First"
//  5 "First"
//  6 "First"
//  7 "First"
//  8 "First"
//  9 "First"
}
console.log(i, 'Second'); 
// 10 "Second"

// Beacuse we have used the `var` keyword in the for block scope, so we can access `i` inside and outside the loop as well. Hence after printing 9 times it prints value of `i` as 10 outside the loop.
```

9. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (let i = 0; i < 10; i++) {
  console.log(i, 'First'); 
//  0 "First"
//  1 "First"
//  2 "First"
//  3 "First"
//  4 "First"
//  5 "First"
//  6 "First"
//  7 "First"
//  8 "First"
//  9 "First"
}
console.log(i, 'Second');
// ReferenceError: i is not defined

// Whereas in this scenario, since let is used and let is block scoped hence we cannot access it outside the loop block. So it throws error when we try to access outside the loop.
```
