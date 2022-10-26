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



