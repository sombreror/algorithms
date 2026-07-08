# Sliding Window

La **Sliding Window** è una tecnica algoritmica utilizzata per risolvere problemi che coinvolgono **intervalli continui** (subarray o substring) di un array o di una stringa.

L'idea consiste nel mantenere una **finestra**, delimitata da due puntatori (`left` e `right`), che rappresenta un intervallo continuo della struttura dati.

---

## Tipi di Sliding Window

### Fixed Sliding Window

La finestra ha una dimensione fissa `k`.

Esempio (`k = 3`):

```text
[2, 1, 5] 1 3 2
```

↓

```text
2 [1, 5, 1] 3 2
```

↓

```text
2 1 [5, 1, 3] 2
```

Ad ogni spostamento:

- entra un nuovo elemento nella finestra;
- esce l'elemento più a sinistra;
- la dimensione della finestra rimane sempre `k`.

---

### Variable Sliding Window

La finestra non ha una dimensione fissa.

Può:
- espandersi (`right++`);
- restringersi (`left++`);

finché viene soddisfatta una determinata condizione.

---

# Obiettivo della Sliding Window

La Sliding Window **non evita di scorrere l'array** (che viene comunque visitato una sola volta).

Il suo scopo è **evitare di ricalcolare ogni volta le informazioni della finestra**.

Ad esempio, per trovare la somma massima di `k` elementi consecutivi, invece di risommare tutti gli elementi ad ogni spostamento, basta aggiornare la somma:

```text
somma = somma
      - elemento che esce
      + elemento che entra
```

Grazie a questa tecnica, molti algoritmi passano da **O(n × k)** a **O(n)**.

---

# Quando usare Sliding Window

La Sliding Window è spesso la soluzione giusta quando il problema parla di:

- subarray
- substring
- elementi consecutivi
- intervalli continui
- finestra di dimensione `k`
- somma massima/minima
- lunghezza massima/minima

---

# Schema generale

## Fixed Sliding Window

```javascript
// Costruisci la prima finestra

// Fai scorrere la finestra
entra un elemento
esce un elemento

// Aggiorna la risposta
```

## Variable Sliding Window

```javascript
let left = 0;

for (let right = 0; right < nums.length; right++) {

    // Espandi la finestra

    while (/* finestra non valida */) {

        // Restringi la finestra
        left++;
    }

    // Aggiorna la risposta
}
```

---

# Complessità

- **Tempo:** `O(n)`
- **Memoria:** `O(1)` (oppure `O(k)` se si utilizza una HashMap o un Set)


