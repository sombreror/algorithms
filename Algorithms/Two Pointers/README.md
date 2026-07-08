<div align="center">

# Two Pointers

### *Two indices, one pass: the array has no secrets left.*

[![Difficulty](https://img.shields.io/badge/Difficulty-Easy-22C55E?style=for-the-badge)](#)
[![Time](https://img.shields.io/badge/Time-O(n)-3B82F6?style=for-the-badge)](#complexity)
[![Space](https://img.shields.io/badge/Space-O(1)-8B5CF6?style=for-the-badge)](#complexity)
[![Category](https://img.shields.io/badge/Category-Arrays%20%2F%20Strings-F59E0B?style=for-the-badge)](#)

</div>

---

## The drawing

![Visual scheme of the Two Pointers pattern](Two%20Pointers.png)

---

## The idea in one sentence

Instead of comparing every element against all the others (**O(n²)**), you use **two pointers** starting from opposite ends of the array, moving toward each other (**O(n)**).

```diff
+ LEFT  → starts on the left  and INCREASES (left++)
- RIGHT → starts on the right and DECREASES (right--)
```

> [!IMPORTANT]
> **When the two pointers meet, they have checked EVERY element of the array.**
> The meeting point is exactly where the `while` stops: it means the whole array has been scanned.

---

## How it works

```mermaid
graph TD
    A["left = 0, right = n - 1"] --> B{"left < right ?"}
    B -- "Yes" --> C{"Check the conditions"}
    C -- "need to advance from the left" --> D["left++"]
    C -- "need to retreat from the right" --> E["right--"]
    D --> B
    E --> B
    B -- "No — they met" --> F["Array 100% checked"]

    style A fill:#DBEAFE,stroke:#3B82F6,color:#1E3A8A
    style B fill:#FEF3C7,stroke:#F59E0B,color:#78350F
    style C fill:#FDE68A,stroke:#D97706,color:#78350F
    style D fill:#D1FAE5,stroke:#10B981,color:#064E3B
    style E fill:#FEE2E2,stroke:#EF4444,color:#7F1D1D
    style F fill:#EDE9FE,stroke:#8B5CF6,color:#4C1D95
```

1. **`left`** starts at the **first** element and moves right
2. **`right`** starts at the **last** element and moves left
3. On every iteration you check the problem's **conditions** and decide *which* pointer to move
4. When `left` and `right` meet, the loop ends: every element has been seen

> [!TIP]
> **The best technique is a `while`, not a `for`:** `while (left < right)` stops by itself *exactly* at the meeting point, with no need to precompute how many iterations are required.

---

## The template

```javascript
let left = 0;
let right = array.length - 1;

while (left < right) {

    if (/* condition: advance from the left */) {
        left++;
        continue;
    }

    if (/* condition: retreat from the right */) {
        right--;
        continue;
    }

    // here: left and right satisfy what we are looking for
    // → record the result, then move one (or both) pointers

} // end of while → left and right have met
```

Keep checking the conditions inside the loop to see whether they match what you are looking for, increasing `left` and decreasing `right` until they meet.

---

## Complexity

| Metric | Value | Why |
|:-------|:-----:|:----|
| **Time** | `O(n)` | Every element is visited **at most once**: the pointers only move toward each other |
| **Space** | `O(1)` | Only two variables are needed (`left`, `right`), no matter how big the array is |

> [!NOTE]
> Compared to brute force: two nested loops cost `O(n²)`. On an array of 1,000,000 elements that means **1,000,000,000,000 operations** versus **1,000,000**.

---

## When to use it

You recognize the pattern when the problem shows these clues:

- The input is a **sorted array** or a **string**
- You are looking for a **pair** of elements satisfying a condition (sum, distance, …)
- You need to compare elements at **opposite ends** (e.g. palindromes)
- The brute-force solution would be `O(n²)` with two nested loops

---

## Classic problems to practice

Solutions live in the twin repo [sombreror/leetcode](https://github.com/sombreror/leetcode): every link in the *Solution* column leads to the write-up + runnable JavaScript code.

| Problem | Difficulty | Idea | Solution |
|:--------|:----------:|:-----|:--------:|
| [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) | 🟢 Easy | Compare characters at both ends and squeeze toward the center | [0125](https://github.com/sombreror/leetcode/tree/main/solutions/0125-valid-palindrome) |
| [Two Sum II](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) | 🟢 Easy | Sum too small? `left++` • Too big? `right--` | [0167](https://github.com/sombreror/leetcode/tree/main/solutions/0167-two-sum-II) |
| [Container With Most Water](https://leetcode.com/problems/container-with-most-water/) | 🟡 Medium | Always move the pointer at the shorter height | [0011](https://github.com/sombreror/leetcode/tree/main/solutions/0011-container-with-most-water) |
| [3Sum](https://leetcode.com/problems/3sum/) | 🟡 Medium | Fix one element + two pointers on the rest | [0015](https://github.com/sombreror/leetcode/tree/main/solutions/0015-3sum) |
| [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/) | 🔴 Hard | Two pointers + max seen from each side | — |

---

<div align="center">

**[← Back to the pattern index](README.md)**

</div>
