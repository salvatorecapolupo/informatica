### Micro-Esercizio 1: Operatori di Incremento in C++

**Traccia:**
Dato il seguente frammento di codice C++, se l'utente inserisce il valore **5** per la variabile `x`, quali saranno i quattro valori stampati a schermo, nell'ordine?

```
int x;
cin >> x;        // Utente inserisce 5
cout << ++x << endl;
cout << x << endl;
cout << x++ << endl;
cout << x << endl;
```

**Svolgimento:**

1.  `cin >> x;` → `x` è **5**.
2.  `cout << ++x << endl;` → Pre-incremento. `x` diventa 6, poi stampa **6**.
3.  `cout << x << endl;` → Stampa il valore corrente di `x`, che è **6**.
4.  `cout << x++ << endl;` → Post-incremento. Stampa il valore corrente di `x` (**6**), e *poi* `x` diventa 7.
5.  `cout << x << endl;` → Stampa il nuovo valore di `x`, che è **7**.

**Output Visualizzato:**

```
6
6
6
7
```
