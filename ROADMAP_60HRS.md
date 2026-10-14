# 🎯 60-Hour Pure JavaScript Deep Dive (MAANG & Big Tech)

A laser-focused, battle-tested preparation tracker dedicated exclusively to **Pure JavaScript Mastery**: Core Runtime Internals, Metaprogramming & Prototypes, Whiteboard Native Polyfills, and Advanced Async Concurrency.

*(DOM Manipulation, Machine Coding UI, and DSA have been excluded to maximize pure JS depth).*

> **Total Budget:** 60 Hours  
> **Progress:** 2.5 / 60 Hours Completed  
> **Status Legend:** `[ ]` Not Started | `[/]` In Progress | `[x]` Completed & Mastered

---

## 📊 Quick Progress Dashboard

| Module | Core Domain | Time Allocated | Status |
| :--- | :--- | :---: | :---: |
| **Module 1** | JS Runtime Internals, Mental Model & Output Tracing | 15 Hours | `[ ]` |
| **Module 2** | Object/Array Metaprogramming, Descriptors & Prototypes | 15 Hours | `[ ]` |
| **Module 3** | Native Polyfills From Scratch (A+ Spec & Edge Cases) | 15 Hours | `[ ]` |
| **Module 4** | Advanced Async Programming, Concurrency & Schedulers | 15 Hours | `[ ]` |
| **Total** | **Pure JavaScript Mastery** | **60 Hours** | **0%** |

---

## 🧠 Module 1: JS Runtime Internals, Mental Model & Output Tracing (15 Hours)
*Goal: Solve any complex "explain the output", scope resolution, hoisting, closure, or event-loop question with 100% precision.*

- [x] **1.1 Execution Context & Call Stack (2.5 hrs)**
  - [x] Global Execution Context (GEC) vs Function Execution Context (FEC)
  - [x] Creation Phase (variable object, scope chain, `this`) vs Execution Phase
  - [x] Call stack overflows, recursion limits, and stack trace analysis
- [ ] **1.2 Scope, Lexical Environment & Closures (3 hrs)**
  - [ ] Global, Module, Function, and Block Scopes (`var` vs `let` / `const`)
  - [ ] Lexical Environment, Environment Records, and Scope Chain lookup mechanics
  - [ ] Closures: Data privacy, factory functions, and the infamous loop closure bug (`var` vs `let` vs IIFE)
  - [ ] Stale closures in asynchronous handlers and long-lived callbacks
  - [ ] Accidental memory leaks: dangling closures, forgotten timers, and DOM references
- [ ] **1.3 Hoisting & Temporal Dead Zone (TDZ) (2 hrs)**
  - [ ] Function Declarations vs Function Expressions vs Arrow Functions hoisting rules
  - [ ] `var` undefined initialization vs `let`/`const`/`class` in TDZ
  - [ ] Edge-case drills: function vs variable naming conflicts, parameter scope vs function body scope
- [ ] **1.4 The `this` Keyword Masterclass (3 hrs)**
  - [ ] The 4 Call-site Rules: Default binding, Implicit binding, Explicit binding (`call`, `apply`, `bind`), `new` operator binding
  - [ ] Order of precedence among the 4 rules
  - [ ] Lexical `this` in Arrow Functions (why `call`/`apply`/`bind` can never rebind arrow function `this`)
  - [ ] `this` in `strict mode` vs non-strict mode
  - [ ] Method borrowing, lost context in callbacks, and self-referencing patterns
- [ ] **1.5 The Event Loop & Async Execution Order (3 hrs)**
  - [ ] V8 Call Stack, libuv / Browser Web APIs execution model
  - [ ] Microtask Queue: `Promise.then/catch/finally`, `queueMicrotask`, `MutationObserver`, `process.nextTick`
  - [ ] Macrotask Queue: `setTimeout`, `setInterval`, `setImmediate`, I/O
  - [ ] Microtask starvation / queue exhaustion vulnerabilities
  - [ ] Multi-layered tricky output puzzle drills combining all queues
- [ ] **1.6 Types, Coercion & Engine Internals (1.5 hrs)**
  - [ ] Primitives vs Objects, wrapper objects (`Number`, `String`, `Boolean`)
  - [ ] Type Coercion: `ToPrimitive` algorithm, `valueOf` vs `toString`, `+` operator dual nature
  - [ ] Equality algorithms: Abstract Equality (`==`), Strict Equality (`===`), `Object.is()` (handling `NaN`, `+0`, `-0`)
  - [ ] V8 under the hood: Hidden Classes (Shapes), Inline Caches (IC), Garbage Collection (Mark-and-Sweep, Young/Old generation)

