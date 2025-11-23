# JAVASCRIPT.md

Welcome to your complete, end-to-end **JavaScript tutorial (ES5 → ES2025)**.  
This guide is tutorial-style: **theory → examples → mini exercises**, covering fundamentals, deep language mechanics, modern features, and practical browser/Node essentials.

---

# Part 1: Fundamentals

---

## Chapter 1.1: What Is JavaScript?

### Section 1.1.1: Language Overview

**Theory**  
JavaScript (JS) is a **high-level, multi-paradigm, dynamically typed** language. It runs primarily in:

- **Browsers** (front-end): drives interactivity using Web APIs.
- **Servers** (Node.js, Deno, Bun): builds backends, CLIs, tools.
- **Edge/serverless** runtimes (Cloudflare Workers, Vercel Edge).
- **Mobile/desktop** via frameworks (React Native, Electron).

JavaScript uses a **single-threaded event loop** model but supports concurrency through async APIs.

**Why it matters**  
JS is everywhere. Mastering the language (not just frameworks) makes you effective across web, backend, tooling, and automation.

---

## Chapter 1.2: Setup

### Section 1.2.1: Node + npm

**Theory**  
Node.js lets you run JavaScript outside the browser. `npm` is the package manager and script runner.

```bash
node -v
npm -v
```

Initialize a project:

```bash
mkdir my-js && cd my-js
npm init -y
```

---

### Section 1.2.2: Browser DevTools

**Theory**  
Every major browser ships DevTools with a **Console**, **Network**, **Sources**, and **Performance** tab. You’ll use them for debugging, profiling, and inspecting DOM/network activity.

Try in console:

```js
console.log("Hello from DevTools!");
```

---

### Section 1.2.3: ES Modules vs CommonJS

**Theory**  
JavaScript has two module systems:

- **ES Modules (ESM)** ✅: standard in modern JS.
- **CommonJS (CJS)** ✅: legacy Node system.

**ESM**
```js
// math.js
export const add = (a, b) => a + b;
export default function mul(a, b) { return a * b; }

// main.js
import mul, { add } from "./math.js";
```

**CommonJS**
```js
// math.cjs
const add = (a,b) => a+b;
module.exports = { add };

// main.cjs
const { add } = require("./math.cjs");
```

**Runtime note**  
Node uses ESM when `"type": "module"` is set in `package.json`.

---

## Chapter 1.3: Variables and Scoping

### Section 1.3.1: var, let, const

**Theory**  
JavaScript has three declarations:

- `var` ✅: function-scoped, hoisted, legacy.
- `let` ✅: block-scoped, reassignable.
- `const` ✅: block-scoped, **not reassignable** (but objects can mutate).

```js
var a = 1;
let b = 2;
const c = 3;
```

Prefer **`const` by default**, `let` if reassignment is needed, avoid `var`.

---

### Section 1.3.2: Hoisting and Temporal Dead Zone

**Theory**  
Declarations are “hoisted” (moved to top of scope):

- `var` initializes to `undefined`.
- `let/const` hoist but **cannot be used before declaration** (TDZ).

```js
console.log(x); // undefined
var x = 10;

// console.log(y); // ReferenceError (TDZ)
let y = 20;
```

---

## Chapter 1.4: Data Types

### Section 1.4.1: Primitives vs References

**Theory**  
JavaScript types:

**Primitives (immutable)**
| Type | Example | Notes |
|---|---|---|
| number | `42`, `3.14` | 64-bit float |
| bigint | `999n` | arbitrary integer |
| string | `"hi"` | UTF-16 |
| boolean | `true` | |
| undefined | `let a;` | unset |
| null | `let a=null;` | intentional empty |
| symbol | `Symbol("id")` | unique keys |

**Reference types (mutable)**  
Objects, arrays, functions, maps, sets, dates, etc.

```js
const n = 1;           // primitive
const obj = { a: 1 };  // reference
```

---

### Section 1.4.2: typeof and Type Checks

```js
typeof 10;          // "number"
typeof 10n;         // "bigint"
typeof "x";         // "string"
typeof null;        // "object" (historical quirk)

Array.isArray([]);  // true
```

---

## Chapter 1.5: Type Coercion and Equality

### Section 1.5.1: Truthy / Falsy

