# Javascript
**Javascript** is the language of the web.

## Table of Contents
- [Hoisting](#hoisting)
- [Variables](#variables)
- [Functions](#functions)
- [Useful](#useful)
- [Conditions](#conditions)
- [Loops](#loops)
- [JSON](#json)

## Hoisting

Both variable and function declarations are hoisted to the top on code execution, meaning that their order is irrelevant i.e functions can be called before they are declared.

## Variables

```javascript
var a; //Regular
let b; //Block Scoped
const c; //immutable
```

### Data types
```javascript
let a = 12; //Integer
let b = "Test"; //String
let c = [1,2,3,4]; //Array
let d = {"hi":"Hello"} //Object
```

## Functions
Functions are first class objects - a function is a regular object of type function. The function object type has a constructor: `Function`.

There are several ways to declare a function.

The difference is how the function interacts with the external components (the outer scope, the enclosing context, object that owns the method, etc) and the invocation type (regular function invocation, method invocation, constructor call, etc).

### Function Declaration
**Hoisted**. Available immediately after parsing, before any code is executed.

The function declaration creates a variable in the current scope with the identifier equal to function name. This variable holds the function object.

```javascript
function foo() {}
foo();
```

Use them when a function expression is not appropriate or when it is important that that a function is hoisted.

### Function Expression
**Not hoisted**. Available only after the variable assignment is executed.

```javascript
// Named
let bar = function foo() {};
bar();
foo(); // undefined
```
Use them when you are doing recursion or want to see the function name in the debugger.

```javascript
// Anonymous
let foo = function() {};
foo();

let bar = foo();
bar(); // Error: not a function.
```
Use them when you want to pass a function as an argument to another function or you want to form a closure.

### Immediately Invoked Function Expression
```javascript
(function() {
    // ...
})();
```
### ES6
```javascript
const foo = () => {
console.log('I am getting called')
};

foo();
```

### Function constructor (Avoid this)
let foo = new Function();

### Other
- Use function declaration generators function* foo(){} when you want to exit and then re-enter a function.
- Use function expression generators let foo = function* [name](){} when you want to exit and then re-enter a nested function.

### Function parameters vs arguments
An argument is the value supplied to the parameter.
```javascript
function foo(bar) {
    // bar is a parameter
    console.log(bar);
}

foo("baz"); // baz is an argument.
```

## Useful
### Truthy / Falsy
Strings with at least one letter and numbers larger than zero are truthy.
```javascript
console.log(true && "foo"); // foo
console.log(true && "foo" && 1); // 1
```

## Conditions

### If/Else
```javascript
const age = (age) => {
  if (age < 10) {
    return "Kid";
  }if else(age > 10 || age < 20){
      return "Teen";
  }if else(age > 20 || age < 50){
    return "Adult";
  }else {
    return "Old";
  }
}
age(10);
```

### Do/While
```javascript
let text = "";
let i = 0;
do{
  text += "The number is "+i;
}while(i<5);
```

### Try/Catch
```javascript
let x = "";

try{
  if(x == "") throw "Empty";
}catch(error){
  console.log(error);
}
```

## Loops
### For
```javascript
let plus = 0;
for(let i = 0 ; i < 5; i++){
 plus = plus +i;
}
```

### For Each
```javascript
let array = [1,2,3,4,5];
array.forEach((value,index,array)=>{
  console.log(value,index,array)
});
```

### Map
```javascript
let array = [1,2,3,4,5];
let doubled = array.map((num) => {
    return num * 2;
});
```

## JSON
**Javascript Object Notation** is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate. It is based on a subset of the JavaScript Programming Language, Standard ECMA-262 3rd Edition - December 1999.

### Examples
```javascript
{
    "glossary": {
        "title": "example glossary",
		"GlossDiv": {
            "title": "S",
			"GlossList": {
                "GlossEntry": {
                    "ID": "SGML",
					"SortAs": "SGML",
					"GlossTerm": "Standard Generalized Markup Language",
					"Acronym": "SGML",
					"Abbrev": "ISO 8879:1986",
					"GlossDef": {
                        "para": "A meta-markup language, used to create markup languages such as DocBook.",
						"GlossSeeAlso": ["GML", "XML"]
                    },
					"GlossSee": "markup"
                }
            }
        }
    }
}
```

```javascript
{
  "users":{
    "1":{
      "name":"john",
      "lastname":"doe"
    },
    "2":{
      "name":"jane",
      "lastname":"doe"
    }
  }
}
```

### JSON Validator
https://oyoyoi.github.io/JSONValidator-Javascript/
