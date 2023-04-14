# Classes & Interfaces

## Definitions

`Objects`: Things we work with in our code. Moreover, Instances of classes.

`Classes`: Blueprints for objects which means they defined how objects look like, properties and methods.

## First Class

To create a class in TypeScript, use the keyword `class` followed by the class name. The conventional way to name a class is to start with a capital letter. Then add the class attributes, and the `constructor` method.

```ts
class Footballer {
  _name: string;
  _age: number;

  constructor(name: string, age: number) {
    this._name = name;
    this._age = age;
  }
}

// instantiate an object
let messi = new Footballer('Lionel Messi', 34);
```
