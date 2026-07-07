<div align="center">

# Algorithms — Appunti Visuali

### *Gli algoritmi si capiscono con gli occhi, non a memoria.*

[![Obsidian](https://img.shields.io/badge/Obsidian-Vault-7C3AED?style=for-the-badge&logo=obsidian&logoColor=white)](https://obsidian.md)
[![Excalidraw](https://img.shields.io/badge/Excalidraw-Disegni-6965DB?style=for-the-badge&logo=excalidraw&logoColor=white)](https://excalidraw.com)
[![Lingua](https://img.shields.io/badge/Lingua-Italiano-009246?style=for-the-badge)](#)
[![Work in Progress](https://img.shields.io/badge/Status-In%20crescita-F59E0B?style=for-the-badge)](#-roadmap)
[![LeetCode](https://img.shields.io/badge/Pratica-LeetCode%20Solutions-FFA116?style=for-the-badge&logo=leetcode&logoColor=white)](https://github.com/sombreror/leetcode)

</div>

---

## Cos'è questo repository

Una raccolta di **appunti visuali sui pattern algoritmici** più importanti, disegnati a mano con **Excalidraw** dentro un vault **Obsidian**.

Ogni pattern ha la sua cartella con:

| Contenuto | Descrizione |
|:----------|:------------|
| **Disegno** | Lo schema visuale del pattern, disegnato passo passo |
| **Nota Excalidraw** | Il file sorgente, modificabile direttamente in Obsidian |
| **README** | La spiegazione completa: come funziona, template di codice, complessità e problemi classici |

> [!TIP]
> **Perché visuale?** Un pattern algoritmico non è una formula da imparare a memoria: è un *movimento*. Vedere i puntatori che si muovono, le finestre che scorrono, gli alberi che si dividono rende il concetto impossibile da dimenticare.

---

## Indice dei Pattern

| # | Pattern | Difficoltà | Stato |
|:-:|:--------|:----------:|:-----:|
| 1 | **[Two Pointers](Two%20Pointers/README.md)** | 🟢 Facile | Completo |
| 2 | Sliding Window | 🟢 Facile | In arrivo |
| 3 | Binary Search | 🟡 Media | In arrivo |
| 4 | Fast & Slow Pointers | 🟡 Media | In arrivo |
| 5 | BFS / DFS | 🟡 Media | In arrivo |
| 6 | Dynamic Programming | 🔴 Difficile | In arrivo |

> [!NOTE]
> Il repository cresce nel tempo: ogni nuovo pattern viene prima **disegnato**, poi **spiegato**.

---

## Teoria + Pratica

Questo repo è la **teoria**; la **pratica** vive nel repo gemello **[sombreror/leetcode](https://github.com/sombreror/leetcode)**, dove ogni problema ha il suo write-up e la soluzione JavaScript eseguibile.

```mermaid
graph LR
    A["algorithms<br/>(pattern disegnati e spiegati)"] <--> B["leetcode<br/>(soluzioni ai problemi, in JS)"]

    style A fill:#EDE9FE,stroke:#8B5CF6,color:#4C1D95
    style B fill:#FEF3C7,stroke:#F59E0B,color:#78350F
```

Nei README dei pattern, la tabella dei problemi rimanda direttamente alla **mia soluzione** quando esiste: studi il pattern qui, poi vai a vedere come l'ho applicato davvero.

---

## Come usare questi appunti

### Da GitHub (solo lettura)
Sfoglia le cartelle: ogni README mostra il disegno e la spiegazione completa. Non serve installare nulla.

### Da Obsidian (modifica)
1. Clona il repository:
   ```bash
   git clone https://github.com/sombreror/algorithms.git
   ```
2. Apri la cartella come **vault** in [Obsidian](https://obsidian.md)
3. Installa il plugin **Excalidraw** (già configurato in `.obsidian/`)
4. Apri una nota e passa alla *Excalidraw View* per modificare i disegni

---

## Filosofia

```mermaid
graph LR
    A["Problema"] --> B["Disegno il pattern"]
    B --> C["Capisco il movimento"]
    C --> D["Scrivo il template"]
    D --> E["Risolvo qualsiasi variante"]

    style A fill:#FEE2E2,stroke:#EF4444,color:#7F1D1D
    style B fill:#FEF3C7,stroke:#F59E0B,color:#78350F
    style C fill:#DBEAFE,stroke:#3B82F6,color:#1E3A8A
    style D fill:#EDE9FE,stroke:#8B5CF6,color:#4C1D95
    style E fill:#D1FAE5,stroke:#10B981,color:#064E3B
```

---

<div align="center">

**Appunti di [sombreror](https://github.com/sombreror)**

*Se questi appunti ti sono utili, lascia una stella.*

</div>
