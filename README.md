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


