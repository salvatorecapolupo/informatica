### Micro-Esercizio 3: Condizioni e Logica Booleana

**Traccia:**
Dato il seguente frammento di codice C++, con quali valori di `a` e `b` la stringa **"Verificato"** *non* verrà stampata?

```
int a = 10;
int b = 5;

if (a > b && b != 10 || a == 0) {
    cout << "Verificato" << endl;
} else {
    cout << "Non Verificato" << endl;
}
```

**Svolgimento:**

La stringa "Verificato" viene stampata se la condizione booleana è **vera**. Per far sì che **non** venga stampata, la condizione deve essere **falsa**.

La condizione è: `(a > b && b != 10) || a == 0`

Analizziamo quando l'intera espressione è **FALSA**:

1.  L'operatore principale è **OR** (`||`). Un'espressione OR è falsa solo se *entrambi* i suoi lati sono falsi.

      * Lato Sinistro: `(a > b && b != 10)` deve essere **FALSO**.
      * Lato Destro: `a == 0` deve essere **FALSO**.

2.  Affinché `a == 0` sia **FALSO**, `a` deve essere **qualsiasi numero diverso da 0**.

      * Condizione su `a`: $a \ne 0$

3.  Affinché `(a > b && b != 10)` sia **FALSO**, l'operatore **AND** (`&&`) deve essere falso. Un'espressione AND è falsa se *almeno uno* dei suoi operandi è falso:

      * Caso A: `a > b` è **FALSO** (cioè $a \le b$).
      * Caso B: `b != 10` è **FALSO** (cioè $b = 10$).

**Esempi di Soluzioni (combinando $a \ne 0$ con un caso di falsità per l'AND):**

  * **Soluzione 1 (Sfruttando il Caso A):** Se $a=10$ e $b=15$.

      * $a \ne 0$: Vero.
      * $a > b$ (10 \> 15): Falso. $\rightarrow$ L'AND è Falso.
      * L'OR è Falso || Vero = **FALSO**.

  * **Soluzione 2 (Sfruttando il Caso B):** Se $a=1$ e $b=10$.

      * $a \ne 0$: Vero.
      * $b \ne 10$: Falso. $\rightarrow$ L'AND è Falso.
      * L'OR è Falso || Vero = **FALSO**.

**Risposta Breve:**
La stringa "Verificato" non verrà stampata quando **$a \ne 0$** E contemporaneamente:

  * **$a \le b$** (es. `a=10, b=15`)
    **OPPURE**
  * **$b = 10$** (es. `a=1, b=10`)
