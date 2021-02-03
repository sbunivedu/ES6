# ES6(ECMA2015)
## let

let is similar to var but let has scope. let is only accessible in the block level it is defined.
```javascript
if (true) {
 let a = 40;
 console.log(a);
}
console.log(a);

let a = 50;
let b = 100;
if (true) {
 let a = 60;
 var c = 10;
 console.log(a/c);
 console.log(b/c);
}
console.log(c);
console.log(a);

const
const is used to assign a constant value to a variable. The variable value cannot be changed.

const a = 50;
a = 60;
b = "Assigning new value";

const LANGUAGES = ['Js', 'Ruby', 'Python', 'Go'];
LANGUAGES = "Javascript";
LANGUAGES.push('Java');
console.log(LANGUAGES);
```

## (Flat) Arrow Function
```javascript
let NewOneWithParameters = (a, b) => {
 console.log(a+b);
}
NewOneWithParameters(10, 20);
```

## Default Parameters
```javascript
let Func = (a, b = 10) => {
 return a + b;
}
Func(20);
Func(20, 50);

let NotWorkingFunction = (a = 10, b) => {
 return a + b;
}
NotWorkingFunction(20);
```

## Enhanced For Loop
"for in" loop iterates through a list of elements (e.g. array or object) and return the elements indexes one by one.

```javascript
let arr = [2,3,4,1];
for (let value in arr) {
  console.log(value);
}// output: 0, 1, 2, 3


let person = {fname:"John", lname:"Doe", age:25};
for (let name in person) {
  console.log(name);
}// output: frame, name, age
```

"for of" loop iterates through a list of elements (e.g. array or object) and return the elements one by one.

```javascript
let arr = [2,3,4,1];
for (let value of arr) {
  console.log(value);
} // output: 2 3 4 1
```

The following example doesn't work because property values in person is not utterable.

```javascript
let person = {fname:"John", lname:"Doe", age:25};
for (let value of person) {
  console.log(value);
}// output: error

let string = "Javascript";
for (let char of string) {
  console.log(char);
}

let arr = [2,3,4,1];
for (let value of arr) {
 console.log(value);
}

let string = "Javascript";
for (let char of string) {
 console.log(char);
}
```

## Spread Arguments
```javascript
let SumElements = (arr) => {
 console.log(arr);
 let sum = 0;
 for (let element of arr) {
  sum += element;
 }
 console.log(sum);
}

SumElements([10, 20, 40, 60, 90]);

let SumElements = (...arr) => {
 console.log(arr);
 let sum = 0;
 for (let element of arr) {
  sum += element;
 }
 console.log(sum);
}

SumElements(10, 20, 40, 60, 90); // Note we are not passing array here. Instead we are passing the elements as arguments.

Math.max(10, 20, 60, 100, 50, 200); // returns 200.
);

let arr = [10, 20, 60];
Math.max(arr);

let arr = [10, 20, 60];
Math.max(...arr);
```

source: https://hackernoon.com/es6-for-beginners-f98120b57414

## Maps

Map holds key-value pairs. All indexes are unique. We can use any value as key or value.

```javascript
var map = new Map();
map.set('name', 'John');
map.set('name', 'Andy');
map.set(1, 'number one');
map.set(NaN, 'No value');

map.get('name'); // Andy. Note John is replaced by Andy.
map.get(1); // number one
map.get(NaN); // No value

var map = new Map();
map.set('name', 'John');
map.set('id', 10);

map.size; // 2. Returns the size of the map.

map.keys(); // outputs only the keys.
map.values(); // outputs only the values.

for (let key of map.keys()) {
  console.log(key);
} // output: name id

var map = new Map();

for (let element of map) {
  console.log(element);
} //output: ['name', 'John'] ['id', 10]

for (let [key, value] of map) {
  console.log(key+" - "+value);
}

Output:
name - John
id - 10
```

## Sets

```javascript
var sets = New Set([1,5,6,8,9]);
sets.size; // returns 5. Size of the set.
sets.has(1); // returns true.
sets.has(10); // returns false.

Static methods

class Example {
 static Callme() {
 console.log("Static method");
 }
}
Example.Callme();

Output:
Static method

Class People{
  constructor(name) {
    this.name = name;
  }
  get Name() {
    return this.name;
  }
  set Name(name) {
    this.name = name;
  }
}

let person = new People("Jon Snow");
console.log(person.Name);
person.Name = "Dany";
console.log(person.Name);
```

## Async Await

```javascript
async function hello() {
  let response = await fetch('https://api.github.com/');
  // above line fetches the response from the given API endpoint.
  return response;
}
hello()
.then(function(x) {
  console.log(x);
  console.log(x.json());
});
```

source: https://hackernoon.com/es6-for-beginners-part-2-ee8a77f7f4c7

## Array Map

```javascript
let arr = [1,2,3,4,5];
let modifiedArr = arr.map(function(element, index, arr) {
  return element * 10;
});
console.log(modifiedArr);
```

## Array Filter

```javascript
let arr = [1, 2, 3, 4, 5, 6]
let modifiedArr = arr.filter(function(element, index, array) {
  return element % 2 == 0
});
console.log(modifiedArr);
Array Reduce
let arr = [1,2,3,4,5,6];
let totalSum = arr.reduce(function(sum, element, index, array) {
  console.log(sum+"+"+element+"="+(sum+element));
  return sum + element;
}, 10);
console.log("Total sum is "+ totalSum);
```
