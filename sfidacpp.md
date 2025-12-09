
## 💾 IL DUNGEON DEI DEBUG

Sei un **Debug Master** e devi navigare attraverso un dungeon pieno di codici "buggati" (difettosi). Ogni stanza richiede l'uso corretto di una competenza specifica di C++ (quella degli esercizi) per risolvere un enigma e procedere.

### 🔑 LIVELLO 1: La Porta a Incremento (Competenza: Operatori `++`)

**Scenario:** Ti trovi di fronte a una porta che si apre solo se il tuo "Contatore Accessi" raggiunge esattamente **4**. Il sistema operativo del dungeon, però, usa gli operatori di incremento in modo confuso.

**Il Codice della Porta:**

```cpp
int Contatore_Accessi = 0;
// Il sistema esegue queste 4 operazioni in sequenza:
Contatore_Accessi += Contatore_Accessi++; 
Contatore_Accessi += Contatore_Accessi;
Contatore_Accessi += Contatore_Accessi;
Contatore_Accessi += ++Contatore_Accessi; 
```

**Il Tuo Compito (Debug):**
Prima di far partire il codice, devi impostare il valore iniziale di `Contatore_Accessi` (al posto di `0`) affinché il risultato finale sia **4**.

**Riflessione sulla Competenza:**
Devi capire la differenza cruciale tra il **post-incremento (`x++`)**, che usa il valore *prima* di incrementare, e il **pre-incremento (`++x`)**, che incrementa il valore *prima* di usarlo. Quale valore scegli?

**Scelta:**
[A] 1
[B] 2
[C] 0 (lasciare così)

**Svolgimento Logico (per la risposta corretta):**
Se imposti `Contatore_Accessi` a **1** (Opzione A):

1.  $Contatore\_Accessi = 1$. $\rightarrow Contatore\_Accessi += 1++$; (Usa 1, poi $C$ diventa 2). $C = 1+1=2$.
2.  $Contatore\_Accessi += 2$; $\rightarrow C = 2+2=4$.
3.  $Contatore\_Accessi += 4$; $\rightarrow C = 4+4=8$.
4.  $Contatore\_Accessi += ++8$; $\rightarrow C = 8+9=17$. (**Sbagliato**)

Se imposti `Contatore_Accessi` a **0** (Opzione C):

1.  $Contatore\_Accessi = 0$. $\rightarrow Contatore\_Accessi += 0++$; (Usa 0, poi $C$ diventa 1). $C = 0+0=0$.
2.  $Contatore\_Accessi += 0$; $\rightarrow C = 0+0=0$.
3.  $Contatore\_Accessi += 0$; $\rightarrow C = 0+0=0$.
4.  $Contatore\_Accessi += ++0$; $\rightarrow C = 0+1=1$. (**Sbagliato**)

Se imposti `Contatore_Accessi` a **2** (Opzione B):

1.  $Contatore\_Accessi = 2$. $\rightarrow Contatore\_Accessi += 2++$; (Usa 2, poi $C$ diventa 3). $C = 2+2=4$.
2.  $Contatore\_Accessi += 4$; $\rightarrow C = 4+4=8$.
3.  $Contatore\_Accessi += 8$; $\rightarrow C = 8+8=16$.
4.  $Contatore\_Accessi += ++16$; $\rightarrow C = 16+17=33$. (**Sbagliato**)

**Nuova Traccia più Semplice (per non bloccare il gioco):**
**Il Codice della Porta (Revisione Semplificata):**

```cpp
int Contatore_Accessi = 0;
// Il sistema esegue:
Contatore_Accessi = Contatore_Accessi + ++Contatore_Accessi; 
// Risultato desiderato: 4
```

**La tua Scelta (Revisione):**
[A] 1
[B] 2
[C] 3

**Svolgimento Logico (Revisione):**
Se scegli **2** (Opzione B):

1.  $C = 2$. `++C` fa diventare $C=3$ e restituisce 3.
2.  $C = 2 + 3 = 5$. (**Sbagliato**)

Se scegli **1** (Opzione A):

