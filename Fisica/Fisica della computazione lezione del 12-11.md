
### Turing Machines

Macchina di turing "=" matematico più lento del mondo.

Pyhon è un linguaggio moderno, è nativamente molto complesso, pertanto non è molto utile allo studio dell'informatica teorica, che predilige modelli formali più semplici come macchine di Turing e Lambda calcolo.
Nonostante ciò, programmi in python è macchine di turing sono equivalenti, nei termini di quali problemi possono risolvere.
Programmi equivalenti a macchine di Turing si dicono Turing-completi.

Le macchine di Turing sono i più semplici dei computer, ma restano oggetti astratti. Tuttavia possiamo immaginarla abbastanza bene, sia da un punto di vista più pratico che da uno più matematico.

POV pratico:
Una macchina di turing è fatta da 3 componenti, un'unità di controllo, una testa che legge e scrive ed un nastro.
Il nastro contiene celle, ciascuna della quale può contenere un singolo simbolo (tra cui il simbolo vuoto).
Il simbolo che si trova sotto la testa si dice "scanned symbol".
La testa può cancella il simbolo letto e scriverne uno nuovo.
L'unità di controllo è l'oggetto che dice alla testa che operazione fare.
La configurazione di una macchina è la descrizione completa dello stato in cui si trova in un certo istante di tempo.

![[Pasted image 20261112154720.png]]

POV matematico:
da un punto di vista matematico posso vederlo come un oggetto fatto da un alfabeto $\sum$, insieme finito di simboli (tra cui il vuoto).
Un insieme di stati $Q$, ed una funzione di transizione:
$$
	\delta(q,x)=(q',x',d)
$$
che ad ogni stato e simbolo sotto la testa mi restituisce il nuovo stato $q'$, il nuovo simbolo $x'$ e la direzione in cui si muove la testa dopo, $d$.
Questa rappresentazione si può raffigurare tramite diagrammi di stato.

Descrizione di cosa fa la macchina:
![[Pasted image 20261112155340.png]]

Stessa descrizione tramite diagramma di stato:
![[Pasted image 20261112155440.png]]


Macchine di turing possono agire come accettori o trasduttori, o entrambi.

riempi da slide

Se una macchina di turing va avanti all'infinito, diciamo che va in loop.
Diciamo che una macchina va in halt se non entra in loop, sia accettando, rigettando o non accetando ne rigettando un certo stato $q_{halts}$.
Preso un input, qualunque macchina di turing o entra in loop o halta.

SEGUI DA SLIDE