---

## 🛠️ Module 2: Object/Array Metaprogramming, Descriptors & Prototypes (15 Hours)
*Goal: Master property descriptors, custom prototype extensions, immutability, and full metaprogramming with `Proxy` & `Reflect`.*

- [ ] **2.1 Property Descriptors & Method Extension (3 hrs)**
  - [ ] Data Descriptors: `value`, `writable`, `enumerable`, `configurable`
  - [ ] Accessor Descriptors: `get` and `set` (computed properties)
  - [ ] The Prototype Enumerability Trap: why `enumerable: false` is required when adding methods to `Array.prototype` / `Object.prototype`
  - [ ] Converting Data Descriptors to Accessor Descriptors (and configurable lock rules)
  - [ ] `Object.getOwnPropertyDescriptor(s)` & `Object.defineProperty / defineProperties`
- [ ] **2.2 Object Mutability & Integrity Levels (2.5 hrs)**
  - [ ] `Object.preventExtensions(obj)` vs `Object.seal(obj)` vs `Object.freeze(obj)` comparison matrix
  - [ ] Why `Object.freeze` is shallow by default
  - [ ] Implementing a production-grade `deepFreeze(obj)` handling circular references, nested objects, and symbols
- [ ] **2.3 Prototypes, Inheritance & Prototype Pollution (3.5 hrs)**
  - [ ] `Function.prototype` vs `Object.prototype` vs `__proto__` vs `[[Prototype]]`
  - [ ] Prototype chain traversal and property shadowing
  - [ ] `Object.create(proto, descriptors)` vs constructor functions vs ES6 `class extends`
  - [ ] Overriding constructor returns (returning primitives vs objects)
  - [ ] Prototype Pollution vulnerabilities: how malicious payloads pollute `Object.prototype`, and defense with `Object.create(null)` / `Map`
  - [ ] Safe property checking: `obj.hasOwnProperty` vs `Object.prototype.hasOwnProperty.call(obj, key)` vs `Object.hasOwn(obj, key)`
- [ ] **2.4 Metaprogramming with `Proxy` & `Reflect` (6 hrs)**
  - [ ] Understanding all 13 Proxy Traps (`get`, `set`, `has`, `deleteProperty`, `apply`, `construct`, `ownKeys`, etc.)
  - [ ] Why `Reflect` must be used inside Proxy traps (correct `receiver` binding)
  - [ ] **Hands-on Challenge 1:** Implement Python-style negative array indexing (`arr[-1]`, `arr[-2]`)
  - [ ] **Hands-on Challenge 2:** Safe navigation / Default dictionary proxy (no `TypeError: Cannot read properties of undefined`)
  - [ ] **Hands-on Challenge 3:** Complete mini Vue-3 reactivity engine (`reactive()`, `effect()`, dependency tracking)
  - [ ] Revocable proxies (`Proxy.revocable()`) for sandboxing and security

---

## ⚡ Module 3: Core Native Polyfills From Scratch (15 Hours)
*Goal: Write 100% bug-free, edge-case-resilient polyfills on a whiteboard or coderpad under interview pressure.*

- [ ] **3.1 Array Polyfills (3.5 hrs)**
  - [ ] `Array.prototype.myMap`: handling sparse arrays (holes) and `thisArg`
  - [ ] `Array.prototype.myFilter`: handling sparse arrays and `thisArg`
  - [ ] `Array.prototype.myReduce`: handling omitted initial value, empty array throw, sparse indices
  - [ ] `Array.prototype.myFlat(depth)`: recursive and iterative stack implementations
  - [ ] `Array.prototype.myFlatMap`
  - [ ] `Array.prototype.mySlice` & `mySplice`
- [ ] **3.2 Function Polyfills (3 hrs)**
  - [ ] `Function.prototype.myCall`: symbol keys to prevent collision, primitive context boxing
  - [ ] `Function.prototype.myApply`: handling array-like argument validation
  - [ ] `Function.prototype.myBind`: preserving prototype chain when invoked with `new` operator
  - [ ] `curry(fn)`: supporting arbitrary arguments and dynamic execution
  - [ ] `curryWithPlaceholder(fn)`: supporting placeholder values (`_`)
