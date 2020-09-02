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
7. [Control Flow](#Control-Flow)
8. [Classes (for OOP)](#Classes)
9. [Import & Export (CommonJS vs ES6 Modules)](#Import-and-Export)
10. [Async/Await](#Async-and-Await)
11. [More coming soon...](#More-Coming-Soon)

---

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

One thing to keep in mind when using these modern solutions is that you can still use the `()` just as before where you store your arguments that pass to the function for usage within the function block. So `function myFunction(x, y)...` are served the same way in `const myFunction = (x, y) => ...`. One key difference here is that when using arrow functions, there is no need to use `()` when only one argument is being used, so `const myFunction = x => ...` works just fine.

## Returning from Functions

Typically, if you're used to working with legacy functions in JavaScript, you may be used to simply using the `return` keyword with something that is returned. But with modern JavaScript, there are implicit and explicit returns. That means that if you're returning something from a small function, you can optimize the readability of the code by consolidating the function to a single line by omitting the `return` keyword entirely. Keep in mind though that explicit returns are still used regularly, so get some practice in with using implicit returns.

**Explicit Return**

```
const myFunction = () => {
    return true;
}
```

**Implicit Return**

```
const myFunction = () => true;
```

# Strings

## Template Strings

Strings have evolved a bit with the newer versions of JavaScript. They've since introduced _template strings_ which give you a bit more control over how you use strings. Gone are the days where you are adding strings to concatenate them. And you no longer need to handle breaking a string up in order to provide a string as a block of text using spaces and `<br/>` tags (though `<br/>` tags are still useful on a regular basis for other things).

**Regular String**

```
const myString = 'Some String';
const myDoubleQuotedString = "Some String";
```

**Template String**

```
const myString = `Some String`;
```

Ensure that you are using backticks (\`) rather than single quotes. It's pretty often that you might forget that you're working with a template string and see an error and scratch your head for a minute or two before remembering that it's a template string that uses backticks. You'll get used to it though.

## Interpolation

Another key feature of template strings is the ability to interpolate the string with some data. Remember above when I mentioned not needing to concatenate stringe with the `+` operator anymore. Yeah, this is what I mean. Instead of using the `+` operator, all you need to do is add a formatter to the template string that follows the `${...}` syntax. Simply adding this to the inside of the string where you want to add the data you are interpolating will handle the issue with ease and in a much easier to read syntax.

**Interpolated Template String**

```
const hello = 'Hello';
const world = 'World!';
const myInterpolatedString = `${hello} ${world}`; // gives you 'Hello World!'
```

## Multi-line Strings

You can also break template strings across different lines as well. Simply use three backticks (```) to open and close a text block.

# Numbers

There isn't much here to remember other than the two methods, `parseInt()` (also `parseFloat()` if you're dealing with floating points - seems to be used for doubles as well so use what is best for you) and `toString()`. I've heard that `toString()` will eventually be phased out, but I haven't seen anything definitive about that in writing so it could just be conjecture, so take it as that for now.

**Parsing an Integer**

```

const numberAsString = '99';
const actualNumber = parseInt(numberAsString); // gives you 99 - no quotes so it isn't a string

```

**Number to String**

```

const number = 99;
const numberAsString = number.toString(); // gives you "99" - usually expressed with double quotes but either way, still a string

```

# Arrays

Arrays are a data type that you're likely to use pretty often so get comfortable with the different array methods, new and old. Being able to filter an array by specific results is helpful using the `.filter()` callback. It'll return a new array with the results so it's indespensible when working with _pure functions - functions that don't mutate state or the input provided_.

**Array Filtering**

```
const grades = [ 90, 58, 93, 0, 80 ];
// Get passing grades that are above a 79
const passingGrades = grades.filter(grade => grade > 79); // gives you [ 90, 93, 80 ]
```

Checking an array for any occurrence of a specific value is also helpful. This can be done with strings in a similar way since strings are simply an array of characters (usually checking for a specific substring) using the `.includes(some_value)` method.

**Checking Array for Value**

```
const statesVisited = ["Florida", "New York", "Virginia", "California" ];
const hasVisitedTexas = statesVisited.includes("Texas"); // gives boolean value of false
```

Another helpful pair of methods are the `.join('some_string')` and `.split('some_string')` methods that allow you to create a string from an array of values or split a string into an array with some kind of separator.

**Join Array Values**

```
const statesVisited = ["Florida", "New York", "Virginia", "California" ];
const statesVisitedAsString = statesVisited.join(','); // gives you "Florida, New York, Virginia, California"
const placesVisitedInUsa = `I've visited ${statesVisitedAsString}.`; // interpolating value into string works nicely
```

**Splitting String into Array**

```
const code = "G3ZS3-3FDW3-FEAG3-G94E8";
const codeBrokenUp = code.split('-'); // gives you ["G3ZS3", "3FDW3", "FEAG3", "G94E8" ]
```

The last method here I'll cover, though there are more for arrays, is going to be something you use a **LOT** if you're working with a framework, like React.js. Typically when iterating through an array of values that need to be rendered within their own components, for example. You do this with the `.map()` method.

**Mapping Array Values**

```
const itemArray = ["cheese", "bread", "mayo", "ham" ];
itemArray.map((item, index) => <SomeComponent key={index} value={item} />) // React.js example rendering component from values
```

# Objects

Objects are at the core of the JavaScript language and it is helpful to know a couple of methods when working with them since you'll often need to iterate through keys and values of an object at some points. Previously, this was a pain because you needed to loop and set an array where the values were equal to the keys or values of the object. That's since been simplified using both the `Object.keys()` and `Object.values()` methods.

**Get Object Keys**

```
const person = { name: "Jimbo", age: 43, is_famous: false };
const personKeys = Object.keys(person); // gives you [ "name", "age", "is_famous" ]
```

**Get Object Values**

```
const person = { name: "Jimbo", age: 43, is_famous: false };
const personValues = Object.values(person); // gives you [ "Jimbo", 43, false ]
```

# Control Flow

Remember that readability is important when working with other developers. And refactoring is a key aspect of the work you're doing so you'll want to prevent yourself from writing insanely long `if else` statements. One way of avoiding this is to break those statements up by their respective logic, where the only time you're using a block (`{...}`) is when it's absolutely unavoidable. That'll help you with your ability to generate _one-liners_ that can solve issues in a more efficient manner. This helps you to reach for that senior level developer style of development as well.

**Normal Conditional**

```
const isOnVacation = true;
if (isOnVacation) {
    return true;
} else {
    return false;
}
```

**More Optimal Conditional**

```
const isOnVacation = true;
if (!isOnVacation) return false;
return true;
```

Another key aspect of this that you should be keeping in mind (though slightly off topic here) is that, if you're a self taught engineer like myself, you should already be working on learning computer science concepts and theory that will help make you a better overall engineer/developer. One of these concepts of that of _Big-O_. I won't dive too deep into it, but essentially, Big-O is related to the efficiency of a function or script and how well it accomplishes a given task, more specifically in relation to _complexity_. Complexity comes in two flavors, space complexity and time complexity. Time complexity is generally what most people refer to when discussing complexity. Time complexity deals with how convoluted the given function or script is, how many different operations it is attempting to perform, and whether or not there are nested conditional statements as this could potentially increase the complexity exponentially (O(N) => O(N^2) for example). Space complexity is a bit more concerned with the data types and whether or not you're using the proper data type for the specific case. I say this because when discussing space complexity, you'll likely need to pay attention to the size of the data being input, and if you're familiar with data types at a binary level, you'll know that strings will take up more space than say, a number in their binary representations respectively. Learning about this will greatly aid you with paying attention to the most optimal ways of writing your code to produce more efficiency, especially when dealing with more computational heavy scripts, and this skill translates well to other languages as well.

# Classes

# Import and Export

# Async and Await

# More Coming Soon

```

```
