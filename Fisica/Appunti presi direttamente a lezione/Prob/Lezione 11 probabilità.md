
Problema del collezionista nel caso di più di due figurine ($s\neq 2$).

Costruiamo un ragionamento valido per $s$ oggetti con probabilità $p=\frac{1}{s}$ (Caso equiprobabile).

Impostiamo il ragionamento per $s=2$:
- primo lancio ha successo $p=1$
- il secondo lancio ha successo $p=\frac{1}{2}\implies$ # lanci medi $=2$.
Tot: 1 lancio dal primo, 2 dal secondo $\implies 3$ lanci

$s$ generico:

| ORDINI | PROB              | # NUMERO DI "LANCI" |
| ------ | ----------------- | ------------------- |
| 1      | 1                 | 1                   |
| 2      | $$\frac{s-1}{2}$$ | $$\frac{s}{s-1}$$   |
| 3      | $$\frac{s-2}{s}$$ | $$\frac{s}{s-2}$$   |
| ...    |                   |                     |
| $s$    | $$\frac{1}{s}$$   | $$s$$               |
dunque:
$$
	\langle n \rangle =\sum^s_{k=1} \frac{s}{k} = s \sum^s_{k=1} \frac{1}{k}
$$
Nel caso $s=6$ troviamo $\langle n \rangle=14.7$ lanci in media.
Nel caso in cui $s\gg 1$ si può ulteriormente semplificare la formula.
$$
	\langle n \rangle =s \sum^s_{k=1} \frac{1}{k} \simeq s[\ln s+\gamma]
$$
Con $\gamma=0.577$ costante di Eulero-Mascheroni.


**Esercizio** (Sulle catene di Markov)

Abbiamo una scatola contenente 2 palline rosse e 2 palline nere.
2 giocatori a turno estraggono una pallina. Se viene estratta $N$ viene rimossa, se viene estratta $R$ viene reinserita nella scatola e viene aggiunta una nera.
Vince $A$ se arrivo a $4$ palline nere, vince $B$ se arrivo a $0$, (è uno pseudo random walk con barriere).
Il gioco è equo?

- Dimostriamo che è una catena di markov, cioè troviamo $W$. A questo punto troviamo $\vec{\pi}$ distribuzione stazionaria e le probabiltà di uscita $u_{0}$ e $u_{4}$.

Osservazione: la pallina rossa non descrive lo stato del sistema, lo stato del sistema è descritto solo dalle palline nere, con $0\leq N\leq 4$, 5 stati.
In partenza abbiamo $W_{21}=W_{23}=\frac{1}{2}$.
Partendo da $1$ nera abbiamo: $W_{13}=\frac{1}{3}$ e $W_{12}=\frac{2}{3}$.
Per $0$ abbiamo: $W_{00}=1$ e $W_{01}=0$
Per 3 abbiamo: $W_{34}=\frac{2}{5}$ e $W_{32}=\frac{3}{5}$
Per 4 abbiamo: $W_{44}=1$ $W_{43}=0$.
Dunque:
$$
	W=\begin{pmatrix}
	1 & 0 & 0 & 0 & 0 \\
	\frac{1}{3} & 0 & \frac{2}{3} & 0 & 0 \\
	0 & \frac{1}{2} & 0 & \frac{1}{2} & 0 \\
	0 & 0 & \frac{3}{5} & 0 & \frac{2}{5} \\
	0 & 0 & 0 & 0 & 1
	\end{pmatrix}
$$
Troviamo gli stati stazionari:
$$
	\vec{\pi}=\vec{\pi} \cdot W
$$
Dunque:
$$
	\begin{cases}
	\pi_{0}=\pi_{0}+\frac{1}{3}\pi_{1} \\
	\pi_{1}=\frac{1}{2}  \pi_{2} \\
	\pi_{2} = \frac{2}{3} \pi_{1} +\frac{3}{5}\pi_{3} \\
	\pi_{3}= \frac{1}{2}\pi_{2} \\
	\pi_{1}= \frac{2}{5}\pi_{3}+\pi_{4}
	\end{cases}
$$
Troviamo che $\pi_{1},\pi_{2},\pi_{3}=0$ e $\pi_{0}$ e $\pi_{4}$ sono legat tra loro dalla normalizzazione:
Dunque:
$$
	\vec{\pi}=(p,0,0,0,1-p)\; \forall p \in[0,1]