**Theory**  
Falsy values are only:

`false, 0, -0, 0n, "", null, undefined, NaN`

Everything else is truthy.

```js
if ("0") console.log("truthy"); // runs
if (0) console.log("nope");     // doesn't run
```

---

### Section 1.5.2: == vs ===

**Theory**  
- `==` performs coercion (loose).
- `===` compares type + value (strict). Prefer strict.

```js
0 == false;   // true
0 === false;  // false
"5" + 1;      // "51"
"5" - 1;      // 4
```

---

## Chapter 1.6: Operators

### Section 1.6.1: Core Operators

```js
// Arithmetic
+ - * / % **

// Comparison
> < >= <= == === != !==

// Logical
&& || !
```

---

### Section 1.6.2: Modern Operators

**Optional chaining** ✅
```js
const city = user?.profile?.city;
```

**Nullish coalescing** ✅  
Only falls back on `null` or `undefined`.

```js
const name = input ?? "Anonymous";
```

**Logical assignment** ✅
```js
a ||= 10;   // if a is falsy
b &&= 20;   // if b is truthy
c ??= 30;   // if c is nullish
```

---

## Chapter 1.7: Control Flow

### Section 1.7.1: Conditionals

```js
if (x > 10) { ... }
else if (x > 5) { ... }
else { ... }
```

Ternary:

```js
const msg = ok ? "yes" : "no";
```

---

### Section 1.7.2: switch

```js
switch (day) {
  case "Sat":
  case "Sun":
    rest();
    break;
  default:
    work();
}
```

---

### Section 1.7.3: Loops and Labels

```js
for (let i=0; i<3; i++) {}
while (cond) {}
do {} while (cond);
```

`for...of` vs `for...in`:

```js
for (const v of [10,20]) console.log(v); // values
for (const k in {a:1,b:2}) console.log(k); // keys
```

Labels (rare, but exists):

```js
outer:
for (let i=0;i<3;i++){
  for (let j=0;j<3;j++){
    if (j===1) continue;
    if (i===2) break outer;
  }
}
```

---

## Chapter 1.8: Functions and Closures

### Section 1.8.1: Function Forms

Declaration:

```js
function add(a, b) { return a + b; }
```

Expression:

```js
const add2 = function(a, b) { return a + b; };
```

Arrow function ✅:

```js
const add3 = (a, b) => a + b;
```

**Arrow caveat:** no own `this`, no `arguments`, can’t be used with `new`.

---

### Section 1.8.2: Default Params, Rest, Spread

```js
function greet(name = "world") {
  return `Hi ${name}`;
}

function sum(...nums) {
  return nums.reduce((a,b)=>a+b, 0);
}

const arr = [1,2,3];
const arr2 = [...arr, 4];

const obj = {a:1};
const obj2 = {...obj, b:2};
```

---

### Section 1.8.3: Callbacks and Higher-Order Functions

```js
const nums = [1,2,3];
const doubled = nums.map(n => n*2);
```

---

### Section 1.8.4: Closures

**Theory**  
A closure is when a function “remembers” variables from its creation scope.

```js
function makeCounter() {
  let count = 0;
  return () => ++count;
}

const c = makeCounter();
c(); // 1
c(); // 2
```

**Why it matters**  
Closures power encapsulation, factories, and async patterns.

---

**Mini-exercises (Part 1)**
1. Write a function that returns another function to multiply by `n`.
2. Implement `once(fn)` that allows a function to be called only once.
3. Convert a function declaration to arrow form without changing behavior.

---

# Part 2: Data Structures & Built-ins

---

## Chapter 2.1: Arrays

### Section 2.1.1: Core Ideas

**Theory**  
Arrays are ordered, 0-indexed lists. JS arrays are dynamic and can hold mixed types.

```js
const xs = [1, "two", true];
xs.length;   // 3
xs[0];       // 1
```

---

### Section 2.1.2: Common Methods

```js
xs.push(4); xs.pop();
xs.shift(); xs.unshift(0);

xs.map(x => x);
xs.filter(x => x);
xs.reduce((a,b)=>a+b, 0);
xs.find(x => x > 2);
xs.includes(2);
```

---

### Section 2.1.3: Modern Array Methods

**Copy-by-change methods** ✅ (ES2023)  
These return new arrays instead of mutating:

