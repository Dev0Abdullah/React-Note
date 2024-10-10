# React-Note
This Is React Notes
# Waht is React ?
React is a JavaScript library for building user interfaces, especially single-page applications (SPAs). It allows developers to create large web applications that can update and render efficiently in response to data changes, without reloading the entire page.
In JavaScript, especially when using **ES6 modules**, there are two main ways to export components, functions, or variables from a file: `export` and `export default`. They both allow you to make code from one file available to another, but they work in slightly different ways.

### 1. **`export` (Named Export)**
   - You can export multiple things from a file using **named exports**.
   - Each item is explicitly exported by name, and when you import it, you must use the same name (or rename it using `as`).

#### Example:

```js
// file: math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

To import named exports, you use the exact name of the export:

```js
// file: app.js
import { add, subtract } from './math';

console.log(add(5, 3));  // Outputs: 8
console.log(subtract(5, 3));  // Outputs: 2
```

- You can export **multiple** named exports from the same file.
- If you want to rename them during import, you can use `as`:

```js
import { add as sum } from './math';
```

### 2. **`export default` (Default Export)**
   - Each file can have **only one default export**.
   - A default export can be a function, class, or variable.
   - When importing a default export, you can give it any name you want because it's the default export.

#### Example:

```js
// file: calculator.js
export default function multiply(a, b) {
  return a * b;
}
```

To import a default export, you don’t need curly braces, and you can choose any name for the import:

```js
// file: app.js
import multiply from './calculator';

console.log(multiply(5, 3));  // Outputs: 15
```

- There can only be **one** default export per file.
- You can still have named exports alongside a default export in the same file.

### Summary of Differences:

| Feature            | `export` (Named Export)                         | `export default` (Default Export)            |
|--------------------|-------------------------------------------------|---------------------------------------------|
| **Number of exports per file** | Multiple named exports per file                 | Only one default export per file            |
| **Import syntax**  | Must import using the exact name (or rename with `as`) | Can import with any name                    |
| **Curly braces needed in import** | Yes (`import { ... }`)                        | No (`import ...`)                           |
| **Use case**       | Used when exporting multiple items from a file | Used when the file exports one main item    |

In many cases, `export` is used for utilities or smaller functions, while `export default` is typically used for exporting the main function or component of a module.