$$
Dove $p$ dipende dalle condizioni iniziali.

Troviamo le probabilità di uscita (ricorda, sono gorvernate dalle kolmogorov backward).
$$
	\vec{u}=W \cdot \vec{u}
$$
Dunque:
$$
	\begin{cases}
	u_{0}=u_{0} \\
	u_{1}=\frac{1}{3}u_{1}+\frac{2}{3}u_{2} \\
	u_{2}= \frac{1}{2}u_{1}+\frac{1}{2}u_{3} \\
	u_{3}= \frac{3}{5}u_{2}+\frac{2}{3}u_{4} \\
	u_{4}=u_{4}
	\end{cases}
$$
$u_{k}$= probabilità di uscita in $0$ partendo da $k$.
Risolvendo il sistema troviamo:
$u_{1}=\frac{7}{11}$ e $u_{2}=\frac{5}{11}$ e $u_{3}=\frac{3}{11}$.
Ha senso, più parto lontano dalla barriera in $0$ più è facile uscire.
Abbiamo trovato che $u_{2}=\frac{5}{11} \neq \frac{1}{2}$ e il gioco è iniquo.


### Applicazioni della probabilità a campi non strettamente fisici

**Distribuzione dei numeri primi**:

$$
	\pi(x): \#\text{ di primi } \leq x
$$
$\pi(2)=1$, $\pi(3)=2$, $\pi(4)=2$, $\pi(5)=3$, si tratta di una distribuzione crescente e $\pi(x)\leq x-1$.
Un modo per trovare i numeri primi è il codiddetto setaccio:
Considero una sequenza di numeri naturali:
$$
	1,2,3,4,5,6,7,8,9,10,11,\dots
$$
Prendo il primo primo $p_{1}=2$ e tolgo tutti i multipli di 2:
$$
	1,2,3,5,7,9,11\dots
$$
Prendo il secondo primo $p_{2}=3$ e tolgo tutti i multipli di 3:
$$
	1,2,3,5,7,11\dots
$$
Procedo così fino a restare con soli numeri primi.
Su questo si basa l'argomentazione probabilistica di Schroeder.
Se $k$ è un primo, la "probabilità" che $x>k$ sia divisibile per $k$ vale $\frac{1}{k}$.
Dunque la probabilità che $x$ sia pimo è la probabilità che non sia divisibile per $k<x$
$$
	p(x)=\left( 1-\frac{1}{2} \right)\left( 1-\frac{1}{3} \right)\left( 1-\frac{1}{5} \right)\dots=\prod_{k_{j}<x}\left( 1-\frac{1}{k_{j}} \right)
$$
dove $k_{j}$ sono i primi minori di $x$. Prendiamo il logaritmo di entrambi i membri:
$$
	\ln p(x)= \sum_{k_{j}<x}\ln\left( 1-\frac{1}{k_{j}} \right) \simeq -\sum_{k_{j}<x} \frac{1}{k_{j}}
$$
Se $k_{j}$ è sufficientemente grande (ho introdotto così un errore sistematico). Posso riscriverlo come una somma su tutti i numeri che vale $0$ se non è primo e $1$ se è primo, oppure posso usare come peso la probabilità che il numero sia primo.
$$
	\ln p(x) = -\sum^x_{j=1} \frac{1}{j} p(j) \underset{x\gg 1}{\simeq} -\int^x_{2} \frac{p(t)}{t} dt
$$
Derivo entrambi i membri:
$$
	\frac{1}{p(x)}p'(x)=-\frac{p(x)}{x}
