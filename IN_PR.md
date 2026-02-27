# Topic 1: Differences between var, let and const :

Let and const are block-scoped variable declarations introduced in ES6.
The main difference is about reassignment, not mutability of values.

🔹 let
Can be reassigned
Block-scoped ({ })
Cannot be redeclared in the same scope
Use it when the value needs to change.

🔹 const
❌ Cannot be reassigned
✅ Must be initialized at declaration
Block-scoped

Important: Objects & Arrays with const
const prevents reassignment, not mutation.

const arr = [1, 2, 3];
arr.push(4); // ✅ allowed

🔥 Key Differences
Feature let const
Reassignment ✅ Allowed ❌ Not allowed
Must initialize ❌ No ✅ Yes
Block scoped ✅ Yes ✅ Yes
Object mutation ✅ Yes ✅ Yes

🔥 var vs let in JavaScript
1️⃣ Scope (Biggest Difference)
🔹 var → Function Scoped
🔹 let → Block Scoped
Example:
if (true) {
var a = 10;
let b = 20;
}

console.log(a); // ✅ 10
console.log(b); // ❌ ReferenceError

👉 var ignores block {}
👉 let respects block {}

This is why let is safer.

# Topic 2:

🔥 What is a Function?

A function is a reusable block of code designed to perform a task.
function greet() {
console.log("Hello!");
}
Call it :
greet(); //Hello

🧠 Types of Functions in JavaScript

1️⃣ Function Declaration:

function add(a, b) {
return a + b;
}

✅ Hoisted (can call before declaration)

console.log(add(2, 3)); // 5

2️⃣ Function Expression

Stored inside a variable.

const multiply = function(a, b) {
return a \* b;
};

❌ Not hoisted like declarations.

multiply(2, 3); // Works only AFTER declaration

3️⃣ Arrow Functions (ES6)

Shorter syntax.

const subtract = (a, b) => {
return a - b;
};

Short form (implicit return):

const square = n => n \* n;

🔥 Arrow Function vs Normal Function (Important Difference)
1️⃣ this behavior

Arrow functions:

❌ Do NOT have their own this

They inherit this from parent scope

Normal functions:

✅ Have their own this

Example:

const user = {
name: "Max",
greet: function() {
console.log(this.name);
}
};

If you use arrow inside object:

greet: () => {
console.log(this.name); // ❌ undefined
}

Very common interview trap.

4️⃣ Anonymous Functions
Functions without a name.

setTimeout(function() {
console.log("Hello");
}, 1000);

5️⃣ Callback Functions
A function passed into another function.

function greet(name, callback) {
console.log("Hi " + name);
callback();
}

greet("Lavanya", function() {
console.log("Done!");
});
Very important for:
map
filter
reduce
API calls
Event handler

6️⃣ Higher Order Functions

A function that:
Takes another function as argument OR
Returns a function

function multiplier(factor) {
return function(number) {
return number \* factor;
};
}

const double = multiplier(2);
console.log(double(5)); // 10
This uses closure 🔥

# TOPIC 3:Arrays

Arrays are one of the most important data structures in JavaScript.
An array is an ordered collection of values.

Example:

const numbers = [1, 2, 3, 4];

Arrays can store:
Numbers
Strings
Objects
Functions
Even other arrays
const mixed = [1, "hello", { name: "Max" }, [10, 20]];

📌 Accessing Elements
const fruits = ["apple", "banana", "mango"];

console.log(fruits[0]); // apple
console.log(fruits.length); // 3

Indexes start from 0.

🔁 Important Array Methods (Very Important for Interviews)
1️⃣ push() – Add to end
const arr = [1, 2];
arr.push(3); // [1, 2, 3]

2️⃣ pop() – Remove from end
arr.pop(); // removes last element

3️⃣ shift() – Remove from start
arr.shift();

4️⃣ unshift() – Add to start
arr.unshift(0);
