# 📘 JavaScript Fundamentals Notes

---

# 🟢 Topic 1: Differences Between `var`, `let`, and `const`

`let` and `const` are block-scoped variable declarations introduced in
ES6.\
The main difference is about **reassignment**, not mutability of values.

---

## 🔹 `let`

- ✅ Can be reassigned\
- ✅ Block-scoped (`{ }`)\
- ❌ Cannot be redeclared in the same scope

👉 Use it when the value needs to change.

---

## 🔹 `const`

- ❌ Cannot be reassigned\
- ✅ Must be initialized at declaration\
- ✅ Block-scoped

---

### 📌 Important: Objects & Arrays with `const`

`const` prevents **reassignment**, not mutation.

```js
const arr = [1, 2, 3];
arr.push(4); // ✅ allowed
```

---

## 🔥 Key Differences

Feature let const

---

Reassignment ✅ Allowed ❌ Not allowed
Must initialize ❌ No ✅ Yes
Block scoped ✅ Yes ✅ Yes
Object mutation ✅ Yes ✅ Yes

---

## 🔥 `var` vs `let` in JavaScript

### 1️⃣ Scope (Biggest Difference)

- 🔹 `var` → Function Scoped\
- 🔹 `let` → Block Scoped

### Example:

```js
if (true) {
  var a = 10;
  let b = 20;
}

console.log(a); // ✅ 10
console.log(b); // ❌ ReferenceError
```

👉 `var` ignores block `{}`\
👉 `let` respects block `{}`

This is why `let` is safer.

---

# 🟢 Topic 2: Functions in JavaScript

## 🔥 What is a Function?

A function is a reusable block of code designed to perform a task.

```js
function greet() {
  console.log("Hello!");
}

greet(); // Hello
```

---

# 🧠 Types of Functions in JavaScript

## 1️⃣ Function Declaration

```js
function add(a, b) {
  return a + b;
}
```

✅ Hoisted (can call before declaration)

```js
console.log(add(2, 3)); // 5
```

---

## 2️⃣ Function Expression

Stored inside a variable.

```js
const multiply = function (a, b) {
  return a * b;
};
```

❌ Not hoisted like declarations.

```js
multiply(2, 3); // Works only AFTER declaration
```

---

## 3️⃣ Arrow Functions (ES6)

Shorter syntax.

```js
const subtract = (a, b) => {
  return a - b;
};
```

### Short Form (Implicit Return)

```js
const square = (n) => n * n;
```

---

## 🔥 Arrow Function vs Normal Function (Important Difference)

### `this` Behavior

**Arrow Functions:** - ❌ Do NOT have their own `this` - ✅ Inherit
`this` from parent scope

**Normal Functions:** - ✅ Have their own `this`

### Example:

```js
const user = {
  name: "Max",
  greet: function () {
    console.log(this.name);
  },
};
```

If you use arrow inside object:

```js
greet: () => {
  console.log(this.name); // ❌ undefined
};
```

⚠️ Very common interview trap.

---

## 4️⃣ Anonymous Functions

```js
setTimeout(function () {
  console.log("Hello");
}, 1000);
```

---

## 5️⃣ Callback Functions

```js
function greet(name, callback) {
  console.log("Hi " + name);
  callback();
}

greet("Lavanya", function () {
  console.log("Done!");
});
```

Important for: - `map` - `filter` - `reduce` - API calls - Event
handlers

---

## 6️⃣ Higher Order Functions

A function that: - Takes another function as argument\

- OR Returns a function

```js
function multiplier(factor) {
  return function (number) {
    return number * factor;
  };
}

const double = multiplier(2);
console.log(double(5)); // 10
```

🔥 This uses **closure**.

---

# 🟢 Topic 3: Arrays

Arrays are one of the most important data structures in JavaScript.\
An array is an ordered collection of values.

```js
const numbers = [1, 2, 3, 4];
```

---

## 📦 Arrays Can Store:

- Numbers\
- Strings\
- Objects\
- Functions\
- Even other arrays

```js
const mixed = [1, "hello", { name: "Max" }, [10, 20]];
```

---

## 📌 Accessing Elements

```js
const fruits = ["apple", "banana", "mango"];

console.log(fruits[0]); // apple
console.log(fruits.length); // 3
```

👉 Indexes start from `0`.

---

# 🔁 Important Array Methods

## 1️⃣ `push()` -- Add to end

```js
const arr = [1, 2];
arr.push(3); // [1, 2, 3]
```

---

## 2️⃣ `pop()` -- Remove from end

```js
arr.pop(); // removes last element
```

---

## 3️⃣ `shift()` -- Remove from start

```js
arr.shift();
```

---

## 4️⃣ `unshift()` -- Add to start

```js
arr.unshift(0);
```

---

# ✅ End of Notes
