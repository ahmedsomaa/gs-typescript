# Introduction

TypeScript is a free and open-source programming language developed and maintained by Microsoft. It was developed by Anders Hejlsberg at Microsoft and it was first released in 2012 as a superset to JavaScript.

## What is TypeScript ?

> TypeScript is a JavaScript Superset.

This means that TypeScript is a programming language buliding up on JavaScript by adding new features and advantages
to JavaScript like types...etc. Though, it's a JavaScript superset, neither the browser nor nodejs can execute it and
it has to be compiled down to JavaScript. So the question has to be asked, why TypeScript then ?

## Why TypeScript ?

- **Static typing** – TypeScript comes with optional static typing and a type inference system, which means that a variable, declared with no type may be inferred by TypeScript based on its value.

- **Object oriented programming** – TypeScript supports object-oriented programming concepts like classes, inheritance.

- **Compile time checks** – JavaScript is an interpreted programming language. There is no compilation involved. Hence, the errors get caught during the runtime. Since TypeScript compiles into JavaScript, errors get reported during the compile time rather than the runtime.

- **Code editor support** – IDEs or code editors like VS Code support autocomplete for a TypeScript codebase. They also provide inline documentation and highlight the errors.

- **Use existing packages** – You might want to use an npm package that is written in JavaScript. Since TypeScript is a superset of JavaScript, you can import and use that package. Moreover, the TypeScript community creates and maintains type definitions for popular packages that can be utilized in your project.

- **Next-gen JavaScript Features** - TypeScript supports Next-gen JavaScript features compiled down for older browsers.

- **Non-JavaScript Features** - TypeScript adds new features which don't exit in JavaScript such as interfaces, generics...etc.

- **Meta-Programming Features** - TypeScript adds add meta programming features like decorators...etc.

## Installing and Using TypeScript

- Make sure to have [nodejs](https://nodejs.org) installed on your machine. You can check using `node --version`.
- Run the commmand `npm install -g typescript`.
- To use TypeScript, you can run the command `tsc` on any `.ts` file and it will compile it down to JavaScript.

## 🔖 References

- [What is TypeScript and why should you use it?](https://www.contentful.com/blog/what-is-typescript-and-why-should-you-use-it/)
