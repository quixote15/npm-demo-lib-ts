# This is a npm demo project written in Typescript

The goal of this project is to be a guide line and starting point for creating npm Javascript libraries with Typescript.

## how to use
```shell
npm install demo-lib-ts
```

```
// using commonJS
const {add} = require('demo-lib-ts');
add(2,4)


// using es6
import {add} from 'demo-lib-ts';
add(2,4);

```

## How to create & publish a npm package with Typescript

### Step 1 - Create a new npm project

`npm init -y`

### Step 2 - Add Typescript to your project

You will need to add `typescript` to your dev dependencies:

`npm i -D typescript` 

### Step 3 - Create a tsconfig File
By add tsconfig.json file in your project indicates that the directory is the root of a TypeScript project. The tsconfig.json file specifies the root files and the compiler options required to compile the project.

You can create this file manually or use `tsc`:

`npx tsc --init`

This command will create a `tsconfig.json` with default configurations.

### Step 4 - Create your lib
In this project I have just exported a function on `src/index.ts`

```js
export function add(a: number, b: number) {
  return a + b;
}
```

### Step 4 - Setup package.json
When you publishing your lib, npm will look into your package.json for information. Here`s how you should do it:  
```
{
  "name": "your-lib-name",
  "version": "1.0.0",
  "description": "this is a lib to build libs",
  "main": "lib/index.js", // your library entry point file
  "types": "lib", // since we are using ts
  "scripts": {
    "build": "tsc -p ." // compile ts files into commonJs 
  },
  ...
}
```

### Step 5 - Publish

If you do not have a npm account run: `npm adduser`

If you already have an account run: `npm login` 

then `npm publish`

Its done!