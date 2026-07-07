<div align="center">

# Algorithms — Visual Notes

### *Algorithms are understood with your eyes, not memorized.*

[![Obsidian](https://img.shields.io/badge/Obsidian-Vault-7C3AED?style=for-the-badge&logo=obsidian&logoColor=white)](https://obsidian.md)
[![Excalidraw](https://img.shields.io/badge/Excalidraw-Drawings-6965DB?style=for-the-badge&logo=excalidraw&logoColor=white)](https://excalidraw.com)
[![LeetCode](https://img.shields.io/badge/Practice-LeetCode%20Solutions-FFA116?style=for-the-badge&logo=leetcode&logoColor=white)](https://github.com/sombreror/leetcode)

[![Last commit](https://img.shields.io/github/last-commit/sombreror/algorithms?style=for-the-badge&color=10B981&label=Last%20commit)](https://github.com/sombreror/algorithms/commits/main)
[![Commit activity](https://img.shields.io/github/commit-activity/m/sombreror/algorithms?style=for-the-badge&color=3B82F6&label=Commits%2Fmonth)](https://github.com/sombreror/algorithms/graphs/commit-activity)
[![Status](https://img.shields.io/badge/Status-Growing-F59E0B?style=for-the-badge)](#pattern-index)

</div>

---

## What is this repository

A collection of **visual notes on the most important algorithmic patterns**, hand-drawn with **Excalidraw** inside an **Obsidian** vault.

Every pattern gets its own folder containing:

| Content | Description |
|:--------|:------------|
| **Drawing** | The visual scheme of the pattern, drawn step by step |
| **Excalidraw note** | The source file, editable directly in Obsidian |
| **README** | The full write-up: how it works, code template, complexity, and classic problems |

> [!TIP]
> **Why visual?** An algorithmic pattern is not a formula to memorize — it is a *movement*. Watching pointers slide, windows glide, and trees split makes the concept impossible to forget.

---

## Pattern Index

| # | Pattern | Difficulty | Status |
|:-:|:--------|:----------:|:------:|
| 1 | **[Two Pointers](Two%20Pointers/README.md)** | 🟢 Easy | Done |
| 2 | Sliding Window | 🟢 Easy | Planned |
| 3 | Binary Search | 🟡 Medium | Planned |
| 4 | Fast & Slow Pointers | 🟡 Medium | Planned |
| 5 | BFS / DFS | 🟡 Medium | Planned |
| 6 | Dynamic Programming | 🔴 Hard | Planned |

> [!NOTE]
> This repository grows over time: every new pattern gets **drawn first**, then **explained**.
> The *Last commit* badge above always shows how fresh these notes are.

---

## Theory + Practice

This repo is the **theory**; the **practice** lives in the twin repo **[sombreror/leetcode](https://github.com/sombreror/leetcode)**, where every problem has its own write-up and a runnable JavaScript solution.

```mermaid
graph LR
    A["algorithms<br/>(patterns drawn & explained)"] <--> B["leetcode<br/>(problem solutions, in JS)"]

    style A fill:#EDE9FE,stroke:#8B5CF6,color:#4C1D95
    style B fill:#FEF3C7,stroke:#F59E0B,color:#78350F
```

Inside each pattern README, the problems table links straight to **my actual solution** whenever one exists: study the pattern here, then go see how it was applied for real.

---

## How to use these notes

### From GitHub (read-only)
Browse the folders: every README shows the drawing and the full write-up. Nothing to install.

### From Obsidian (editable)
1. Clone the repository:
   ```bash
   git clone https://github.com/sombreror/algorithms.git
   ```
2. Open the folder as a **vault** in [Obsidian](https://obsidian.md)
3. Install the **Excalidraw** plugin (already configured in `.obsidian/`)
4. Open a note and switch to *Excalidraw View* to edit the drawings

---

## Philosophy

```mermaid
graph LR
    A["Problem"] --> B["Draw the pattern"]
    B --> C["Understand the movement"]
    C --> D["Write the template"]
    D --> E["Solve any variant"]

    style A fill:#FEE2E2,stroke:#EF4444,color:#7F1D1D
    style B fill:#FEF3C7,stroke:#F59E0B,color:#78350F
    style C fill:#DBEAFE,stroke:#3B82F6,color:#1E3A8A
    style D fill:#EDE9FE,stroke:#8B5CF6,color:#4C1D95
    style E fill:#D1FAE5,stroke:#10B981,color:#064E3B
```

---

<div align="center">

**Notes by [sombreror](https://github.com/sombreror)**

*If these notes help you, leave a star.*

</div>
