
**Prerequisiti:** [[Funzioni Generatrici]]

Un processo di ramificazione è un processo in cui in individuo genera $k$ individui con probabilità $P_{k}$ e ogni generazione successiva fa lo stesso. Si tratta dunque di una formalizzazione di processi a catena.

![[Pasted image 20261004122603.png]]

La domanda che viene spontaneo porsi è: se a $t=0$ ho un individuo e le $\{ P_{k} \}$ sono note, qual è la probabilità di avere $m$ individui dopo $n$ generazioni? Per $n$ piccolo si può procedere a contare con la orza bruta, se $n$ è grande la situazione si fa di gran lunga più complessa.
Esiste però un modo per calcolare $G_{2}(s)$ cioè la funzione generatrice dopo 2 generazioni, e poi $G_{3}(s)$ e così via fino a $G_{n}(s)$. La probabilità di avere $m$ individui dopo $n$ generazioni sarà il coefficiente davanti a $s^m$ nella serie $G_{n}(s)$.

Per arrivare a ciò andiamo ad esporre ancora un risultato molto utile.
Siano $x_{1},x_{2},\dots$ variabili **indipendenti e identicamente distribuite** con funzioni generatrici $G(s)$, e sia $N$ una variabile, indipendente dalle $\{ x_{i} \}$, con funzione generatrice $F(s)$. La funzione generatrice $G_{y}(s)$ della variabile $y=x_{1}+x_{2}+\dots+x_{N}$ vale:
$$
	G_{y}(s)=F(G(s))
$$

La dimostrazione è semplice e segue dai risultati precedenti:
___
Sia $P_{N}$ la probabilità di $N$. Fissato $N$ ho che $G_{y}^{(N)}=\prod^N_{i=1}G(s)=G^N(s)$.
Per $N$ non fissato trovo:
$$
	G_{y}(s)=\sum^\infty_{N=0}P_{N}G_{y}^{(N)}(s)=\sum^\infty_{N=0}P_{N}G^N(s)=F(G(s))
$$
$\blacksquare$
___

Usando questo risultato possiamo calcolare $G_{n}$ del problema di un processo di ramificazione.
Sia $N_{n-1}$ il numero di individui all'$(n-1)$-esima generazione. Chiamiamo $x_{1}$ il numero di individui generati dal primo individuo, $x_{2}$ il numero di individui generati dal secondo individuo (della stessa generazione) e così via. All'$n$-esima generazione avremo:
$$
	N_{n}=x_{1}+x_{2}+\dots+x_{N_{n-1}}
$$
Usando il risultato appena dimostrato si ha che:
$$
	G_{n}(s)=G_{n-1}(G(s))
$$
dunque:
$$
	G_{2}(s)=G(G(s)),\quad G_{3}(s)=G_{2}(G(s))=G(G(G(s))),\quad \dots
$$
Questo calcolo è matematicamente semplice ma può velocemente portare a espressioni scomode da maneggiare.

**ESEMPIO:** Calcoli di A.Lotka, 1920

Sfruttando i dati demografici, Lotka mostrò che negli Stati Uniti all'inizio del 1900 un maschio generava $k$ maschi con probabilità date da:
$$
	P_{0}=\frac{1-(\alpha+\beta)}{1-\beta},\quad P_{k}=\alpha \beta^{k-1}
$$
con $\alpha \simeq{0}.2126$ e $\beta \simeq{0}.5892$. La funzione generatrice risulta pertanto:
$$
	G(S)=P_{0}+\alpha \sum^\infty_{k=1}\frac{(s\beta)^k}{\beta}=P_{0}+\frac{\alpha s}{1-\beta s}
$$
Cioè un'iperbole. Si può ulteriormente dimostrare che:
$$
	G_{n}(s)=\frac{A_{n}-B_{n}s}{C_{n}-D_{n}s}
$$
resta sempre un'iperbole, i coefficienti $A_{n}, \dots$ si ottengono in maniera ricorsiva.