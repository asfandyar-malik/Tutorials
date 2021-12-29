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

A function implicitly returns undefined, when no return value is specified. 

As functions are objects, you can return them from a function. 


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

**Function Hoisting**
In javascript we can use a function before it is declared. 

```
showMe(); // a hoisting example

function showMe(){
    console.log('an hoisting example');
}
```


---
**forEach() Method**

Javascript Array forEach() method. This is a replacement to for loop where we iterate through the whole array. 

```Array.forEach(callback [, thisArg]); ```

forEach method executed a **callback** on every on every element of an array. 


**reduce() Method**

This method is there to reduce the array to a single value. 

Syntax of reduce method

A reduce method takes 2 arguments: a reducer **callback** function and an optional initial value.

```array.reduce(reducer [, initialValue]) ```


Syntax of **reducer** method:

``` function reducer(accumulator, currentValue, currentIndex, array){} ```

Here **accumulator** is the value returned from the previous call of the reducer function. 

Check below, how **accumulator** is working here: 

```
let numbers = [1, 2, 3];

let sum = numbers.reduce(function (accumulator, currentValue) {
    return accumulator + currentValue;
});
console.log(sum);
```

Second **reduce** example: 

We have an array of shoppingCart here: 

```
let shoppingCart = [{
        product: 'phone',
        qty: 1,
        price: 699
    },
    {
        product: 'Screen Protector',
        qty: 1,
        price: 9.98
    },
    {
        product: 'Memory Card',
        qty: 2,
        price: 20.99
    }
];

```

```
let total = shoppingCart.reduce(function (acc, curr) {
    return acc + curr.qty * curr.price;
},0);

console.log(total);
```

The **reduceRight()** method works in the same way as the reduce() method, but in the opposite direction.

---

**IIFE (Immediately invoked function expressions)**

The following expression is called an immediately invoked function expression (IIFE) because the function is created as an expression and executed immediately:

```
(function(a,b){
        return a + b;
})(10,20);
```

Why?
1. So that functions and variables dont pollute the global object. All functions and variables inside an immediately invoked function expression 

An IIFE can have a name. However, it cannot be invoked again after execution:

---

**Javascript Objects**


In JavaScript, an object is an unordered collection of key-value pairs. Each key-value pair is called a **property**.


The key of a property can be a string and the value of a property can be any valid JavaScript value e.g., a string, a number, an array, and even a function.

When a function is a property of of an object, it’s often called a method.

Unlike objects in other programming languages such as Java and C++, you can add a property to an object after object creation.

Besides data, objects can have actions. The actions of objects are known as methods.


```
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

person.greet = function () {
    console.log('Hello!');
}
person.greet();
```

Output: 

```
Hello!

```




**Javascript Object Properties**


```
let person = {
    firstName: 'John',
    lastName: 'Doe'
}

Object.defineProperty(person, 'fullName', {
    get: function () {
        return this.firstName + ' ' + this.lastName;
    },
    set: function (value) {
        let parts = value.split(' ');
        if (parts.length == 2) {
            this.firstName = parts[0];
            this.lastName = parts[1];
        } else {
            throw 'Invalid name format';
        }
    }
});

console.log(person.fullName);
```
Output: 
```
John Doe
```



```
let person = {
    firstName: 'John',
    lastName: 'Doe'
};

person.greet = function () {
    console.log('Hello!');
}
person.greet();
```