```js
const a = [3,1,2];

a.toSorted();     // [1,2,3]
a.toReversed();   // [2,1,3]
a.toSpliced(1,1); // removes index 1 in a copy
a.with(0, 99);    // [99,1,2]
```

`findLast` / `findLastIndex` ✅ (ES2023)

```js
[1,2,3,4].findLast(n => n%2===0); // 4
```

`.at()` ✅

```js
a.at(-1); // last element
```

---

### Section 2.1.4: Destructuring

```js
const [first, , third] = [10,20,30];
const [a1=1, b1=2] = [];
```

---

## Chapter 2.2: Objects

### Section 2.2.1: Properties and Access

**Theory**  
Objects store key-value pairs. Keys are strings or symbols.

```js
const user = { name: "A", age: 30 };
user.name;
user["age"];
```

Computed keys ✅:

```js
const key = "likesJS";
const o = { [key]: true };
```

---

### Section 2.2.2: Destructuring and Defaults

```js
const { name, city="Unknown" } = user;
```

---

### Section 2.2.3: Immutability Patterns

**Theory**  
To avoid bugs, especially in async/stateful code, prefer copying:

```js
const u2 = { ...user, age: 31 };
```

Deep copy ✅:

```js
const copy = structuredClone(user);
```

---

### Section 2.2.4: Prototypes (preview to Part 3)

Every object has a prototype; properties not found on the object are looked up there.

---

## Chapter 2.3: Map / Set / WeakMap / WeakSet

### Section 2.3.1: Map

**Theory**  
Map supports any key type and preserves insertion order.

```js
const m = new Map();
m.set("a", 1);
m.set({x:1}, 2);
m.get("a"); // 1
```

---

### Section 2.3.2: Set

**Theory**  
Set stores unique values.

```js
const s = new Set([1,2,2,3]);
[...s]; // [1,2,3]
```

---

### Section 2.3.3: WeakMap / WeakSet

**Theory**  
They hold **weak references** to object keys/values which can be GC’d, useful for caching without leaks.

```js
const wm = new WeakMap();
const obj = {};
wm.set(obj, "meta");
```

---

## Chapter 2.4: JSON

```js
const str = JSON.stringify({a:1});
const obj = JSON.parse(str);
```

**Theory**  
JSON is a data exchange format, not a JS object. It forbids functions, `undefined`, and symbols.

---

## Chapter 2.5: Date & Time + Temporal

**Theory**  
`Date` is legacy and mutable. It represents an instant in milliseconds since epoch.

```js
const d = new Date();
d.toISOString();
```

**Temporal** 🧭  
Temporal is a TC39 proposal aimed to fix Date’s issues (time zones, immutability).

---

## Chapter 2.6: Intl APIs

**Theory**  
Built-in internationalization utilities.

```js
new Intl.NumberFormat("en-IN").format(1234567.89);
new Intl.DateTimeFormat("en-GB", { dateStyle: "long" }).format(new Date());
new Intl.Collator("de").compare("ä", "z");
```

---

**Mini-exercises (Part 2)**
1. Given orders with `{category, amount}`, group by category using `Object.groupBy` (Part 6).
2. Write a function that returns a new sorted array without mutating input.
3. Use Map to count word frequencies.

---

# Part 3: Deep JavaScript

---

## Chapter 3.1: Execution Model

### Section 3.1.1: Call Stack, Heap, Event Loop

**Theory**  
- **Call stack:** tracks function calls (LIFO).
- **Heap:** stores objects.
- **Event loop:** runs tasks when stack is empty.

**Event loop diagram (ASCII)**

```
┌─────────────┐
│ Call Stack  │ ← sync code runs here
└─────┬───────┘
      │ empty?
      v
┌─────────────┐
│ Microtasks  │ ← promises/queueMicrotask
└─────┬───────┘
      v
┌─────────────┐
│ Macrotasks  │ ← timers, IO, UI events
└─────────────┘
      |
      v
 repeat
```

Microtasks always run **before** the next macrotask.

```js
console.log("A");
setTimeout(()=>console.log("B"), 0);
Promise.resolve().then(()=>console.log("C"));
console.log("D");
// A D C B
```

---

## Chapter 3.2: Prototypes & Inheritance

