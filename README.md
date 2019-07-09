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


