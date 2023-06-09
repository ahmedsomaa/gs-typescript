# TypeScript Basics

## Core Types

| Type      | Example                | Notes                                                                    |
| --------- | ---------------------- | ------------------------------------------------------------------------ |
| `number`  | `1, 2.5, -10`          | All numbers, no difference between integers or decimals                  |
| `string`  | 'TS', "TS", \`TS\`     | All text values                                                          |
| `boolean` | `true, false`          | Just these two values, no "truthy" or "falsey" values                    |
| `object`  | `{lang: 'TypeScript'}` | Any JavaScript object, more specific types are possible                  |
| Array     | `[1, 2, 3]`            | Any JavaScript array, type can be mixed or strict                        |
| Tuple     | `[2, 'John']`          | Fixed-length array added by TypeScript                                   |
| Enum      | `enum {SAT, SUN, MON}` | Automatically enumerated global constant identifiers added by TypeScript |
| Any       | `*`                    | Any kind of value, no specific type                                      |

## Special Types

| Type                 | Example                                       | Notes                                                                                                          |
| -------------------- | --------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `unknown`            | `let data: unknown`                           | `unknown` is a similar, but safer alternative to `any`. TypeScript will prevent unknown types from being used. |
| `never`              | `function(): never { throw Error('Error'); }` | `never` doesn't return and best suited for code that throws an error or infinite loops                         |
| `undefined` & `null` | `let x: undefined` & `let y: null`            | refer to the JavaScript primitives `undefined` and `null` respectively.                                        |

## Type Assignment

To declare a variable with type in TypeScript, simply use the colon `:` character and add the type after it.

```ts
let num: number = 11;
let str: string = 'eleven';
let bol: boolean = true;
```

## Type Inference

TypeScript is a typed language. However, it is not mandatory to specify the type of a variable. TypeScript infers types of variables when there is no explicit information available in the form of type annotations.

Types are inferred by TypeScript compiler when:

- Variables are initialized
- Default values are set for parameters
- Function return types are determined

```ts
// Variables are initialized
let num = 11; // Typescript infers that num is of type number
num = '11'; // Compile Error: Type 'string' is not assignable to type 'number'.

// Default values are set for parameters
// Here both a & b are infered to be of type 'number'
function add(a = 1, b = 2) {
  return a + b;
}

add(); // Ok
add(3, 4); // Ok
add('3', 4); // Compile Error: Argument of type 'string' is not assignable to parameter of type 'number'

// Function return types are determined
// TypeScript infers the return type of the function to be boolean
function greater(a: number, b: number) {
  return a > b;
}

let right: boolean = greater(2, 1); // Ok
let wrong: number = greater(2, 1); // Compile Error: Type 'boolean' is not assignable to type 'number'.
```

In complex objects, TypeScript looks for the most common type to infer the type of the object. However, if there is no super type that can encompass all the types present in the array, the compiler treats the type as a union of all types present in the array.

```ts
let nums = [1, 2, '3', 4]; // TypeScript infers that nums is of type number or string
nums.push(5); // Ok
nums.push(true); // Compiler Error: Argument of type 'boolean' is not assignable to parameter of type 'string | number'.
```

## Type Alias

Type Aliases allow defining types with a custom name (an Alias).

Type Aliases can be used for primitives like string or more complex types such as objects and arrays.

To create a type alias in TypeScript, just use the `type` keyword followed by an alias and then assign that alias to your type(s).

```ts
type Num = number;
type Answer = 'Yes' | 'No';
type Mixed = number | string;
```

## Functions as Types

TypeScript provides a `Function` type to annotate a variable as a function. However, this type doesn't tell anything about the function parameters nor the return type. Therefore, if you want your variable to to be of specific function type, it's better to use TypeScript's function types instead. TypeScripts' function types syntax is `(...params here) => return type`. It looks like an arrow function but it wouldn't return an actual value, instead we identify the return type for the function.

```ts
function subtract(a: number, b: number) {
  return a - b;
}

function displayResult(num: number) {
  console.log('Subtraction result: ', num);
}

// Function Type
let sub: Function;

sub = subtract; // Ok
sub = displayResult; // Ok

// Though this will not cause a Compile Error
// it would not make sense most of the time, so
// it is preferred to use function types instead
let func: (x: number, y: number) => number;

func = subtract; // Ok
func = displayResult; // Compile Error: Type '(num: number) => void' is not assignable to type '(x: number, y: number) => number'. Type 'void' is not assignable to type 'number'.
```

## 💡 Side Notes

> JavaScript uses _dynamic types_ (resolved at runtime) while TypeScript uses _static types_ (set during development).

## 🔖 References

- [Everyday Types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)

- [Type Inference in TypeScript](https://www.tutorialsteacher.com/typescript/type-inference)

- [TypeScript Type Aliases and Interfaces](https://www.w3schools.com/typescript/typescript_aliases_and_interfaces.php)
