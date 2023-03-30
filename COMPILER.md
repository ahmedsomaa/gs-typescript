# TypeScript Compiler

## Watch Mode

To run TypeScript in watch mode, use `tsc filename.ts --watch` or `tsc filename.ts -w`.

## Compile Multiple `.ts` Files

In order to be able to compile multiple `.ts` files down to `.js` files:

1. Run `tsc --init`. This will create a `tsconfig.json` file where you can set several compilation flags like `outDir`.

2. Now, you can run `tsc` without specifying filename and all `.ts` files will be compiled down to `.js` files.

## Include & Exclude

- Use the `include` option to add the files you want the TypeScript's compiler to compile down to JavaScript.

- Use the `exclude` option to add the files you want the TypeScript's compiler to igonre and not to compile down to JavaScript. An example would be `node_modules` directory but they are ignored by default.

- Use the `files` option to choose only specific files for compilation.

```json
{
  "comilerOptions": {},
  "include": ["app.ts", "server.ts"],
  "exclude": ["node_modules"]
}
```
