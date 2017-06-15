# Arrow-function-primer

In ES2015, we saw arrow function was introduced. Two of the benefits of arrow function are:

1. Shorter function expression
2. Solve the non-binding of 'this'

### Syntax

ES5
<br>

``` 
var a = function(b) {
   return b * 2
}

a(2)   //4
```
<br>


ES2015 with single parameter (concise body)
<br>


```
let a = b => b * 2

a(2)  //4
```
<br>


ES2015 with return statement (block body)
<br>


```
let a = b => {
   return b * 2
}

a(2)  //4
```
<br>


ES2015 with multiple parameters
<br>


```
let a = (b, c) => b * c 

a(2, 2)  //4
```
<br>


ES2015 with no parameters
<br>


```
let a = () => 2 * 2 

a()  //4
```
<br>


ES2015 returning object literal
<br>


```
let a = () => ({
    foo: 'bar'
})

a()   //{ foo: 'bar' }
```
<br>


ES2015 returning object literal with return statement
<br>


```
let a = () => {
   return {
      foo: 'bar'
   }
}

a()
```
<br>


ES5 callback 
<br>


```
[1,2,3,4].map(function(val) {
   return val * 2
})

//[2,4,6,8]
```
<br>


ES2015 callback 
<br>


```
[1,2,3,4].map(val => val * 2 )

//[2,4,6,8]
```
<br>

ES5 IIFE 
<br>


```
let person = function(name) {
    return {
        getName: function() {
            return name;
        }
    };
}("Irsyad");
console.log(person.getName()); //'Irsyad'
```
<br>

ES2015 IIFE
<br>


```
let person = (function(name) {
    return {
        getName: function() {
            return name;
        }
    };
})("Irsyad");
console.log(person.getName()); //'Irsyad'
```
<br>


### Solving Bind
<br>

ES5
<br>

```
let PageHandler = {
    id: "123456",
    58 Chapter 3
    init: function() {
        document.addEventListener("click", (function(event) {
            this.doSomething(event.type);     // no error
        }).bind(this), false);
    },
    doSomething: function(type) {
        console.log("Handling " + type  + " for " + this.id);
   } 
};                //example from Understanding ECMAScript 6 by Nicholas Zakas

```
<br>


ES2015
<br>


```
let PageHandler = {
    id: "123456",
    init: function() {
        document.addEventListener("click", event => this.doSomething(event.type), false);
   },
    doSomething: function(type) {
        console.log("Handling " + type  + " for " + this.id);
   } 
};

```
<br>


ES5 Binding in constructor
<br>

```
class Foo {
   constructor() {
      this.bar = this.bar.bind(this)
   }
   
   bar: function() {
      //code
   }
}
```
<br>


Binding in constructor using property initilizer(do note that this is in stage-2 and not part of ES2015)
<br>


```
class Foo {
   constructor() {
      //empty
   }
   
   bar = () => {
      //code
   }
}
```
<br>


Further reading

[Mozilla MDN](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
<br>
[Understanding ECMAScript 6: The Definitive Guide for JavaScript Developers](https://www.amazon.com/Understanding-ECMAScript-Definitive-JavaScript-Developers/dp/1593277571/ref=sr_1_1?s=books&ie=UTF8&qid=1493735907&sr=1-1&keywords=understanding+ecmascript+6)
<br>
[When not to use arrow function](https://rainsoft.io/when-not-to-use-arrow-functions-in-javascript/)
<br>
[Do ES6 Arrow Functions Really Solve “this” In JavaScript?](https://derickbailey.com/2015/09/28/do-es6-arrow-functions-really-solve-this-in-javascript/)

