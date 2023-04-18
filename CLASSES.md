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

## Access Modifiers

An **access modifier** specifies the accessibility of the class variable or method outside the class. Three access modifiers are available:

- Public
- Private
- Protected

### Public Access modifier

Public variables and methods can be accessed by other classes and objects. By default, the members of a class are public in TypeScript. To declare a public variable/method, we use the `public` keyword before the declaration of the variable or method.

```ts
class Course {
  courseNumber: string; // this is a public property by default

  constructor(courseNumber: string) {
    this.courseNumber = courseNumber;
  }

  // public method
  getCourseNumber(): string {
    return this.courseNumber;
  }
}

const biology = new Course('BIO101');
console.log(biology.courseNumber); // prints BIO101
console.log(biology.getCourseNumber()); // prints BIO101
```