- [ ] **3.3 Promise & Async Polyfills (4.5 hrs)**
  - [ ] Custom `MyPromise` from scratch (A+ compliant: pending, fulfilled, rejected states, then chaining, microtask execution)
  - [ ] `Promise.myAll`: fail-fast on first rejection, non-promise values handling, empty array edge-case
  - [ ] `Promise.myAllSettled`: never rejects, returns structured status objects
  - [ ] `Promise.myRace`: first settled promise wins
  - [ ] `Promise.myAny`: first fulfilled promise wins, rejects with `AggregateError`
  - [ ] `promisify(nodeStyleCallbackFn)`
- [ ] **3.4 Fundamental Utility Polyfills (4 hrs)**
  - [ ] `debounce(fn, delay, { leading, trailing, maxWait })`
  - [ ] `throttle(fn, interval, { leading, trailing })`
  - [ ] `deepClone(obj)`: robust clone handling Primitives, Arrays, plain Objects, Date, RegExp, Map, Set, Symbol keys, and circular references
  - [ ] `deepEqual(a, b)`: structural equality comparison
  - [ ] `memoize(fn, resolver)`: caching with custom serializer and optional LRU eviction

---

## 🚦 Module 4: Advanced Async Programming, Concurrency & Schedulers (15 Hours)
*Goal: Ace the toughest async coding questions asked by Tier-1 infrastructure and frontend platform teams.*

- [ ] **4.1 Concurrency Pools & Schedulers (4 hrs)**
  - [ ] Concurrency limit task runner: execute $N$ asynchronous tasks with max $K$ in parallel
  - [ ] Priority-based async task queue (high priority tasks preempt or run first)
  - [ ] Sliding-window rate limiter (e.g., execute max $M$ operations per $S$ seconds)
- [ ] **4.2 Resilience, Cancellation & Retries (3.5 hrs)**
  - [ ] `retryWithBackoff(fn, { maxRetries, baseDelay, factor, jitter })`
  - [ ] Promise timeout wrapper (`withTimeout(promise, ms)`)
  - [ ] Cancellable promises using `AbortController` and custom cancellation tokens
  - [ ] Auto-cancelling stale in-flight requests (typeahead / search pattern)
- [ ] **4.3 Batching & Deduplication (3.5 hrs)**
  - [ ] In-flight request deduplication (returning identical active promise for duplicate calls)
  - [ ] Request batching window (mini DataLoader: aggregating single calls within same microtask tick into one batch request)
- [ ] **4.4 Iterators, Generators & Async Pipelines (4 hrs)**
  - [ ] Custom iterables with `[Symbol.iterator]()`
  - [ ] Generators (`function*`): yielding values, two-way communication (`gen.next(val)`), handling errors (`gen.throw()`)
  - [ ] Implementing `async/await` runner using generators and promises (`co` library pattern)
  - [ ] Async generators and `for await...of` (`[Symbol.asyncIterator]()`)
  - [ ] Asynchronous pipeline & waterfall execution (`asyncPipe(fn1, fn2, fn3)`)

---

## 📝 Practice Log & Session Notes

| Session # | Date | Hours Spent | Topic Covered | Key Learnings / Bugs Faced |
| :---: | :---: | :---: | :---: | :--- |
| #1 | 2026-10-14 | 2.5 hrs | **1.1 Execution Context & Call Stack** ([Notes](notes/module-1/1.1-execution-context-and-call-stack.md)) | Creation vs Execution phase, function vs var collision priority, dead-code hoisting, microtask queue starvation vs Trampoline pattern |
| #2 | | | | |
| #3 | | | | |
| #4 | | | | |

---

## 🏆 Definition of "Ready for MAANG" (Pure JS)
You are interview-ready when you can:
1. Explain every step of the V8 execution model, closures, and multi-layered event loop tasks without error.
2. Extend `Array.prototype` / `Object.prototype` cleanly using property descriptors without polluting `for..in` loops.
3. Write `Array.prototype.reduce`, `Promise.all`, `debounce`, `throttle`, and `deepClone` with zero bugs and full edge-case coverage on a blank screen in under 15 minutes each.
4. Implement async concurrency schedulers, retry with backoff, and generator runners cleanly under interview pressure.
