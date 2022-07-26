---
title: "JS Modules"
---

## Modules
A module is a piece of program that specifies which other pieces it relies on and which functionality it provides for other modules to use, i.e. is visible to other modules (its _interface_). The interface are the connection points between different modules; there's some _internal_ stuff going on inside the module, and some _public_ stuff that is shared with other modules. 

See also: [[JS Packages]], [[JS npm]]

Why modules:
- To not have to code everything from scratch if you want to use something repeatedly. 
- To manage complexity.
- To have a "LEGO" system of code pieces that can interact through well-defined connectors. 

The relations between modules are called _dependencies_ (i.e. a module _depends_ on another module). Dependencies are the other modules that a module makes use of.

_Think about how to structure your code and what should maybe go into modules after you have done most of the coding, not during. _

If we want to make dependency relations part of the code, we'll have to take control of **loading dependencies**. Doing that requires being able to execute strings as code. 
For that, we use the `Function` constructor. It takes two arguments: a string containing a comma-separated list of argument names, and a string containing the function body. 

```
let plusOne = Function("n", "return n+1;");
console.log(plusOne(4));
// 5
```


**`require`**
When you call this function with the module name of a dependency, the module is loaded and returns its interface. Modules automatically get their own local scope. All they have to do is call `require` to access their dependencies and put their interface in the object boud to `exports`.

Usually modules have their dependencies on the top, e.g.
```
const ordinal = require("ordinal");
```
Calling `require` involves reading the module's code, wrapping it in a function and calling it. 
It's usually written as a filepath, e.g. `"./format-date"` (i.e. the file `format-date.js` in the same directory). 

**`exports`**
The module adds its interface function to `exports` so that modules that depend on it get access to it, e.g. 
```
exports.formatDate = function(date, format) {......};
``` 

**`module`**

## ECMAscript modules
Since 2015, there's a new standard, that's however slow to be widely adopted. It uses **`import`** instead of `require` to acess a dependency, and **`export`** instead of `exports` to export things. 
```
import ordinal from "ordinal";

export funciton formatDate(date, format) {......}
```

It's possible to rename imported bindings using the word **`as`**:
`import {days as dayNames} from "date-names"; `




When writing your own modules, find out what data structures people are usually using and follow their example, if possible. 

