## Closure Exercise

1. Write a function, `outer` that takes an input `string`. Inside the function `outer` define another function expression named `sayHello` which alerts the `input`. `sayHello` should be call immediately after it is defined.

```js
// Your code goes here
function outer(str){
  let sayHello = () => {
    alert(str)
  }
  sayHello();
}
outer("Hi")
```

2. Write a function `delay` that accepts two arguments, a callback and the wait for the time in milliseconds (1000 ms is 1 second). `delay` should return a function that, when invoked waits for the specified amount of time before executing the callback. (Use setTimeout)

```js
// Your code goes here
function delay(cb,time){
  return function (){
    setTimeout(cb,time);
  }
}
function hi(){
  console.log(`Hiiii`);
}
let sample = delay(hi,2000)
sample();

let lastNameLee = lastName('lee'); // logs nothing
lastNameLee('Brett'); //logs 'Brett Lee'
```

```js
function lastNameLee(ln) {
  return function(fn){
    console.log(`${fn} ${ln}`);
  }
}
let lastNameLee = lastName('Lee')
```

This function is useful in case you want to create name for multiple people with same last name.

```js
lastNameLee('Jane'); //logs 'Jane Lee'
lastNameLee('Lynne'); //logs 'Lynne Lee'
```

4. Create a `storyWriter` function that returns an object with two methods. One method, `addWords` adds a word to your story and returns the story while the other one, `erase`, resets the story back to an empty string. Here is an implementation:

```js
function storyWriter() {
  // Your code goes here
  let story = "";
  return {
    addWords: function (word){
      story = story + word;
      return story;
    },
    erase: function (){
      return story = "";
    },
  };
}

// Test
let farmLoveStory = storyWriter();
farmLoveStory.addWords('There was once a lonely cow.'); // 'There was once a lonely cow.'
farmLoveStory.addWords('It saw a friendly face.'); //'There was once a lonely cow. It saw a friendly face.'
farmLoveStory.erase(); //''

let storyOfMyLife = storyWriter();
storyOfMyLife.addWords('My code broke.'); // 'My code broke.'
storyOfMyLife.addWords('I ate some ice cream.'); //'My code broke. I ate some ice cream.'
storyOfMyLife.erase(); // ''
```

5. Create a function named `forEach` which accepts one parameter an array. Inside the function `forEach` there a variable named `index` which is initialized to `0`.

When `forEach` function is called it returns another function. When the returned function is called it returns the element from the array at specific index. Every time you call the returned function the value of index should increment.

```js
function forEach(arr) {
  // Your code goes here
  var index = 0;
  return function (){
    return arr[index++];
  }
}

let next = forEach([1, 2, 3, 4, 5]);
next(); // 1
next(); // 2
next(); // 3
next(); // 4
next(); // 5
```

6. Create a function named `addDesignation` which accepts a `title` and returns another function.

The returned function accepts a string `prefix` and returns `prefix` and `title` with a space.

```js
function addDesignation(title) {
  // your code goes here
  return function (str){
    return str+' '+title;
  }
}

let sales = addDesignation('Salesman');
sales('Main'); // Main Salesman

let manager = addDesignation('Manager');
manager('Regional'); // Regional Manager
manager('Head'); // Head Manager
```

7. Create a function named `changeSalary` which accepts `currentSalary` (number) and returns an object that contains three methods

- `raise` which will add `500` to the current salary and returns the updated salary
- `lower` will decrease the salary by 500 returns the updated salary
- `current` will return the current salary returns the updated salary

```js
function changeSalary(currentSalary=0) {
  // Your code goes here
  return {
    raise: function (){ // One way of writing function inside an Object
      return currentSalary+500;
    },
    lower(){ // Another way of writing function inside an Object
      return currentSalary-500;
    },
    current: function (){
      return currentSalary;
    },
  };
}

let sam = changeSalary(2000);
sam.raise(); // 2500

let arya = changeSalary(4000);
arya.lower(); // 3500
```

8. Create a function named `nameFactory` which accepts `firstName` and `lastName` and returns an object with multiple functions.

- `getFullName`: return the full name of the person with a space
- `setFirstName`: accepts a parameter first name using which updates the firstName and return the updated full name
- `setLastName`: accepts a parameter last name using which updates the firstName and return the updated full name

```js
// Your code goes here
function nameFactory(fname,lname){
  return {
    getFullName: function (){
      return fname.concat(" ",lname);
    },
    setFirstName: function (firstName){
      fname = firstName;
      return fname.concat(" ",lname);
    },
    setLastName: function (lastName){
      lname = lastName;
      return fname.concat(" ",lname);
    },
  };
}

let arya = nameFactory('Arya', 'Stark');
arya.getFullName(); // "Arya Stark"
arya.setFirstName('Jon'); // "Jon Stark"
arya.setLastName('Lannister'); // "Jon Lannister"
```

9. Create a function named `createTag` which accepts an HTML element name and returns another function.

The returned function accepts a string (children) and returns the children with the tag you passed.

```js
function createTag(tag) {
  // your code goes here
  return function (children){
    // This below is one way
    // return `<${elm}>${children}</${elm}>`

    // This below is another way
    let elm = document.createElement(tag);
    elm.innerText = children;
    return elm;
  }
}

let bold = createTag('b');
bold('Hello World!'); // <b>Hello World!</b>

let italic = createTag('i');
italic('Hello World!'); // <i>Hello World!</i>
```
