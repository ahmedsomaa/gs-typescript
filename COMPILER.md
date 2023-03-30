# TypeScript Compiler

## Watch Mode

To run TypeScript in watch mode, use `tsc filename.ts --watch` or `tsc file.ts -w`.

## Compile Multiple `.ts` Files

In order to be able to compile multiple `.ts` files down to `.js` files:

1. Run `tsc --init`. This will create a `tsconfig.json` file where you can set several compilation flags like `outDir`.

2. Now, you can run `tsc` without specifying filename and all `.ts` files will be compiled down to `.js` files.
