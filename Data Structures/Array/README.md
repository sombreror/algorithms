<div align="center">

# Array

### *One block of memory, one index, instant access.*

[![Access](https://img.shields.io/badge/Access-O(1)-3B82F6?style=for-the-badge)](#complexity)
[![Search](https://img.shields.io/badge/Search-O(n)-F59E0B?style=for-the-badge)](#complexity)
[![Category](https://img.shields.io/badge/Category-Fundamentals-8B5CF6?style=for-the-badge)](#)

</div>

---

## The idea in one sentence

An array is a sequence of elements stored in **contiguous memory**: since every cell has the same size, the position of element `i` can be **computed directly** — no searching needed.

```text
address of arr[i]  =  start address  +  i × (size of one element)
```

That single multiplication is why `arr[i]` costs **O(1)**: the computer jumps straight to the cell.

---

## How it lives in memory

```text
 index:      0     1     2     3     4
           ┌─────┬─────┬─────┬─────┬─────┐
 arr:      │  7  │  2  │  9  │  4  │  1  │
           └─────┴─────┴─────┴─────┴─────┘
 address:  1000  1004  1008  1012  1016      (4 bytes per element)
```

- **Contiguous**: the cells sit one after another, with no gaps.
- **Indexed**: `arr[3]` = jump to `1000 + 3 × 4 = 1012`. Done.
- **The price**: to keep the block contiguous, inserting or removing *in the middle* forces every element after it to **shift**.

```text
 insert 5 at index 1 → everything after shifts right (O(n))

           ┌─────┬─────┬─────┬─────┬─────┬─────┐
           │  7  │ ⮕5  │  2  │  9  │  4  │  1  │
           └─────┴─────┴─────┴─────┴─────┴─────┘
                    └──── 4 elements moved ────┘
```

---

## Static vs dynamic arrays

| | Static array | Dynamic array (JS `[]`, Python `list`, …) |
|:--|:--|:--|
| **Size** | Fixed at creation | Grows automatically |
| **How it grows** | It doesn't | When full, allocates a **bigger block** (usually ×2) and copies everything |
| **`push` cost** | — | `O(1)` *amortized*: the occasional O(n) copy is spread over many cheap pushes |

> [!NOTE]
> JavaScript arrays are dynamic arrays managed by the engine. You never see the resize, but it's there — that's why `push` is *amortized* O(1), not always O(1).

---

## Complexity

| Operation | Cost | Why |
|:----------|:----:|:----|
| **Access** `arr[i]` | `O(1)` | Address computed directly |
| **Update** `arr[i] = x` | `O(1)` | Same jump, then write |
| **Search** (unsorted) | `O(n)` | Must look at every element |
| **Search** (sorted) | `O(log n)` | Binary Search |
| **Insert/remove at the end** | `O(1)`* | Nothing shifts (*amortized for dynamic arrays) |
| **Insert/remove at start/middle** | `O(n)` | Everything after must shift |

### In JavaScript

| Method | Cost | Note |
|:-------|:----:|:-----|
| `push` / `pop` | `O(1)` | End of the array: cheap |
| `shift` / `unshift` | `O(n)` | Start of the array: everything shifts |
| `slice` | `O(n)` | Copies a portion |
| `splice` | `O(n)` | Insert/remove in the middle + shift |
| `includes` / `indexOf` | `O(n)` | Linear search |

> [!TIP]
> If you find yourself calling `shift`/`unshift` in a loop, stop: that's `O(n²)`. Use an index (pointer) that moves forward instead — that is exactly the intuition behind [Two Pointers](../../Algorithms/Two%20Pointers/README.md).

---

## Strengths and weaknesses

**Arrays shine when:**

- you access elements **by position** (`arr[i]`)
- you iterate **in order**
- you mostly add/remove **at the end**
- the data is **sorted** → Binary Search, Two Pointers

**Arrays hurt when:**

- you insert/remove **in the middle or at the start** often → consider a linked list or a different approach
- you keep asking *"have I already seen this value?"* → that's an `O(n)` search per query: use a [Hash Map](../Hash%20Map/README.md) instead

---

## Patterns built on arrays

| Pattern | What it exploits |
|:--------|:-----------------|
| [Two Pointers](../../Algorithms/Two%20Pointers/README.md) | O(1) access from both ends |
| [Sliding Window](../../Algorithms/Sliding%20Window/README.md) | Contiguity: windows are subarrays |
| Binary Search | O(1) access + sorted order |

---

## Classic problems to practice

Solutions live in the twin repo [sombreror/leetcode](https://github.com/sombreror/leetcode).

| Problem | Difficulty | Idea | Solution |
|:--------|:----------:|:-----|:--------:|
| [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) | 🟢 Easy | One pass, track the minimum so far | [0121](https://github.com/sombreror/leetcode/tree/main/solutions/0121-best-time-to-buy-and-sell-stock) |
| [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/) | 🟢 Easy | Array alone costs O(n²) or O(n log n) — a Set makes it O(n) | [0217](https://github.com/sombreror/leetcode/tree/main/solutions/0217-contains-duplicate) |
| [Two Sum](https://leetcode.com/problems/two-sum/) | 🟢 Easy | Brute force on the array is O(n²) — a Hash Map makes it O(n) | [0001](https://github.com/sombreror/leetcode/tree/main/solutions/0001-two-sum) |

---

<div align="center">

**[← Back to the index](../../README.md)**

</div>
