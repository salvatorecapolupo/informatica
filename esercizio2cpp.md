### Micro-Esercizio 2: Tipi di Dato e Casting

**Traccia:**
Quali saranno i valori stampati in output dai seguenti due comandi? Spiega la differenza.

```
int a = 10;
int b = 3;

// Operazione 1
cout << a / b << endl; 

// Operazione 2
cout << (double)a / b << endl;
```

**Svolgimento:**

1.  **Operazione 1 (`cout << a / b << endl;`):**

      * Sia `a` che `b` sono di tipo **int** (interi).
      * L'operazione `a / b` esegue una **divisione intera**.
      * $10 / 3$ dà come risultato intero **3** (il resto viene troncato).
      * **Output:** `3`

2.  **Operazione 2 (`cout << (double)a / b << endl;`):**

      * Viene applicato il **casting** esplicito `(double)a` sulla variabile `a`.
      * Ora l'operazione è tra un **double** (10.0) e un **int** (3).
      * Il compilatore esegue una **promozione di tipo** implicita, convertendo anche `b` in `double`.
      * Viene eseguita una **divisione in virgola mobile** (reale).
      * $10.0 / 3.0$ dà come risultato **3.33333...**
      * **Output:** `3.33333` (o un numero simile a seconda dell'implementazione del `cout`)

**Differenza Chiave:**
L'Operazione 1 usa la **divisione intera** perché entrambi gli operandi sono interi. 
L'Operazione 2 usa la **divisione in virgola mobile** perché, grazie al *casting*, 
almeno un operando è un tipo a virgola mobile (`double`).
