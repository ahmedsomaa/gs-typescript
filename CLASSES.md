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

// create an object
let messi = new Footballer('Lionel Messi', 34);
```

## Access Modifiers

An **access modifier** specifies the accessibility of the class variable or method outside the class. Three access modifiers are available:

- Public
- Private
- Protected

### Public Access Modifier

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

### Private Access Modifier

Private variables and methods cannot be accessed outside the classes. The private members can be accessed only inside the class in which it is created.

```ts
class Course {
  private courseNumber: string; // this is a private property

  constructor(courseNumber: string) {
    this.courseNumber = courseNumber;
  }

  // public method
  getCourseNumber(): string {
    // courseNumber can be accessed here as we're in the same class
    return this.courseNumber;
  }
}

const biology = new Course('BIO101');
console.log(biology.getCourseNumber()); // prints BIO101
console.log(biology.courseNumber); //throws an error: Property 'courseNumber' is private and only accessible within class 'Course'.
```

### Protected Access Modifier

Protected variables and methods can be accessed inside the containing class and its child classes (derived classes).

```ts
// base class
class Course {
  protected courseNumber: string; // this is a protected property

  constructor(courseNumber: string) {
    this.courseNumber = courseNumber;
  }

  // public method
  getCourseNumber(): string {
    return this.courseNumber;
  }
}

// inherited class
class MathCourse extends Course {
  constructor(courseNumber: string) {
    super(courseNumber);
  }

  toString(): string {
    return `Course Name: Math, CourseNumber: ${this.courseNumber}`; // accessible because of protected
  }
}
```

## Getters and Setters

In TypeScript, The getters and setters are two terms that can be used to get and set the value of the class members.
For each property:

- A **getter** method returns the value of the property’s value. A getter is also called an _accessor_.
- A **setter** method updates the property’s value. A setter is also known as a _mutator_.

A getter method starts with the keyword `get` and a setter method starts with the keyword `set`.

```ts
class Book {
  private _bookName: string;
  private _bookISBN: string;

  constructor(bookName: string, bookISBN: string) {
    this._bookName = bookName;
    this._bookISBN = bookISBN;
  }

  // getters
  public get bookName() {
    return this._bookName;
  }

  public get bookISBN() {
    return this._bookISBN;
  }

  // setters
  public set bookName(bookName: string) {
    this._bookName = bookName;
  }

  public set bookISBN(bookISBN: string) {
    this._bookISBN = bookISBN;
  }
}
```

## 🔖 References

- [What are access modifiers in TypeScript?](https://www.educative.io/answers/what-are-access-modifiers-in-typescript)
- [How to use getters and setters in TypeScript?](https://www.tutorialspoint.com/how-to-use-getters-and-setters-in-typescript)
- [TypeScript Getters and Setters](https://www.typescripttutorial.net/typescript-tutorial/typescript-getters-setters/)
