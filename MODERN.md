# TypeScript & Modern JavaScript

# let & const

Introduced in ES6.

`const` is used to declare constants while `let` is used to declare variables.
`var` is till there but not recommended for usage and `let` is preferred because `var` declarations are globaly-scoped and function-scoped while `let` declarations are block-scoped.

```js
if (true) {
  var flag = true;
}

console.log(flag); // No Error -> prints true

if (true) {
  let flag = true;
}

console.log(flag); // Uncaught ReferenceError: flag is not defined
```

## Arrow Functions

lets us declare a new function without using the `function` keyword. If the function
only has one expression, the `return` keyword can be excluded. If the function only has one parameter, we could remove the function parenthesis `()` as well.

```ts
// old
function addOld(a: number, b: number) {
  return a + b;
}

// new
const addNew = (a: number, b: number) => {
  return a + b;
};

// no return statement
const addNoReturn = (a: number, b: number) => a + b;
```

## Default Function Parameters

ES6 allows for functions to have default values for parameters, and it is preferred to make default function params come last.

```ts
function add(a: number, b: number = 1) {
  return a + b;
}

console.log(add(2)); // prints 3
```

## The Spread Operator (...)

It expands the array into individual elements. So, it can be used to expand the array in a places where zero or more elements are expected.

Uses cases for the spred operator include:

- Copying an array.
- Concatenating arrays.
- Spreading elements together with an individual element.
- Spreading elements on function calls.
- Spread syntax for object literals.

```ts
// Copying an array
let fruits = ['Apple', 'Orange', 'Banana'];
let fruitsCopy = [...fruits];
console.log(fruitsCopy); // ['Apple','Orange','Banana']

// Concatenating arrays
let arr1 = ['A', 'B', 'C'];
let arr2 = ['X', 'Y', 'Z'];
let result = [...arr1, ...arr2];
console.log(result); // ['A', 'B', 'C', 'X', 'Y', 'Z']

// Spreading elements together with an individual element
let newFruits = ['Cherry', ...fruits];
console.log(newFruits); // ['Cherry', 'Apple','Orange','Banana']

// Spreading elements on function calls
const getFruits = (f1: string, f2: string, f3: string) => {
console.log(Fruits: ${f1}, ${f2} and ${f3}); };
getFruits(...fruits); // Fruits: Apple, Orange and Banana

// Spread syntax for object literals
let obj1 = { id: 101, name: 'Jhon Doe' }
let obj2 = { age: 25, country: 'USA'}
const employee = { ...obj1, ...obj2 }

console.log(employee); //{ "id": 101, "name": "Jhon Doe", "age": 25, "country": "USA" }
```

## Rest Parameters

The rest parameter syntax allows a function to accept an indefinite number of arguments as an array.

```ts
function sum(...numbers: number[]) {
  return numbers.reduce((accu, curr) => accu + curr, 0);
}

console.log(sum(1, 2)); // prints 3
console.log(sum(1, 2, 3)); // prints 6
console.log(sum(1, 2, 3, 4)); // prints 10
console.log(sum(1, 2, 3, 4, 5)); // prints 15
```

## Array & Object Destructruing

Destructuring assignment is a special syntax that allows us to “unpack” arrays or objects into a bunch of variables, as sometimes that’s more convenient.

```ts
// Array destructuring
const fruits = ['Apple', 'Banana', 'Mango'];

// old: access by index
let fruit1 = fruits[0];
let fruit2 = fruits[1];

// new: destructuring
let [fruit_1, fruit_2] = fruits;
// fruit_1 -> 'Apple'
// fruit_2 -> 'Banana'

// Object destructuring
const user = { firstName: 'Ahmed', lastName: 'Abu Qahf', age: 27 };

// old: the dot or bracket notation
let firstName = user.firstName;
let age = user['age'];

// new: destructuring
const { firstName, age } = user;
// firstName -> 'Ahmed'
// age -> 27
```

## 🔖 References

- [JavaScript: Var, Let, or Const? Which One Should you Use?](https://codeburst.io/javascript-var-let-or-const-which-one-should-you-use-2fd521b050fa)

- [Var, Let, and Const – What's the Difference?](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference/)

- [ES6 Tutorials : SPREAD Operator with Fun](https://www.codingame.com/playgrounds/7998/es6-tutorials-spread-operator-with-fun)

- [Rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)

- [Destructuring assignment](https://javascript.info/destructuring-assignment)
