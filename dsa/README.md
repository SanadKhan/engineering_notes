# 1. Time Complexity (Definition)

Time complexity tells how runtime grows as input `n` grows.

Think:

- `n = input size`
- Ignore constants
- Focus on growth

Example:

```js
for(let i=0; i<n; i++) {   
	console.log(i);
}
```

Runs `n` times.

Time = **O(n)**

---

## Common complexities

| Complexity | Meaning                  |
| ---------- | ------------------------ |
| O(1)       | Constant                 |
| O(log n)   | Divide by half           |
| O(n)       | Linear                   |
| O(n log n) | Sorting / Divide-Conquer |
| O(n²)      | Nested loops             |
| O(2^n)     | Subsets/Choices          |
| O(n!)      | Permutations             |

---

# 2. Space Complexity (Definition)

Extra memory used excluding input.

Example:

```js
let sum = 0;
for(let i=0; i<n; i++) {    
	sum += arr[i];
}
```

Only one variable.

Space = **O(1)**

---

Example:

```js
let result = [];
for(let i=0; i<n; i++) {   
	result.push(arr[i]);
}
```

Stores `n` elements.

Space = **O(n)**


---
# How to Decode Time Complexity

## Rule 1: Count loops

Single loop:

```js
for(let i=0; i<n; i++)
```

→ O(n)

---

Nested loops:

```js
for(let i=0; i<n; i++) {   
	for(let j=0; j<n; j++) {}
}
```

→ O(n²)

---

But:

```js
for(let i=0; i<n; i++) {}
for(let j=0; j<n; j++) {}
```

Not nested.

→ O(n + n) = O(n)

---

## Rule 2: Watch input shrinking

```js
while(n > 1) {   
	n = Math.floor(n / 2);
}
```

Half each time.

→ O(log n)

---

Tricky:

```js
while(n > 1) {   
	n = Math.sqrt(n);
}
```

This reduces faster:

Sequence:

n → √n → √√n

Actually:

→ O(log log n)

---

## Rule 3: Recursive tree size

Example:

```js
function f(n){   
	if(n === 0) return;   
	f(n-1);
}
```

Depth = n

Time = O(n)

---

Example:

```js
function f(n){   
	if(n === 0) return;   
	f(n-1);   
	f(n-1);
}
```

Branches = 2

Depth = n

Time = O(2^n)

---

Formula:

```
(branches ^ depth)
```

---
# Tricky Time Complexity Examples

---

# Example 1

```js
for(let i=1; i<n; i*=2) {   
	console.log(i);
}
```

Sequence:

1 → 2 → 4 → 8

How many times?

`2^k = n`

k = log n

Answer:

O(log n)

---

Pattern:

```js
i *= k
i /= k
```

Always suspect log.

---

# Example 2

```js
for(let i=0; i<n; i++) {   
	for(let j=1; j<n; j*=2) {}
}
```

Outer = n

Inner = log n

Total:

O(n log n)

---

# Example 3

```js
for(let i=0; i<n; i++) {   
	for(let j=i; j<n; j++) {}
}
```

Work:

n + (n-1) + (n-2)...

Formula:

n(n+1)/2

= O(n²)

Triangular loops.

Common in:

- pair problems
- substrings

---

# Example 5 (Strings)

```js
for(let i=0; i<n; i++) {   
	str += arr[i];
}
```

Strings are immutable.

Each concatenation copies.

Actual:

O(n²)

Better:

```js
arr.join("")
```

O(n)