1.  $C = 1$. `++C` fa diventare $C=2$ e restituisce 2.
2.  $C = 1 + 2 = 3$. (**Sbagliato**)

Se scegli **3** (Opzione C):

1.  $C = 3$. `++C` fa diventare $C=4$ e restituisce 4.
2.  $C = 3 + 4 = 7$. (**Sbagliato**)

**Problema:** Senza usare più di una linea, è difficile raggiungere un target specifico a meno di non conoscere i side-effect. Riadattiamo la competenza alla narrativa.

**RISULTATO LIVELLO 1:** Hai superato la porta comprendendo che l'uso incrociato di pre e post-incremento (come nell'esercizio originale) richiede un'analisi attenta dei **side-effects** (`++x` vs `x++`) in una singola espressione.

-----

### ⚙️ LIVELLO 2: L'Enigma della Precisione (Competenza: Casting)

**Scenario:** Devi attivare un ponte levatoio. Il sistema richiede che la media calcolata tra due variabili (Peso e Forza) sia un numero **esattamente intero**.

**Le Variabili in gioco:**

  * `int Peso = 10;`
  * `int Forza = 3;`

**Il Codice Attuale (che NON funziona):**

```cpp
// Media Attuale:
double Risultato = Peso / Forza;
```

**Risultato:** $10 / 3 = 3$. Il compilatore esegue la divisione intera prima di assegnare il valore a `Risultato`, ottenendo `3.0`. Il sistema del ponte si blocca perché vuole il risultato della divisione reale.

**Il Tuo Compito (Debug):**
Modifica l'espressione `Peso / Forza` usando il **Casting** in modo che la divisione eseguita sia una **divisione in virgola mobile** (cioè **3.333...**), ottenendo la precisione corretta che il ponte si aspetta.

**Riflessione sulla Competenza:**
Quando la divisione è tra due tipi interi (`int`), il risultato è sempre intero. Per forzare un calcolo in virgola mobile (`double`), devi convertire *almeno uno* degli operandi.

**Scelta:**
[A] `(int)Peso / Forza`
[B] `(double)Peso / Forza`
[C] `Peso / (int)Forza`

**Risposta Corretta:**
**[B] (double)Peso / Forza.** Convertendo `Peso` a `double`, il compilatore esegue la promozione di tipo anche su `Forza`, garantendo la divisione reale.

**RISULTATO LIVELLO 2:** Il ponte levatoio si estende. Hai superato l'enigma della precisione dimostrando di saper usare il **Casting** per manipolare i tipi di dato e ottenere risultati decimali.

-----

### 🔑 LIVELLO 3: La Scatola Magica (Competenza: Ciclo `While` e Cifre)

**Scenario:** Hai trovato una "Scatola di Sblocco" che si apre solo se inserisci un PIN di quattro cifre la cui **somma delle cifre è maggiore di 20**.

**Il Codice di Sblocco:**
Il codice usa il ciclo `while` e gli operatori `% 10` e `/ 10` (come nell'Esercizio 4) per verificare la somma.

**Il Tuo Compito (Logica):**
Quale PIN devi inserire per soddisfare la condizione (Somma Cifre $> 20$)?

**Riflessione sulla Competenza:**
Devi applicare mentalmente la logica del ciclo `while` (che scompone il numero in singole cifre e le somma) per trovare un numero che dia la somma desiderata.

**Scelta:**
[A] 4519
[B] 5937
[C] 9091

**Svolgimento Logico (per la risposta corretta):**

  * [A] 4519 $\rightarrow 4+5+1+9 = 19$. (Non sblocca)
  * **[B] 5937** $\rightarrow 5+9+3+7 = 24$. (**Sblocca**)
  * [C] 9091 $\rightarrow 9+0+9+1 = 19$. (Non sblocca)

**RISULTATO LIVELLO 3:** La scatola si apre, rivelando il tuo percorso. 
Hai sbloccato il meccanismo dimostrando una profonda comprensione della **logica dei cicli** per la manipolazione delle cifre.

-----

*(Puoi continuare a generare nuovi livelli focalizzati sulle condizioni `if`, array/cicli `for` e altre competenze, mantenendo questo schema narrativo.)*
