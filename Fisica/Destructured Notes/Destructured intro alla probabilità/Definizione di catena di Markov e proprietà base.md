
Una catena di Markov è un modo per studiare processi stocastici discreti
Iniziamo definendo:
$$
	p_{i}(t)=P[X_{t}=i] \quad i\in \mathbb{Z}, t\in \mathbb{N}
$$
Probabilità di trovare la variabile $X$ in un certo sito $i$ al tempo $t$.
Questa probabilità dipende dalla posizione della variabile nel tempo precedente, si tratta dunque di una probabilità condizionata (basta pensare al modello del random walk in una dimensione).
$$
	P[X_{t+1}=j|X_{t}=i_{1} \cap X_{t-1}=i_{2}\cap\dots\cap X_{t-s}=i_{s}]
$$
Se questa probabilità dipende solo dalla posizione immediatamente precedente, allora parliamo di processo Markoviano o senza memoria:
$$
	P[x_{t+1}=j|X_{t}=i]
$$
Un processo markoniano equivale a un'equazione differenziale in ambito deterministico.
Un processo non markoviano corrisponde invece ad un'equazione integrale.

Per studiare processi di questo tipo è fondamentale introdurre una Matrice di Transizione:
$$
	W_{ij}(t)=P[X_{t+1}=j|X_{t}=i]
$$
La scelta di tenere lo stato di partenza come primo indice e lo stato di arrivo come secondo indice è puramente convenzionale.
Questa matrice soddisfa alcune proprietà:
1. $W_{ij}(t)\geq 0$
2. $\sum_{j}W_{ij}=1$ (somma sul secondo indice, sto dicendo che partendo da uno stato $i$ la somma delle probabilità di spostarsi su ciascuno stato raggiungibile fa 1).
Matrici che soddisfano queste due proprità prendono il nome di matrici stocastiche.
Convenzionalmente mettiamo il primo indice sulle colonne e il secondo indice sulle righe.
L'evoluzione della catena di Markov è data da:
$$p_{j}(t+1)=\sum_{i}p_{i}(t)W_{ij}(t)$$
Ci occupiamo principalmente di processi stazionari, cioè processi per i quali $W_{ij}$ non dipende dal tempo.
$$
	\sum_{j}p_{j}(t+1)=1=\sum_{j}\sum_{i}p_{i}(t)W_{ij}=\sum_{i}p_{i}(t)\sum_{j}W_{ij}=\sum_{i}p_{i}(t)=1
$$
Dunque la seconda condizione sulla matrice serve a preservare la normalizzazione.

Esempio: RW simmetrico in 1D
Modellando il RW con una catena di Markov devo identificare la matrice di transizione:
$$
	W_{i,i+1}=W_{i+1,i}=\frac{1}{2} \qquad \text{e} \qquad W_{i,j}=0 \quad\text{ negli altri casi}
$$
Dunque troviamo:
$$\begin{aligned}
p_{i}(0)&=\delta_{i 0}\\
p_{j}(1)&=\sum_{i}p_{i}(0)W_{ij} = p_{0}(0)W_{0j}=\begin{cases}
\frac{1}{2} \quad j=-1 \\
\frac{1}{2} \quad j=1
\end{cases}
\end{aligned}
$$
NOTA BENE: In reltà l'importante per processi Markoviani è che la memoria sia finita, non necessariamente 1.
Per farlo consideriamo l'esempio di un processo che abbia memoria dei 2 processi precedenti.
$$
	P[X_{t+1}=j | X_{t}=i \cap X_{t-1}=j]
$$
A questo punto aumento la dimensione dello spazio degli eventi e considero una nuova probabilità:
$$
	P[X_{t},Y_{t}\equiv X_{t-1}|X_{t-2}]
$$
E mi sono ricondotto al caso di prima (?).


**Lezione Associata:** [[6.Catene di Markov discrete]]