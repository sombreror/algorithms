<div align="center">

# Hash Map

### *Trade a little memory for instant answers.*

[![Lookup](https://img.shields.io/badge/Lookup-O(1)%20avg-3B82F6?style=for-the-badge)](#complexity)
[![Insert](https://img.shields.io/badge/Insert-O(1)%20avg-22C55E?style=for-the-badge)](#complexity)
[![Category](https://img.shields.io/badge/Category-Fundamentals-8B5CF6?style=for-the-badge)](#)

</div>

---

## The idea in one sentence

A hash map stores **key → value** pairs and answers *"what is the value for this key?"* in **O(1)** on average: a **hash function** converts the key into an array index, so the lookup becomes a direct jump — no scanning.

```text
key ──▶ hash(key) ──▶ index ──▶ arr[index] = value
```

> [!IMPORTANT]
> A hash map is not magic: **underneath there is still an array**. The hash function is just a way to compute *where in the array* a key belongs, so we inherit the array's O(1) access.

---

## How it works

```text
                 hash("ciao") % 5 = 3

 buckets:    0         1         2         3         4
           ┌───────┬─────────┬───────┬────────────┬───────┐
           │       │ "b"→ 7  │       │ "ciao"→ 42 │       │
           └───────┴─────────┴───────┴────────────┴───────┘
```

1. **Hash**: the key is turned into a number (`hash("ciao")`).
2. **Index**: the number is mapped onto a bucket of the internal array (`% capacity`).
3. **Store / read**: the pair lives in that bucket.

### Collisions

Two different keys can land on the same bucket. The common fix is **chaining**: each bucket holds a small list.

```text
           ┌────────────────────┐
 bucket 3: │ "ciao"→42 → "oro"→9│     two keys, same bucket
           └────────────────────┘
```

- With a good hash function, chains stay tiny → operations stay **O(1) on average**.
- Worst case (everything collides): **O(n)**. In practice it doesn't happen with built-in maps.
- When the map gets too full it **resizes** (bigger array, everything re-hashed), just like a dynamic array.

---

## Complexity

| Operation | Average | Worst | Why |
|:----------|:-------:|:-----:|:----|
| **Insert** `map.set(k, v)` | `O(1)` | `O(n)` | Hash + jump (worst: long chain / resize) |
| **Lookup** `map.get(k)` | `O(1)` | `O(n)` | Hash + jump |
| **Delete** `map.delete(k)` | `O(1)` | `O(n)` | Hash + jump |
| **Contains** `map.has(k)` | `O(1)` | `O(n)` | Hash + jump |
| **Iterate all** | `O(n)` | `O(n)` | Must visit every bucket |

**Space:** `O(n)` — one slot per stored pair. This is the trade: **memory in exchange for speed**.

---

## In JavaScript

| | `Map` | plain object `{}` | `Set` |
|:--|:--|:--|:--|
| **Keys** | Any type | Strings / symbols only | — (values only) |
| **Size** | `map.size` | `Object.keys(obj).length` | `set.size` |
| **Use it for** | Key → value, any key | Quick literal lookups | *"Have I seen this?"* |

```javascript
// Map: key → value
const freq = new Map();
for (const ch of "hello") {
    freq.set(ch, (freq.get(ch) ?? 0) + 1);
}
// Map { h→1, e→1, l→2, o→1 }

// Set: membership only
const seen = new Set();
seen.add(5);
seen.has(5);  // true → O(1), no scanning
```

> [!TIP]
> A `Set` is just a hash map without values. Same engine, same O(1), half the API.

---

## When to use it

The hash map is the answer whenever a loop keeps asking a question about the past:

- *"Have I **already seen** this element?"* → `Set`
- *"**How many times** does each element appear?"* → frequency `Map`
- *"Does the **complement** (`target − x`) exist?"* → `Map` of value → index
- *"**Group** items that share a property"* → `Map` of property → list
- *"**Cache** a result I already computed"* → `Map` (memoization)

> [!NOTE]
> The classic upgrade: a nested loop that searches the array (`O(n²)`) becomes one loop plus O(1) lookups (`O(n)`). **Two Sum** is exactly this.

---

## Classic problems to practice

Solutions live in the twin repo [sombreror/leetcode](https://github.com/sombreror/leetcode): every link in the *Solution* column leads to the write-up + runnable JavaScript code.

| Problem | Difficulty | Idea | Solution |
|:--------|:----------:|:-----|:--------:|
| [Two Sum](https://leetcode.com/problems/two-sum/) | 🟢 Easy | Map value → index; look up `target − x` | [0001](https://github.com/sombreror/leetcode/tree/main/solutions/0001-two-sum) |
| [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/) | 🟢 Easy | Set of seen values | [0217](https://github.com/sombreror/leetcode/tree/main/solutions/0217-contains-duplicate) |
| [Valid Anagram](https://leetcode.com/problems/valid-anagram/) | 🟢 Easy | Compare character frequency maps | [0242](https://github.com/sombreror/leetcode/tree/main/solutions/0242-valid-anagram) |
| [Group Anagrams](https://leetcode.com/problems/group-anagrams/) | 🟡 Medium | Map sorted-word → list of anagrams | [0049](https://github.com/sombreror/leetcode/tree/main/solutions/0049-group-anagrams) |
| [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) | 🟡 Medium | Frequency map + bucket by count | [0347](https://github.com/sombreror/leetcode/tree/main/solutions/0347-top-k-frequent-elements) |

---

<div align="center">

**[← Back to the index](../../README.md)**

</div>
