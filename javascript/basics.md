### **👋 Javascript.**


Javascript DOM (Document Object Model) is an API to interact with HTML and XML documents. 

Excellent Tutorial: https://www.javascripttutorial.net/


**Datatypes**

Javascript has 6 primitive datatypes:
1. null
2. undefined
3. boolean
4. number
5. string
6. symbol (from ES6)
7. Objects


Loosely coupled: so variables can be anything. 

---
**🤚Javascript Arrays**

Javascript has Arrays, which can be dynamically sized so no memory has to be reserved for them. 

``let scores = new Array(9,10,8,7,6);``


**map** in javascripts are there to make `for loops` cleaner. You can transform arrays elements in a cleaner way. 

```
let circles = [
    10, 30, 50
];

let areas = []; // to store areas of circles
let area = 0;
for (let i = 0; i < circles.length; i++) {
    area = Math.floor(Math.PI * circles[i] * circles[i]);
    areas.push(area);
}
console.log(areas);
```

becomes 
```
function circleArea(radius) {
    return Math.floor(Math.PI * radius * radius);
}
let areas = circles.map(circleArea);
console.log(areas);
```

which outputs: `[314, 2827, 7853]`

To make it further shorter, you can pass map as an **Anonymous function**

```
let areas = circles.map(function(radius){
    return Math.floor(Math.PI * radius * radius);
});
console.log(areas);

```

In ES6, you can pass it with `arrow function` 
```
let areas = circles.map(radius => Math.floor(Math.PI * radius * radius));
console.log(areas);
```
---
**🤚Javascript Functions**

Functions in JavaScript are first-class objects, which means you can store functions in variables, pass them to other functions as arguments, and return them from other functions as values.


**CALLBACK FUNCTIONS**

The map() method calls a `callback function` on every element of an array and returns a new array that contains the results.


```
function callback(currentElement,index,array){
  // ... 
}
```

The callback() function takes three arguments:

1. The currentElement is the current element of the array that is being processed.
2. The index is the index of the currentElement.
3. The array is the array object being traversed.

The currentElement is required while the index and array arguments are optional.

It’s important to note that the map() method does not change the original array, it creates a new array of all elements that have been transformed by the callback function.


**Synchronous callback functions**

If your code executes sequentially from top to bottom, it is synchronous.


**Asynchronous callback functions**
Asynchronicity means that if JavaScript has to wait for an operation to complete, it will execute the rest of the code while waiting.

Note that JavaScript is a single-threaded programming language. It carries asynchronous operations via the callback queue and event loop.


**Explain Callback in real life example**

*Imagine this scenario: you are expecting a package in a couple of days. The package is a gift for your neighbor. Therefore, once you get the package, you want it brought over to the neighbors. You are out of town, and so you leave instructions for your spouse.*

*You could tell them to get the package and bring it to the neighbors. If your spouse was as stupid as a computer, they would sit at the door and wait for the package until it came (NOT DOING ANYTHING ELSE) and then once it came they would bring it over to the neighbors. But there's a better way. Tell your spouse that ONCE they receive the package, they should bring it over the neighbors. Then, they can go about life normally UNTIL they receive the package.*

*In our example, the receiving of the package is the "event" and the bringing it to the neighbors is the "callback". Your spouse "runs" your instructions to bring the package over only when the package arrives. Much better!*

**Call Back Summary**

1. A callback is a function passed into another function as an argument to be executed later.
2. Callback functions can be synchronous or asynchronous.



**ANONYMOUS FUNCTIONS**

An anonymous function is a function without a name. An anonymous function is often not accessible after its initial creation.

ES6 introduced arrow function expression that provides a shorthand for declaring anonymous functions:

``` let show = () => console.log('Anonymous function'); ```

**Why do we need Anonymous Functions?**
1. It doesn't make sense to crowd the global namespace with normal functions. If a function wont be used anywhere, declare it as anonymous.
2. Anonymous functions are declared inline and inline functions have advantages in that they can access variables in the parent scopes.
3. The code seems more self-contained and readable when handlers are defined right inside the code that's calling them. You can read the code in almost sequential fashion rather than having to go find the function with that name. 

---