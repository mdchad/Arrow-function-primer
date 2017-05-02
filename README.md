# Arrow-function-primer

In ES2015, we saw arrow function was introduced. Two of the benefits of arrow function are:

1. Shorter function expression
2. Solve the non-binding of this

**Syntax

ES5

``` 
var a = function(b) {
   return b * 2
}

a(2)   //4
```


ES2015 with single parameter (concise body)


```
let a = b => b * 2

a(2)  //4
```


ES2015 with return statement (block body)


```
let a = b => {
   return b * 2
}

a(2)  //4
```


ES2015 with multiple parameters


```
let a = (b, c) => b * c 

a(2, 2)  //4
```


ES2015 with no parameters


```
let a = () => 2 * 2 

a()  //4
```


ES2015 returning object literal


```
let a = () => ({
    foo: 'bar'
})

a()   //{ foo: 'bar' }
```


ES2015 returning object literal with return statement


```
let a = () => {
   return {
      foo: 'bar'
   }
}

a()
```


ES5 callback 


```
[1,2,3,4].map(function(val) {
   return val * 2
})

//[2,4,6,8]
```


ES2015 callback 


```
[1,2,3,4].map(val => val * 2 )

//[2,4,6,8]
```

ES5 IIFE 


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

ES2015 IIFE


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



**Solving Bind

ES5

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


ES2015


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

ES5 Binding in constructor
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


ES2015 Binding in constructor


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


Further reading

[Mozilla MDN](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
[Understanding ECMAScript 6: The Definitive Guide for JavaScript Developers](https://www.amazon.com/Understanding-ECMAScript-Definitive-JavaScript-Developers/dp/1593277571/ref=sr_1_1?s=books&ie=UTF8&qid=1493735907&sr=1-1&keywords=understanding+ecmascript+6)
[When not to use arrow function](https://rainsoft.io/when-not-to-use-arrow-functions-in-javascript/)
[Do ES6 Arrow Functions Really Solve “this” In JavaScript?](https://derickbailey.com/2015/09/28/do-es6-arrow-functions-really-solve-this-in-javascript/)

