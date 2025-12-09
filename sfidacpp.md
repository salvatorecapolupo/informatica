## 🕹️ CODEX CHALLENGE: I Cinque Livelli

### LIVELLO 1: L'Ordigno Temporale (Operatori `++` e `x++`)

**Scenario:** Devi disinnescare un ordigno impostando la variabile `Chiave` al valore corretto. Il tempo scorre in modo non lineare a causa di un *bug* nel clock.

**Codice da Decifrare:**

```cpp
int x = 5;
int Chiave = 0;

Chiave += x;
Chiave += x++; 
Chiave += ++x;
Chiave += x;

// Il disinnesco avviene se Chiave è uguale al valore finale di X.
```

**Obiettivo:** Qual è il **valore finale** della variabile `x` al termine della sequenza e qual è il **valore finale** di `Chiave`? I due valori sono identici? Se no, l'ordigno esplode\!

-----

### LIVELLO 2: Il Raggio Deviato (Tipi di Dato e Casting)

**Scenario:** Un cannone laser deve colpire un bersaglio alla coordinata 4.333. La sua potenza è gestita da due variabili intere.

**Dati Input:**

  * `int Potenza = 13;`
  * `int Distanza = 3;`

**L'Errore:**
Il laser usa l'espressione `Potenza / Distanza` e, a causa della divisione intera, colpisce solo la coordinata 4, mancando il bersaglio.

**Obiettivo:** Riscrivi l'espressione per il calcolo della coordinata usando il **Casting** in modo che il risultato sia **4.333...** e non 4.

-----

### LIVELLO 3: L'Archivio Sigillato (Condizioni Logiche `&&`, `||`)

**Scenario:** Un archivio segreto è protetto da un triplo lucchetto logico. Il lucchetto si apre solo se la condizione finale dell'istruzione `if` risulta **TRUE**.

**Il Criterio di Sblocco:**

```cpp
bool Lucchetto_A = (a > 10);
bool Lucchetto_B = (b != a);
bool Lucchetto_C = (c % 2 == 0); // c è pari

if ( (Lucchetto_A || Lucchetto_B) && !Lucchetto_C ) {
    // Apri Archivio
}
```

**Obiettivo:** Fornisci **tre numeri interi (a, b, c)** che soddisfino la condizione di sblocco (rendendo la condizione `TRUE`).

-----

### LIVELLO 4: La Cripta delle Cifre (Ciclo `While` e `%`/`/`)

**Scenario:** Una cripta si sblocca solo quando la **somma delle cifre** del PIN a 5 cifre inserito è un **numero primo** e **maggiore di 30**.

**Meccanismo di Verifica:**
Il sistema usa un ciclo `while` per eseguire l'algoritmo di somma delle cifre (`% 10` e `/ 10`).

**Obiettivo:** Qual è il **più grande** numero intero a 5 cifre che puoi inserire (es. 9xxxx) che soddisfi la condizione di sblocco?

-----

### LIVELLO 5: Il Vettore Infiltrato (Ciclo `For` e Array)

**Scenario:** Sei alla guida di un sistema di filtraggio dei dati. Devi isolare i "record maligni" (numeri negativi) dall'array `Dati` in modo efficiente.

**Dati Iniziali:**

```cpp
int Dati[] = {15, -8, 20, -12, 5, -1, 0, 7};
```

**Il Tuo Filtro:**
Scrivi la **sola condizione `if`** che, all'interno di un ciclo `for` standard, stamperà **solo** i numeri negativi e **salterà** l'elemento zero.

**Obiettivo:** Quale sequenza di numeri verrà stampata? E qual è la condizione `if` minimale che lo garantisce?

## 🧩 Micro-Esercizio 6: L'Imbroglio dell'Assegnazione Multipla

**Traccia:**
Osserva il seguente frammento di codice. Quale sarà il valore finale della variabile `risultato` e, crucialmente, quale sarà il valore finale della variabile `x`?

```cpp
int x = 5;
int y = 10;
int risultato = 0;

risultato += (x++) * 2; // Operazione 1
risultato += (++y) / 3; // Operazione 2 (divisione intera)
risultato += x;         // Operazione 3

// Qual è il risultato finale?
```

**Punto Chiave:**
Concentrati sull'ordine di esecuzione degli operatori di incremento/decremento (`++` postfisso e prefisso) e come influenzano i valori nelle espressioni successive.

-----

## 🧪 Micro-Esercizio 7: La Trappola della Precisione (Floating Point)

**Traccia:**
Analizza il seguente codice C++. Quale tra i tre messaggi verrà stampato in output? Spiega la logica dietro la condizione che *potrebbe* non risultare come ci si aspetterebbe matematicamente.

```cpp
double A = 10.0;
int B = 3;

if ( (int)(A / B) == 3 && (A / B) * B == 10.0) {
    cout << "Errore di precisione evitato" << endl;
} else if ( (int)(A / B) == 3 ) {
    cout << "Precisione imperfetta, ma ok" << endl;
} else {
    cout << "Errore di logica" << endl;
}
```

**Punto Chiave:**
Questa sfida mette in gioco la **comparazione di numeri in virgola mobile** (`double`). Devi capire perché $10.0 / 3.0 \times 3$ potrebbe non essere esattamente $10.0$ a causa della rappresentazione binaria in memoria.

-----

## 🪢 Micro-Esercizio 8: La Deformazione dell'Indice

**Traccia:**
Il ciclo `for` seguente non solo scorre l'array, ma manipola la sua stessa variabile contatore (`i`) all'interno del corpo. Quale sarà l'esatta sequenza di numeri stampati in output?

```cpp
int dati[] = {1, 2, 3, 4, 5, 6}; // Array di 6 elementi

for (int i = 0; i < 6; i++) {
    int valore = dati[i];
    
    cout << valore << " "; 
    
    // L'operatore ternario modifica l'indice 'i'
    i = (valore % 2 != 0) ? i + 1 : i; 
}
```

**Punto Chiave:**
Segui attentamente il flusso: l'indice `i` viene letto, l'elemento è stampato, l'indice `i` viene modificato dal ternario, e *infine* l'indice viene incrementato dal `i++` nel blocco `for` prima della successiva iterazione.
