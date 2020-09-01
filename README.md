# Modern JavaScript

Putting together a modest resource that should be available for anyone wanting to reference more modern JavaScript while working on projects.

The purpose here is to keep the information grouped based on the relevance. I'm not going into detail about the core legacy JavaScript, I'm going to be focusing mostly on the more modern aspects, hence the name of the repo, "Modern JavaScript."

## Table of Contents

1. [Variables](#Variables)
2. [Functions](#Functions)
3. [Strings](#Strings)
4. [Numbers](#Numbers)
5. [Arrays](#Arrays)
6. [Objects](#Objects)
7. [Conditional Statements](#Conditional-Statements)
8. [Control Flow](#Control-Flow)
9. [Classes (for OOP)](#Classes)
10. [Import & Export (CommonJS vs ES6 Modules)](#Import-and-Export)
11. [Async/Await](#Async-and-Await)
12. [More coming soon...](#More-Coming-Soon)

# Variables

## var

At this point, the `var` keyword is considered legacy and will eventually get phased out once a bit of time has passed. Once that happens, anyone using the `var` keyword in their application will need to update their application code or simply deal with the fact that their application won't operate correctly in more modern browsers that support the latest versions of JavaScript. It's a best practice now to use the appropriate keyword `let` or `const` in its place.

```
var legacyVariable = 'some string';
```

## let

You should have a good understanding of variable scoping within the global and function scopes, how lexical scope works, and what hoisting is and how it affects your code (also, how to take advantage of it so it works in your favor). Ensure you are working with camelCase as it is the standard casing for JavaScript (unless you or your company decide otherwise).

```
let myChangableVariable = 'some string';
```

A really common and good use-case example that many interviewers will ask about are relating to how to use `let` within a `for` loop. Previously, working with `for` loops, when you set the `var i = 0` of the `for` loop, that `i` was recognized at a hoisted level which could create issues at a global scope since you might have numerous `i` variables due to numerous `for` loops. This issue essentially no longer exists due to the fact that using `let` in place of `var` results in `let i = 0` limiting the scope to that specific use-case and if housed within a function, is only hoisted to the top of that function at worst. Generally, you'd only see that scope set to the loop. This is a good piece of info to keep in mind when interview time comes around.

## const

Just as it sounds, the `const` keyword is associated with constants. An important point here is that if you're going to be following some TypeScript standards while working with this keyword, you should also be completely capitalizing your variable name so that your code is more readable for other developers working with your code.

```
const PORT = 8081;
```

# Functions

## Functions as Variables

One pretty neat thing about functions in JavaScript is that they can be set to variables. This is due to them essentially being classified as objects in JavaScript since virtually everything is an object in JavaScript. This neat aspect of JavaScript has bred an entirely efficient usage of functions in JavaScript and given birth to some cool usage relating to them.

**Old Way (still used)**

```
function myFunction() { ... }
```

Make sure you know how to use functions without names, called _anonymous functions_, because you're going to be using them quite often when you're writing more modern JavaScript (they are also used quite regularly in legacy JavaScript as well for purposes like callbacks).

**Anonymous Function as Variable**

```
const myFunction = function() { ... };
```

Another modern way of writing functions is by using something called an _arrow function_ which is pretty much a regular function, just written with a slightly different syntax, `() => { ... }`. Using them just as they are, they serve as anonymous functions, but when used with variables, they then serve a purpose closer to that of the above _anonymous function as variable_. This is also one of the most common forms of defining functions now within modern JavaScript.

**Arrow Function as Variable**

```
const myFunction = () => { ... };
```

# Strings

# Numbers

# Arrays

# Objects

# Conditional Statements

# Control Flow

# Classes

# Import and Export

# Async and Await

# More Coming Soon
