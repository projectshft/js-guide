# JavaScript Crash Course

## Introduction
The following is based on an in-person event, but has also been written in such a way that anyone could pick it up and code along! 

As a disclaimer, this is only a brief introduction and overview of JavaScript. Learning JavaScript confidently (as any programming langauge) is only possible through many hours of dedicated work. However, this should be a great starting point!

## Objectives
- History and Purpose
- The Environment
- Declaring Variables and Doing Math
- Control Flow with Conditionals
- The 7 JavaScript Data Types
- Creating Functions
- Creating Arrays
- Doing Loops
- Creating Objects
- Putting it All Together!
- Next Steps

## History and Purpose

## The Environment
JavaScript can be executed in two places. Either in browser (the most common way) or on your machine using Node.js. Tonight we will use Node.js, but instead of downloading it to our local machines, we'll use [https://repl.it](https://repl.it).

So go ahead and open [https://repl.it](https://repl.it) in a new browser tab, and sign up for an account.

Next, find the blue button at the top that says "+ new repl" and click it:

![img](https://www.projectshift.io/wp-content/uploads/2019/07/Screen-Shot-2019-07-08-at-9.22.39-PM.png)

In the language drop-down, type in JavaScript, skip the rest and click "Create Repl":

![img](https://www.projectshift.io/wp-content/uploads/2019/07/Screen-Shot-2019-07-08-at-9.23.46-PM.png)

Now you will see a screen that looks like this:

![img](https://www.projectshift.io/wp-content/uploads/2019/07/Screen-Shot-2019-07-08-at-9.25.16-PM.png)

On the left (inside of `index.js`), we'll write our code and when we press "run", we'll see any output logged in the black. 

Let's give it a shot. Erase whatever is inside of `index.js` and add the following:

```js
5 * 5;
```

Then click "run". You should see 25 logged to the console! Awesome. You've written your first line of JavaScript! It can only get better from here.

## Declaring Variables and Doing Math
Coding is all about being lazy - instead of doing something ourselves, we want to write code to do it for us. 

For example, I hated math in school and was terrible at it. So I would have liked to be able to code my math problems. Let's imagine we wanted to find the radius of a circle (from the middle to the edge, remember?):

![img](https://www.projectshift.io/wp-content/uploads/2019/07/Screen-Shot-2019-07-08-at-9.33.28-PM.png)

The formula for this is: `circumference / 2 * pi`

But I cannot for the life of myself remember what pie is (I mean, I really can, but let's imagine I can't). For that, we'll set a variable. Go ahead and make `index.js` look like this:

```js
var pi = 3.14;
```

What we just did is delcared a variable. `var` is short for variable. Next to `var` we create a name for our variable. We could use pretty much anything we want, but it's always a good idea to use a name that makes sense.

Then using the `=` symbol, we can _assign_ the variable to a value - in this case, a number (3.14).

Finally, we end this statement with the semicolon `;`. It's not really necessary to have this since these days most environements will add semicolons in in the background if we forget, but it's good practice to use them.

Now let's make `index.js` look like this and press "run":

```js
var pi = 3.14;

console.log(pi);
```

Awesome! The value of `pi` should have logged to the console. `console.log()` enables us to log variables to the terminal so we can see their value.

We can literally assign anything to variables in JavaScript, as we'll see in a bit. Okay let's change our code to look like this and click 'run':

```js
var pi = 3.14;
var circumference = 40;

var radius = circumference / 2 * pi;

console.log(radius);
```

Now, anytime you wanted to figure out the radius of a new circle, all you would have to do it change the `circumference` variable!

### Exercise
Can you write some code now to find the diameter of the circle? The forumla is `2 x radius`:

<details>
  <summary>Peek a possible answer</summary>

  ```js
  var pi = 3.14;
  var circumference = 40;

  var radius = circumference / 2 * pi;

  var diameter = radius * 2;

  console.log(diameter);
  ```
</details>

## Control Flow with Conditionals
Let's make our code a bit smarter. When coding, it's helpful to write code that will run depending on a scenario or condition. 

For example, if someone is trying to log in to an app but their password is wrong, your app should yell at them. But it's right, your app should great them. In this case, the condition we're testing for was whether or not the password was correct.

Let's check out some code. Make `index.js` look like this:

```js
var password = "abracadabra";

var userPassword = "hello";

if (userPassword === password) {
  console.log('welcome, friend!');
} else {
  console.log('get out of here!');
}
```

Since we do not yet have any real mechanism by which someone could enter a dynamic password, we have to just code something in here for now. Imagine that `password` is the real password and `userPassword` is whatever the user just entered.

Below it, we used a "conditional" statement to either console log `'welcome, friend!'` or `'get out of here!'`.

The `else` will run as long as the first statement is false.

The `===` checks to see if `userPassword` and `password` are the same.

There is a ton more we can do with conditionals, but this will have to suffice for now as we have a ton of more ground to cover. Don't worry, we'll put it all together in the end.

## The 7 JavaScript Data Types
When we say "data type" we are reffering to the kind of data that a given variable expresses. In JavaScript, we have 7 data-types. 6 of them are primitives, and 1 is complex. Here's what we mean.

### Primitive Data Types
This is confusing, but primitive data types mean that these "types" do not have methods. A method is essentially a verb. 

As an analogy, we could think of a piece of paper and a car. A piece of paper is just a piece of paper. It really can't do anything. We might be able to describe it as being white and flat and big or small. But it has no action to take.

Whereas a car can drive! It can _do_ stuff!

In JavaScript, here are our 6 primitive:

_Definitions from [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures):_

**Boolean**

  Boolean represents a logical entity and can have two values: `true`, and `false`.

**Null**

  Meaning, nothing. The Null type has exactly one value: `null`.

**Undefined**

  A variable that has not been assigned a value has the value `undefined`.

**Number**

  According to the ECMAScript standard, there is only one number type... There is no specific type for integers. In addition to being able to represent floating-point numbers [decimals], the number type has three symbolic values: `+Infinity`, `-Infinity`, and `NaN` (not-a-number).

**String**

  JavaScript's String type is used to represent textual data. It is a set of "elements" of 16-bit unsigned integer values. Each element in the String occupies a position in the String. The first element is at index 0, the next at index 1, and so on. The length of a String is the number of elements in it.

**Symbol** (new in ECMAScript 6)

  Symbols are new to JavaScript in ECMAScript Edition 6. A Symbol is a unique and immutable primitive value and may be used as the key of an Object property. In some programming languages, Symbols are called atoms.

### Complex Data Type
In JavaScript, all other data-types are technically objects (arrays and functions too). An object is essentially just a key-value pair of data:

```JavaScript
var car = {
  color: 'red',
  wheels: 4
}
```

### Built in Objects

The array and the function are not the only "sub-types" of the humble object. The following is a list of a few of JavaScript's built-in objects with their respective MDN links (pro tip: these links won't automatically open in a new tab, but if you hold down `command` or `ctrl` (for you windows people) and click, it will open the link in a new tab):

- [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
- [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
- [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/function)
- [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/array)
- [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/date)
- [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/regexp)
- [`Error`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/error)

## The Big 3 Object Sub-types
Next, we'll dive into what we normal think of as separate data types - functions, arrays and objects. As we've seen, they're all actually objects, but they're unique representations of objects, so it's good to have distinct mental references for each.

## Functions
With functions, we can wrap a section of code into a "container" and run they code over and over again, whenever we want. For example, make `index.js` look like this:

```js
var greet = function () {
  console.log('hello!');
};
```

If you run this code, it won't do anything - the `console.log('hello')` won't happen. That's because have no _invoked_ the function. We'll invoke it like this:

```js
var greet = function () {
  console.log('hello!');
};

greet();
```

We just added the `()` next to the variable which points to the function. If you run this, what happens? It console logs `'hello!'`.

Now what if you make it look like this?

```js
var greet = function () {
  console.log('hello!');
};

greet();
greet();
```

It console logs `'hello!'` two times! What about this?

```js
var greet = function () {
  console.log('hello!');
};

greet();
greet();
greet();
```

It console logs `'hello!'` three times! What about this? Just kidding, you get the point. We can execute the code inside the function as many times as we want, which will prove extremely useful in the future.

### Function Parameters and Arguments
Saying `'hello'` over and over again isn't all that useful. Let's change this function so that we can greet individuals, depending on their name.

For this, we'll change the code of our function to have a parameter. Make `index.js` look like this:

```js
var greet = function (name) {
  console.log('hello ' + name + '!');
};

greet('Bob');
```

If your run the code above, it will log, `'Hello Bob!'`.

We would say that `name` is "parameter" in the function, `greet`. It's sort of like a placeholder.

Then, at the time in which we invoke the function `greet`, we can provide that function with an "argument" - in this case, `'Bob'`.

The jazz we did inside the function (`'hello ' + name + '!'`) is called string interpolation. As we saw earlier, a string is essentially just text and we create it with quotes.

We can _interpolate_ variables and text together to create a new string, as we did in the code above.

Now change `index.js` to look like this:

```js
var greet = function (name) {
  console.log('hello ' + name + '!');
};

greet('Bob');
greet('Sue');
greet('Larry');
```

Awesome! These are the basics of functions.

## Arrays
In programming, it's helpful to be able to group together items in lists. With JavaScript, these lists are called arrays. We can use arrays to hold anything in JavaScript.

Let's look at an example using my family:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];
```

Here, we have an array of strings. Each item in the array is ordered and indexed. In other words, `'Sarah'` is first in the array, and `'Maayan'` is last.

This is in order of oldest to youngest ;)

Each item in the array has a position (index), and we start indexing these items at 0. So `'Sarah'` is in position `0`, `'Aaron'` is in `1`, `'Isaiah'` is in `2`, etc.

We would also say that the length of this array is 5, because there are 5 items in it.

If I wanted to access the value of a position in the array, I could use this syntax:

```js
family[2]
```

Of course, this would return `'Isaiah'`.

Now let's make `index.js` look like this:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];
```

Write some code below that to console log `'Jeremiah'`.

<details>
  <summary>The Answer</summary>

  ```js
  var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

  console.log(family[4]);
  ```
</details>

### Arrays Can Contain Anything
We can put anything into an array and can even mix what we put inside of them. For example:

```js
var randomThings = ['hello', 5, function () { return 'hello' }, null, undefined, { color: 'red' }];
```

We can also add things to arrays dynamically. For example:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

family.push('Baby # 4');

console.log(family); // ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan', 'Baby #4'];
```

Or we can remove things from an array too using `splice`. Splice is a function that takes two arguments. The first argument is the `index` of the array that we want to start removing things from, and the second argument is the number of items we want to remove.

For example:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

family.splice(2, 3);

console.log(family); // ['Sarah', 'Aaron']
```

The first argument we provided was `2` so we were referring to `family[2]`, which is `Isaiah`. Therefore, with `splice`, we said "let's remove things from the array, starting `'Isaiah'`".

The second argument we provided was `3`, which again, was the number of items we wanted to remove. Therefore, we were saying ,"let's remove things from the array, starting `'Isaiah'` and removing 3 items".

What would the `family` array look like after the following code?

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

family.splice(1, 2);
```

<details>
  <summary>The Answer</summary>

  ```js
  [ 'Aaron', 'Isaiah' ];
  ```
</details>

## Loops
Now let's imagine that we wanted to greet each person in `family`. We would not want to do this:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

console.log('Hello ' + family[0] + '!');
console.log('Hello ' + family[1] + '!');
console.log('Hello ' + family[2] + '!');
console.log('Hello ' + family[3] + '!');
console.log('Hello ' + family[4] + '!');
```

We could make it a little better by using a function:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

var greet = function (name) {
  console.log('Hello ' + name + '!');
};

greet(family[0]);
greet(family[1]);
greet(family[2]);
greet(family[3]);
greet(family[4]);
```

Essentially, we to do this...

```js
greet(family[0]);
```

...over and over again, but replace the `0` with the number of the index in the array each time.

For this, we can use a "for loop". Here is how it will look. Make `index.js` look like this and run it:

```js
for (var i = 0; i < 10; i++) {
  console.log(i);
}
```

As you will see, this will run the console log 10 times, and `i` will change each time. Let's break it down.

Using `for`, we're essentially saying, `for` every loop, do the following.

Inside the `for` parentheses, we're doing three things.

1. We are declaring a variable, `i`. It's convention to call this `i` (short for index) but we can call it whatever we want. In this case we wrote `var i = 0;` to start that `i` will start at `0`.

2. With `i < 10`, we're saying that we want to run the code inside of the brackets (`{}`) _until_ this statement is no longer true. In other words, if `i` gets bigger than 9, stop the loop.

3. Lastly, with `i++`, we're incrementing the `i` variable by 1, each time the loop runs. This is why it start as `0`, then is `1`, then `2`, etc. Writing `i++` is the same as `i +=1` which is the same as `i = i + i`.

Now, let's use `i` for our `family` array. Make `index.js` look like this and run it:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

for (var i = 0; i < 10; i++) {
  console.log(family[i]);
}
```

Notice that we used `i` inside of our bracket notation to console log everyone in the `family` array. For each iteration, `i` pointed to a new index.

However, you will notice that we have a problem as the following was logged to the console:

```js
Sarah
Aaron
Isaiah
Jeremiah
Maayan
undefined
undefined
undefined
undefined
undefined
```

That's because `family[5]`, `family[6]`, `family[7]`, `family[8]` and `family[9]` do no exist.

We can change our `for` loop to only loop through the items in the array. We want the loop to stop after `i` becomes bigger than the array is long. We can do this by editing our code to look like this:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

for (var i = 0; i < family.length; i++) {
  console.log(family[i]);
}
```

Notice that we replaced `i < 10` with `i < family.length`. The `length` property of an array give us the length of the array. Make `index.js` look like this and run it:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

for (var i = 0; i < family.length; i++) {
  console.log(family[i]);
}
```

Woo hoo! It works.

Now if we wanted to use our greet function:

```js
var family = ['Sarah', 'Aaron', 'Isaiah', 'Jeremiah', 'Maayan'];

var greet = function (name) {
  console.log('Hello ' + name + '!');
};

for (var i = 0; i < family.length; i++) {
  greet(family[i]);
};
```

We'll get:

```js
Hello Sarah!
Hello Aaron!
Hello Isaiah!
Hello Jeremiah!
Hello Maayan!
```

Woo hoo!

## Creating Objects
Lastly, we get to the `object` in JavaScript. An object is essentially just a key-value pair. Let's look at an example:

```js
var car = {
  color: 'red',
  wheels: 4
};
```

An object is different than array in this way:
- In an array, the order matters. With an object, the order doesn't matter. `color` could come before or after `wheels`.
- In an array, we index items by a number (`0`, `1`, `2`, etc). With an object, they're indexed by named properties (`color`, `wheels`).

To access the value of an object property, we use dot notation like this:

```js
car.color // 'red'
```

Or bracket notation:

```js
car['color'] // 'red'
```

Note that with bracket notation we have to use quotes around the name of the property.

Just like with arrays, the values of any property in an object can be anything, even functions!

```js
var car = {
  color: 'red',
  wheels: 4,
  drive: function () {
    console.log('vroom!');
  }
};
```

Technically, `drive` is a "method". A method is a function that belongs to an object. If we wanted to invoke it (and make the car "drive"), we could do this:

```js
var car = {
  color: 'red',
  wheels: 4,
  drive: function () {
    console.log('vroom!');
  }
};

car.drive(); // 'vroom!'
```

## Putting it All Together
Let's walk through solving some basic coding problems with everything we've learned!

## Problem 1 - Adding it All Up
Using some JavaScript, let's write a a function called `addAllItems` that takes an array as an argument and returns the sum of all the items in the array.

For example: if the input string is `[2, 3, 3]` then your program should return `8`.

Here is how we could do this, step by step:

1. First, let's write the function:

```js
var addAllItems = function (array) {

};
```

2. Next, let's test it by invoking it and passing in an array of numbers:

```js
var numbers = [2, 3, 3];

var addAllItems = function (array) {

};

addAllItems(numbers);
```

Now we want to write some code that actually does the adding. We'll do this inside the body of `addAllItems`. Here's the strategy:

We'll use a `for` loop to loop through all the numbers in the array and add them up. Then, we'll return that value. It will look like this:


```js
var numbers = [2, 3, 3];

var addAllItems = function (array) {
  var sum = 0;

  for (var i = 0; i < array.length; i++) {
    sum = sum + array[i];
  }

  return sum;
};

addAllItems(numbers);
```

Notice that we used something new called `return`. Real simply, `return` does two things:

1. It returns a value from the function
2. It immediately exists to function so that nothing that comes after it is run.

## Problem 2 - Adding it All Up
Next let's tackle this. Using some JavaScript, write a function called `numberOfVowels` that takes an array of letters as an argument. The function should return how many letters in the array are vowels.

For example: if the input array is `[i, y, a, e, t]` then your program should return the number `3`. Let's solve it now:

First, we'll write the function and create a test array, and invoke it with that test array:

```js
var letters = ['a', 'b', 'c', 'e', 'i'];

function numberOfVowels(array) {

  return number;      
};

numberOfVowels(letters);
```

Next, let's think of a strategy. We can use [`includes`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) to figure out if an array has a certain item in it. Let's do that to see if `letters` has a vowel.

To do this, we'll create an array of vowels inside of `numberOfVowels` that we can check against:

```js
var letters = ['a', 'b', 'c', 'e', 'i'];

function numberOfVowels(array) {
  var number = 0;
  var vowels = ['a', 'e', 'i', 'o', 'u'];

  return number;      
};

numberOfVowels(letters);
```

We've also initialized `number` to `0` so that we can increment it in a moment.

Next, we want to loop through all of the letters that were passed in through the `array` as an argument:

```js
var letters = ['a', 'b', 'c', 'e', 'i'];

function numberOfVowels(array) {
  var number = 0;
  var vowels = ['a', 'e', 'i', 'o', 'u'];

  for (var i = 0; i < vowels.length; i++) {
    if (array.includes(vowels[i])) {
      number++;
    }
  };
  
  return number;      
};

numberOfVowels(letters);
```

It works!

However, what if letters looked like this and had a duplicate?


```js
var letters = ['a', 'b', 'c', 'e', 'i'];
```

Our current solution wouldn't check for that. Why not?

Let's change it to so that it would check for that:

```js
var letters = ['a', 'b', 'c', 'e', 'i', 'e'];

function numberOfVowels(array) {
  var number = 0;
  var vowels = ['a', 'e', 'i', 'o', 'u'];

  for (var i = 0; i < vowels.length; i++) {
    for (var j = 0; j < array.length; j++) {
      if (vowels[i] === array[j]) {
        number++;
      }
    }
  };
  
  return number;      
};

numberOfVowels(letters);
```

So what is this code all about?:

```js
for (var i = 0; i < vowels.length; i++) {
  for (var j = 0; j < array.length; j++) {
    if (vowels[i] === array[j]) {
      number++;
    }
  }
};
```

We're essentially checking every item in the `vowels` array against every item in the `letters` (which we called `array` inside the function) array. So step by step, it's saying this:

1. Is `a` (from `vowels`) the same thing as `a` from letters? Yep! Increment `number`!
2. Is `a` (from `vowels`) the same thing as `b` from letters? Nope. Don't do anything.
3. Is `a` (from `vowels`) the same thing as `c` from letters? Nope. Don't do anything.
4. Is `a` (from `vowels`) the same thing as `e` from letters? Nope. Don't do anything.
5. Is `a` (from `vowels`) the same thing as `i` from letters? Nope. Don't do anything.
6. Is `a` (from `vowels`) the same thing as `e` from letters? Nope. Don't do anything.
7. Is `e` (from `vowels`) the same thing as `a` from letters? Nope. Don't do anything.
8. Is `e` (from `vowels`) the same thing as `b` from letters? Nope. Don't do anything.
9. Is `e` (from `vowels`) the same thing as `c` from letters? Nope. Don't do anything.
10. Is `e` (from `vowels`) the same thing as `e` from letters? Yep! Increment `number`!
11. Is `e` (from `vowels`) the same thing as `i` from letters? Nope. Don't do anything.
12. Is `e` (from `vowels`) the same thing as `e` from letters? Yep! Increment `number`!

And so on...

## More Exercises:

- Multiply: [https://www.codewars.com/kata/multiply/train/javascript](https://www.codewars.com/kata/multiply/train/javascript)
- Return Negative: [https://www.codewars.com/kata/return-negative/train/](https://www.codewars.com/kata/return-negative/train/javascript)
- Is Greater Than: [https://codepen.io/hrprep/pen/wdBKee?editors=1010](https://codepen.io/hrprep/pen/wdBKee?editors=1010)
- Is Even: [https://codepen.io/hrprep/pen/wdBMQO](https://codepen.io/hrprep/pen/wdBMQO)
- Is Old Enough to Drink: [https://codepen.io/hrprep/pen/aWoPaL?q=isoldenoughtodrink&limit=mine](https://codepen.io/hrprep/pen/aWoPaL?q=isoldenoughtodrink&limit=mine)
- Check Age: [https://codepen.io/hrprep/pen/bWGvgo](https://codepen.io/hrprep/pen/bWGvgo)
- Get Length of Word: [https://codepen.io/hrprep/pen/OmJvxg](https://codepen.io/hrprep/pen/OmJvxg)
- Get Length of Two Words: [https://codepen.io/hrprep/pen/gWOeoW](https://codepen.io/hrprep/pen/gWOeoW)
- Remove First and Last Character: [https://www.codewars.com/kata/remove-firstand-last-character/train/javascript](https://codepen.io/hrprep/pen/gWOeoW)
- Return Negative: [https://www.codewars.com/kata/return-negative/train/javascript](https://www.codewars.com/kata/return-negative/train/javascript)
- Is Greater Than: [https://codepen.io/hrprep/pen/wdBKee?editors=1010](https://codepen.io/hrprep/pen/wdBKee?editors=1010)
- Is Even: [https://codepen.io/hrprep/pen/wdBMQO](https://codepen.io/hrprep/pen/wdBMQO)
- Is Old Enough to Drink: [https://codepen.io/hrprep/pen/aWoPaL?q=isoldenoughtodrink&limit=mine](https://codepen.io/hrprep/pen/aWoPaL?q=isoldenoughtodrink&limit=mine)
- Check Age: [https://codepen.io/hrprep/pen/bWGvgo](https://codepen.io/hrprep/pen/bWGvgo)
- Get Length of Word: [https://codepen.io/hrprep/pen/OmJvxg](https://codepen.io/hrprep/pen/OmJvxg)
- Get Length of Two Words: [https://codepen.io/hrprep/pen/gWOeoW](https://codepen.io/hrprep/pen/gWOeoW)
- Remove First and Last Character: [https://www.codewars.com/kata/remove-firstand-last-character/train/javascript](https://www.codewars.com/kata/remove-firstand-last-character/train/javascript)