$$
Definisco $q(x)\equiv\frac{1}{p(x)}\implies q'(x)=-\frac{1}{p^2(x)} \frac{dp}{dx}=-q^2(x)p'(x)$ e ottengo:
$$
	-\frac{q'(x)}{q(x)}=-\frac{1}{xq(x)}\implies q'(x)=\frac{1}{x}
$$
E troviamo:
$$
	q(x)=\ln(x)\implies p(x)=\frac{1}{\ln(x)} \qquad \text{ probabilità che }x \text{ sia un numero primo}
$$
Ora possiamo calcolare la distribuzione $\pi(x)$:
$$
	\pi(x)= \int^x_{2} p(y) dy = \int^x_{2} \frac{dy}{\ln y}=li(x)-li(2)
$$
Dove $li(x)=\int^x_{0} \frac{dy}{\ln y}$, funzione log-integral.

![[Pasted image 20261103120351.png]]

Per $x\gg 1$ abbiamo che $li(x)\simeq \frac{x}{\ln(x)}$.
Dunque:
$$
	\pi(x)\simeq \frac{x}{\ln x}
$$
Teorema dei numeri primi (congetturato da Legendre nel 1798 e dimostrato da Chebychev nel 1848).
Il numero di primi cresce più lentamente di $x$.

| $x$    | $\pi(x)$             | $li(x)-li(2)$        | $$\frac{x}{\ln x}$$ |
| ------ | -------------------- | -------------------- | ------------------- |
| 100    | 25                   | 30,01                | 21,7                |
| $10^6$ | 78498                | 78628                | 72498,...           |
| $10^9$ | 50,8476 $\cdot 10^6$ | 50,849 $\cdot{10}^6$ | 48,25 $\cdot 10^6$  |

#### Legame con la zeta di Riemann

Ricordando che:
$$
	\zeta(s)\equiv \sum^\infty_{n=1} \frac{1}{n^s} = \prod_{\text{p primo}} \frac{1}{1-p^{-s}}
$$
con $s>1$.
Estendendo il dominico della $\zeta$ al campo complesso esiste una famosa ipotesi di Riemann che dice che:
- $\zeta(s)$ ha zeri banali per $s=-2k$ dimostrato in Metodi 2
- $\zeta(s)$ ha zeri non banali solo su $\mathrm{Re}(s)= \frac{1}{2}$
Nel 1900 Hilbert mette la congettura di Riemann tra i suoi 23 problemi da risolvere (fa parte anche dei 7 problemi del millennio).
Di recente OpenAi ha dimostrato che nel semipiano con $\mathrm{Re}(s)> \frac{11}{12}$ non ci sono zeri, riducendo la banda da $[0,1]$ a $\left[ 0, \frac{11}{12} \right]$.


#### Legge di Benford

Newcomb nota che le prime pagine delle tavole logaritmiche erano molto più usate delle altre, cioè numeri che iniziavano con $1,2,3$ erano molto più consultate di quelle che iniziano con $7,8,9$. E si chiede il perchè

Benford (50 anni dopo) osserva la stessa cosa e adotta un approccio sistematico, trovando che, preso un numero casuale di qualunque cosa (di cui sia effettuabile una misura) e il cui valore spanna diversi ordini di grandezza, la frequenza di numeri che iniziano con $a$ 
($a=1,2,\dots 9$) è:
$$
	f_{a}=\log_{10} \left( \frac{a+1}{a} \right)
$$
Si tratta di una legge empirica.
L'esempio più celebre si ha con la lunghezza dei fiumi nel mondo:
$$
	f_{1}= \log_{10} \left( \frac{2}{1} \right) \simeq{0},301\dots
$$
Questo è molto strano, infatti:
Sia $A_{N}$ il set di numeri $<N$ che iniziano con "1".
$$
	\begin{cases}
	N=9 & A_{9}=1 & f_{1}=\frac{1}{9} \\
	N=20 & A_{20}=(1,11,\dots,19) & f_{1}=\frac{11}{20} \\
	\dots \\
	N=50 & A_{50}=A_{20} & f_{1}=\frac{11}{20} \\
	\dots \\
	N\to \infty &  &  f_{1} \simeq \frac{1}{2}
	\end{cases}
$$
Questa frequenza non sembra convergere
Ulteriormente un altro problema è che questa legge dev'essere invariante per cambi di unità di misura, cioè invariante di scala:
$$
	x\to a\cdot x \quad \text{non varia }f
$$
Osservazione: la distribuzione uniforme (che è la più intuitiva lungo cui dovrebbero disporsi le misure) non è invariante di scala:
$$
	f_{k}= \frac{1}{k}
$$
Ad esempio, con un fattore di scala $a=2$
Tutti i numeri che stanno in $[1,1.5]$ vengono mandati in numeri che iniziano con $2$.
Quelli in $[1.5,2]$ vengono mandati in numeri che iniziano con 3.
Quelli in $[2,2.5]$ vengono mandati in numeri che iniziano con 4.
$[2.5,3]\to 5$ ... e ... $[4.5,5]\to{9}$.
Tutti i numeri $[5, 9.99999]\to{1}$. Dopo aver applicato il fattore di scala la distribuzione non è più uniforma ma sbilanciata verso $1$.


