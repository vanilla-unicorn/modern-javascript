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
~~var legacyVariable = 'some string';~~
```

## let

You should have a good understanding of variable scoping within the global and function scopes, how lexical scope works, and what hoisting is and how it affects your code (also, how to take advantage of it so it works in your favor). Ensure you are working with camelCase as it is the standard casing for JavaScript (unless you or your company decide otherwise).

```
let myChangableVariable = 'some string';
```

## const

Just as it sounds, the `const` keyword is associated with constants. An important point here is that if you're going to be following some TypeScript standards while working with this keyword, you should also be completely capitalizing your variable name so that your code is more readable for other developers working with your code.

```
const PORT = 8081;
```

# Functions

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