**Theory**  
JS uses **prototype-based inheritance**. Objects delegate to prototypes.

```js
const animal = { eats: true };
const dog = Object.create(animal);
dog.barks = true;

dog.eats; // true (from prototype)
```

**Prototype chain diagram (ASCII)**

```
dog --> animal --> Object.prototype --> null
```

---

## Chapter 3.3: Classes (Syntax over Prototypes)

**Theory**  
`class` is modern syntax that still uses prototypes.

```js
class Person {
  #secret = "shh";         // private field ✅
  constructor(name) { this.name = name; }
  greet() { return `Hi ${this.name}`; }
  static species() { return "Homo sapiens"; }
  get upper() { return this.name.toUpperCase(); }
  set upper(v) { this.name = v.toLowerCase(); }
}

class Employee extends Person {
  constructor(name, role) {
    super(name);
    this.role = role;
  }
}
```

---

## Chapter 3.4: Modules

### Section 3.4.1: ESM

```js
export const x = 1;
export default function f(){}
import f, { x } from "./m.js";
```

### Section 3.4.2: Dynamic Import ✅

```js
const mod = await import("./m.js");
```

### Section 3.4.3: ESM vs CJS

**Theory**  
ESM is static and analyzable; CJS is runtime/imperative.

---

## Chapter 3.5: Iterators & Generators

**Theory**  
An **iterable** has `[Symbol.iterator]`.

```js
for (const x of [1,2,3]) {}
```

Custom iterator:

```js
const range = {
  start: 1, end: 3,
  [Symbol.iterator]() {
    let cur = this.start;
    return {
      next: () =>
        cur <= this.end
          ? { value: cur++, done: false }
          : { done: true }
    };
  }
};
[...range]; // [1,2,3]
```

Generators ✅:

```js
function* gen() {
  yield 1; yield 2;
}
```

Async generators ✅:

```js
async function* chunks(stream) {
  for await (const c of stream) yield c;
}
```

---

## Chapter 3.6: Error Handling

**Theory**  
Errors are objects. `try/catch` handles runtime failures.

```js
try {
  risky();
} catch (e) {
  console.error(e.message);
} finally {
  cleanup();
}

class ValidationError extends Error {}
throw new ValidationError("Bad input");
```

---

## Chapter 3.7: Memory & GC Basics

**Theory**  
JS runtimes automatically garbage collect unreachable objects. Common leak patterns:
- Long-lived globals holding large data
- Detached DOM nodes retained in closures
- Unbounded caches/maps

---

**Mini-exercises (Part 3)**
1. Build a custom iterable `range(n)`.
2. Create a `class Stack` using private fields.
3. Explain output order of a mixed Promise/timeout snippet.

---

# Part 4: Asynchronous JavaScript

---

## Chapter 4.1: Callbacks → Promises → async/await

**Theory**  
Async evolved:

1. **Callbacks:** nested, error-prone
2. **Promises:** chainable, standard
3. **async/await:** readable sync-style

Callback:

```js
fs.readFile("a.txt", (err, data) => {});
```

Promise ✅:

```js
fetch("/api")
  .then(r => r.json())
  .catch(console.error);
```

async/await ✅:

```js
async function load() {
  const r = await fetch("/api");
  return r.json();
}
```

---

## Chapter 4.2: Promise Combinators

| Method | Behavior |
|---|---|
| `Promise.all` | fails fast, waits all |
| `Promise.allSettled` | never fails, returns status |
| `Promise.race` | settles first |
| `Promise.any` | first fulfilled, ignores rejects |

```js
await Promise.all([p1, p2]);
await Promise.any([p1, p2]);
```

---

## Chapter 4.3: async iteration

```js
for await (const line of lines(url)) {
  console.log(line);
}
```

---

## Chapter 4.4: Top-level await ✅

Only in ESM:

```js
const r = await fetch("/api");
```

---

## Chapter 4.5: AbortController & Cancellation

**Theory**  
Some async ops support cancellation using signals.

```js
const ac = new AbortController();
const p = fetch("/api", { signal: ac.signal });
ac.abort(); // cancels
```

---

**Mini-exercises (Part 4)**
1. Load two APIs in parallel and handle partial failure.
2. Implement a timeout wrapper using `AbortController`.

