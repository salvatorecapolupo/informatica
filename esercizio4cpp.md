Micro-Esercizio 4: Ciclo While e Cifre

Traccia: Quale sarà il valore finale della variabile somma al termine dell'esecuzione del seguente codice C++, se la variabile numero viene inizializzata a 4519? Descrivi brevemente cosa fa il ciclo.
C++

int numero = 4519;
int somma = 0;

while (numero > 0) {
    int cifra = numero % 10;
    somma = somma + cifra;
    numero = numero / 10; 
}

cout << somma << endl;

Svolgimento:

Il ciclo while continua finché numero è maggiore di 0. Ad ogni iterazione, estrae l'ultima cifra del numero e la aggiunge a somma, dopodiché rimuove l'ultima cifra dal numero. In sostanza, calcola la somma delle cifre del numero intero.
Iterazione	numero all'inizio	cifra (numero % 10)	somma (somma + cifra)	numero alla fine (numero / 10)
0	4519	-	0	-
1	4519	9	0+9=9	4519/10=451
2	451	1	9+1=10	451/10=45
3	45	5	10+5=15	45/10=4
4	4	4	15+4=19	4/10=0
5	0	(Condizione false)	-	-

Output Visualizzato:

19

Funzione del Ciclo: Il ciclo calcola la somma delle cifre del numero iniziale (4 + 5 + 1 + 9 = 19).

    L'operazione modulo 10 (% 10) isola l'ultima cifra.

    La divisione intera per 10 (/ 10) elimina l'ultima cifra.
