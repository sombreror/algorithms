# Two Pointers

La tecnica dei **Two Pointers** consiste nell'usare **due indici** (`left` e `right`) che scorrono lo stesso array, invece di confrontare ogni elemento con tutti gli altri con due cicli annidati.

Nella variante classica (quella del disegno):

- `left` parte dal **primo** elemento e **aumenta** (`left++`);
- `right` parte dall'**ultimo** elemento e **diminuisce** (`right--`);
- ad ogni giro si controllano le **condizioni** del problema e si decide *quale* dei due puntatori muovere.

---

## Perché funziona

Ogni elemento viene visitato **al massimo una volta**: i puntatori si muovono solo l'uno verso l'altro, mai indietro. Quindi il costo è **O(n)** invece di **O(n²)** della forza bruta.

Quando `left` e `right` **si incontrano**, vuol dire che tutti gli elementi dell'array sono stati controllati: è esattamente il punto in cui si ferma il `while`.

---

## Lo schema

```javascript
let left = 0;
let right = array.length - 1;

while (left < right) {

    if (/* condizione: avanza da sinistra */) {
        left++;
        continue;
    }

    if (/* condizione: arretra da destra */) {
        right--;
        continue;
    }

    // qui left e right soddisfano quello che cerchiamo
}
```

La tecnica migliore è il `while (left < right)`, non un `for`: si ferma da solo **esattamente** nel punto d'incontro, senza dover calcolare prima quante iterazioni servono.

---

## Attenzione

- Per i problemi di somma (es. Two Sum II) l'array deve essere **ordinato**: muovere `left++` o `right--` è un ragionamento ("la somma è troppo piccola, mi serve un numero più grande") che vale solo se l'ordine è garantito.
- Se l'array non è ordinato: o lo ordini prima, o usi una **HashMap** (vedi Two Sum).
