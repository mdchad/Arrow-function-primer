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

ES2015 with single parameter

```
let a = b => b * 2

a(2)  //4
```

ES2015 with return statement

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

