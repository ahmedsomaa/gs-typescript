# TypeScript & Modern JavaScript

# let & const

Introduced in ES6.

`const` is used to declare constants while `let` is used to declare variables.
`var` is till there but not recommended for usage and `let` is preferred because `var` declarations are globaly-scoped or function-scoped while `let` declarations are block-scoped.

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

## 🔖 References

- [JavaScript: Var, Let, or Const? Which One Should you Use?](https://codeburst.io/javascript-var-let-or-const-which-one-should-you-use-2fd521b050fa)

- [Var, Let, and Const – What's the Difference?](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference/)