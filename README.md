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

<h2 align="center">Event loop</h2>

<p>The event loop is an architectural design pattern that allows code to run asynchronously on the JavaScript engines and makes it possible for code to execute blocking instruction first and when available execute asynchronous function.</p>
<p>The event loop utilizes there major components, call stack, event queue and web apis. It manages function calls in a way that asynchronous events would go into the event queue and will be called only after the call stack is empty.</p>


<h2 align="center">Promise vs Observables</h2>

<p>JavaScript is a single-threaded, non-blocking, and asynchronous concurrent language. That means that JavaScript’s engine doesn’t sit and wait for statements to finish. Instead, it moves to the next statement.</p>
<p>Promises and Observables have a completely different approach to dealing with async code.</p>

<strong>One value vs. multiple values</strong>
<p>The biggest difference is that Promises won’t change their value once they have been fulfilled. They can only emit (reject, resolve) a single value. On the other hand, observables can emit multiple results. The subscriber will be receiving results until the observer is completed or unsubscribed from.</p>

<strong>Observable subscriptions are cancellable; promises aren’t</strong>
<p>Once you start a promise, you can’t cancel it. The callback passed to the Promise constructor will be responsible for resolving or rejecting the promise. The subscriber is passive; once fired, it can just react to the result.

Observables are less passive. Once a subscriber is created, it can opt out of the observer at any time. That makes them useful in scenarios where we are no longer interested in the response.</p>


<strong>Eager vs. lazy execution</strong>
<p>There is a difference in how Observables and Promises are executed. Promises are executed eagerly whilst Observables are executed lazily.</p>

<strong>Eagar:</strong> The Promise callback will execute right away at the constructor level.

<strong>Lazy:</strong> The Producer function will only trigger after there is a subscription created for that Observable. Otherwise, it will stay idle.

<strong>Runtime execution</strong>
The ES Promises, once resolved, will queue the callback in the microtask queue. That means they will be executed after the current macro task has been completed.

With Observables, you can fine-tune the runtime execution using schedulers. A scheduler controls when a subscription starts and when notifications are delivered.

<h2 align="center">Apply vs Bind vs Call</h2>
<p>
All three of the call, bind, and apply methods set the this argument to the function. The call and apply methods set this to a function and call the function. The bind method will only set this to a function. We will need to separately invoke the function.</p>
<p>call() and apply() are identical in functionality, the only difference is that call() accepts a list of arguments; whereas, apply() accepts a single array of arguments.
The bind method binds the this value to the function and returns a new function. However, we still need to separately invoke the returned function.
</p>

<h2 align="center">Promise.all() vs Promise.allSettled()</h2>
<p>
<strong>Promise.all()</strong> returns a promise which resolves, when all promises from an array are resolved and gets rejected if one or more promises get rejected.
<strong>Promise.allSettled()</strong> returns a promise which resolves when all the promises in the array are settled (rejected or resolved).
</p>