---

# Part 5: Browser + Node Essentials

---

## Chapter 5.1: DOM Basics

**Theory**  
DOM is the browser’s in-memory tree representation of HTML.

Querying:

```js
const el = document.querySelector("#btn");
```

Events:

```js
el.addEventListener("click", e => console.log("clicked"));
```

Bubbling/capturing:

```js
parent.addEventListener("click", () => console.log("bubble"));
parent.addEventListener("click", () => console.log("capture"), true);
```

---

## Chapter 5.2: Fetch API ✅

```js
const r = await fetch("/users");
const users = await r.json();
```

---

## Chapter 5.3: Storage

**Theory**
- `localStorage`: persistent key/value string store.
- `sessionStorage`: per-tab session store.
- Cookies: sent with requests, size-limited.

```js
localStorage.setItem("theme", "dark");
```

---

## Chapter 5.4: Node.js Essentials

**fs/promises**:

```js
import { readFile } from "node:fs/promises";
const txt = await readFile("a.txt", "utf8");
```

**path**:

```js
import path from "node:path";
path.join(process.cwd(), "data", "a.txt");
```

**events**:

```js
import { EventEmitter } from "node:events";
const em = new EventEmitter();
em.on("done", () => console.log("done"));
em.emit("done");
```

**streams (overview)**  
Streams are lazy data flows; used for files, HTTP, large payloads.

---

## Chapter 5.5: CLI Basics with Node

```js
#!/usr/bin/env node
console.log(process.argv.slice(2));
```

Run:

```bash
chmod +x tool.js
./tool.js hello
```

---

**Mini-exercises (Part 5)**
1. Build a tiny CLI that reads a file and prints line count.
2. Add a click handler that toggles a CSS class.

---

# Part 6: Modern ES Features Cheat Sheet

---

## Chapter 6.1: ES2015+ Highlights

- `let`, `const`
- Arrow functions
- Template literals
- Destructuring
- Default params, rest/spread
- Classes + private fields
- Modules
- Promises, async/await, top-level await
- `Map` / `Set`, weak collections
- Optional chaining, nullish coalescing
- `BigInt`
- Numeric separators
- `replaceAll`
- `Promise.any`, `allSettled`
- `structuredClone`
- Copy-by-change arrays (`toSorted`, `with`, etc.)

---

## Chapter 6.2: Recent Spec Features (ES2024–ES2025)

- `Object.groupBy`, `Map.groupBy`
- `Promise.withResolvers`
- New `Set` operations
- Iterator helpers / `Iterator.from`
- `Promise.try`
- `RegExp.escape`
- `Float16Array`

Example:

```js
const grouped = Object.groupBy(
  ["a","bb","c"],
  s => s.length
);
// { 1: ["a","c"], 2: ["bb"] }
```

---

## Chapter 6.3: TC39 Proposals Worth Watching 🧭

- Decorators
- Pattern Matching
- Temporal
- Pipeline operator
- Import Attributes

---

# Part 7: Ecosystem & Best Practices

---

## Chapter 7.1: npm Basics

```json
{
  "type": "module",
  "scripts": {
    "dev": "node index.js",
    "test": "vitest",
    "lint": "eslint ."
  }
}
```

---

## Chapter 7.2: ESLint + Prettier

**Theory**  
- ESLint catches bugs and enforces rules.
- Prettier ensures consistent formatting.

---

## Chapter 7.3: Testing Tools

- Jest / Vitest (unit)
- Playwright / Cypress (E2E)

```js
import { test, expect } from "vitest";
test("add", () => expect(1+2).toBe(3));
```

---

## Chapter 7.4: TypeScript Overview

**Theory**  
TypeScript adds static types while compiling to JS. Use it for larger or long-lived projects.

---

## Chapter 7.5: Recommended Project Structure

```
src/
  index.js
  lib/
  routes/
test/
package.json
eslint.config.js
```

---

**Mini-exercises (Part 7)**
1. Set up ESLint + Prettier.
2. Write unit tests for a small utility module.

---

# Final Notes

You now have a full-spectrum JavaScript foundation with core mechanics and modern ES2025 features. Prefer modern patterns (`const`, ESM, async/await, immutable array methods), and verify proposal/runtime support before using stage features in production.
