### Micro-Esercizio 5: Ciclo `For` e Array

**Traccia:**
Dato il seguente array e ciclo `for` in C++, quale sarà la sequenza di numeri stampati a schermo?

```cpp
int numeri[] = {15, 8, 20, 12, 5};
int dimensione = 5;

for (int i = 0; i < dimensione; i++) {
    if (numeri[i] > 10) {
        cout << numeri[i] << " ";
    }
}
```

**Svolgimento:**

Il ciclo `for` itera attraverso ogni elemento dell'array `numeri`, da un indice $i=0$ fino a $i=4$. All'interno, verifica se l'elemento corrente `numeri[i]` è **maggiore di 10**. Se la condizione è vera, stampa l'elemento.

| Iterazione | Indice (`i`) | Elemento (`numeri[i]`) | Condizione (`numeri[i] > 10`) | Output Stampato |
| :--------: | :----------: | :--------------------: | :---------------------------: | :-------------: |
| **1** | 0 | 15 | Vero | 15 |
| **2** | 1 | 8 | Falso | |
| **3** | 2 | 20 | Vero | 20 |
| **4** | 3 | 12 | Vero | 12 |
| **5** | 4 | 5 | Falso | |

**Output Visualizzato:**

```
15 20 12 
```

**Funzione del Codice:**
Il codice stampa tutti gli elementi dell'array che sono **strettamente maggiori di 10**.
