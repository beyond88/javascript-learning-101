<h1 align="center">
JavaScript Learning 101
</h1>
  
 This repository is for my daily learning of JavaScript basic featues, codesnippet, new featues and so on. So I can track my learning progress and can recall of this materials If I forget.  

<h2 align="center">Callback function</h2>
A callback function is a function passed as an argument to another function. This technique allows a function to call another function. A callback function can run after another function has finished.

<h4>
Why do we need Callback Functions?
</h4>

<p>
JavaScript runs code sequentially in top-down order. However, there are some cases that code runs (or must run) after something else happens and also not sequentially. This is called asynchronous programming.

Callbacks make sure that a function is not going to run before a task is completed but will run right after the task has completed. It helps us develop asynchronous JavaScript code and keeps us safe from problems and errors.

In JavaScript, the way to create a callback function is to pass it as a parameter to another function, and then to call it back right after something has happened or some task is completed. Let’s see how…
</p>

<strong>Example:</strong><br>
```
const message = function() {  
    console.log("This message is shown after 3 seconds");
}
 
setTimeout(message, 3000);
```
<strong>Callback as an Anonymous Function</strong><br>
```
setTimeout(function() {  
    console.log("This message is shown after 3 seconds");
}, 3000);
```
<strong>Callback as an Arrow Function</strong><br>

```
setTimeout(() => { 
    console.log("This message is shown after 3 seconds");
}, 3000);
```

<strong>Events</strong><br>

```
<button id="callback-btn">Click here</button>
document.queryselector("#callback-btn")
    .addEventListener("click", function() {    
      console.log("User has clicked on the button!");
});
```


<h2 align="center">Higher-order function</h2>
<p>In Javascript, functions can be assigned to variables in the same way that strings or arrays can. They can be passed into other functions as parameters or returned from them as well.</p>
<p>A “higher-order function” is a function that accepts functions as parameters and/or returns a function.</p>

<p>On the other side, the functions that use only primitives or objects as arguments, and only return primitives or objects are named first-order functions.</p>

A. Assign functions to variables:
```
// Assign to variables
const hiFunction = function() { 
  return 'Hello!' 
};
hiFunction(); // => 'Hello!'
```
B. Use functions as arguments to other functions:
```
// Use as arguments
function iUseFunction(func) {
  return func();
}
iUseFunction(function () { return 42 }); // => 42
```
In the above examples, iUseFunction() is higher-order because it accepts a function as an argument. 

C. And even return functions from functions:
```
// Return function from function
function iReturnFunction() {
  return function() { return 42 };
}
const myFunc = iReturnFunction();
myFunc(); // => 42
```
<p><i>"The functions that use other functions as arguments or return functions are named higher-order functions."</i></p>
<p>In the previous examples, iUseFunction() is higher-order because it accepts a function as an argument. Also iReturnFunction() is a higher-order function because it returns another function.</p>

<p>In the previous examples, hiFunction() is a first-order function since it simply returns a number.

So, in JavaScript a function can be either first-order or higher-order.</p>

