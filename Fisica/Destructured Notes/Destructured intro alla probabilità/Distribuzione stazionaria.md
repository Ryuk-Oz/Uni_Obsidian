
**Essenziale:** [[Definizione di catena di Markov e proprietà base]]

arliamo di distribuzione stazionaria se esiste una distribuzione di probabilità che non varia nel tempo, una sorta di posizione di equilibrio $\pi$.
Diciamo che la catena converge ad una distribuzione stazionaria se:
$$
	\lim_{ t \to \infty } p_{i}(t)\equiv \pi_{i}
$$
Cioè da un certo punto in poi $p_{i}$ smette di dipendere dal tempo.
E vale:
$$
	\pi_{j}=\sum_{i}\pi_{i}\cdot W_{ij} \qquad \text{cioè} \quad \vec{\pi}=\vec{\pi}W
$$
Quest'identità è quella che "codifica" l'invarianza temporale della sitribuzione stazionaria.
**Oss:** Non è detto che esista la distribuzione stazionaria $\pi$. Ad esempio nel random walk non esiste una distribuzione stazionaria.

**Esempio semplice**: Catena di Markov a 2 stati.
Catena in cui la variabile aleatoria può assumere solo 2 valori $X=\{ 0,1 \}$, tipo il lancio di una moneta (ma il lancio di una moneta non è una catena di Markov).
Consideriamo il processo in cui $X$ cambia stato con probabilità $p$ e resta nello stesso stato con probabilità $1-p$.
Possiamo modellare il processo come un grafo:
![[Pasted image 20261020120454.png|526]]
scriviamo la matrice di transizione:
$$W=
	\begin{pmatrix}
	1-p & p \\
	p & 1-p
	\end{pmatrix}
$$
Cerchiamo la distribuzione stazionaria.
Intuitivamente ci viene da pensare che $\vec{\pi}=\left( \frac{1}{2}, \frac{1}{2} \right)$.
Sappiamo che $\vec{\pi}=\vec{\pi}\cdot W$ dunque:
$$
	(\pi_{0},\pi_{1})=(\pi_{0},\pi_{1})\begin{pmatrix}
	1-p & p \\
	p & 1-p
	\end{pmatrix}
$$
E otteniamo:
$$
	\begin{cases}
	\pi_{0}=(1-p)\pi_{0}+p\pi_{1} \\
	\pi_{1}=p\pi_{0}+(1-p)\pi_{1} \\
	\pi_{0}+\pi_{1}=1 \quad \text{ per la normalizzazione}
	\end{cases}
$$
Risolvendo il sistema troviamo:
$$
	\begin{cases}
	\pi_{0}=\pi_{1} \\
	\pi_{0}+\pi_{1}=1
	\end{cases}
$$
E torniamo al risultato atteso.

Occupiamoci di studiare l'evoluzione della catena partendo da condizioni iniziali generiche:
$$
	\vec{p}(0)=(p_{0},1-p_{0})=(p_{0}(0),p_{1}(0))
$$
$p_{0}=$ probabilità di trovarsi nello stato 0 all'istante iniziale.
Studiamo l'evoluzione partendo da questa condizione iniziale mediante la matrice di transizione.
$$
	(p_{0}(1),p_{1}(1))=(p_{0}(0),p_{1}(0))\begin{pmatrix}
	1-p & p \\
	p & 1-p & 
	\end{pmatrix}
$$
Guardiamo cosa troviamo al tempo $t+1$.
$$
	\begin{cases}
	p_{0}(1)=(1-p)p_{0}(0)+p\,p_{1}(0) \\
	p_{0}(2)=(1-p)p_{0}(1)+p\,p_{1}(1) \\
	\dots \\
	p_{0}(t+1)=(1-p)p_{0}(t)+p\,p_{1}(t)
	\end{cases}
$$
L'altra equazione è: $p_{1}(t+1)=p\,p_{0}(t)+(1-p)p_{1}(t)$
Mettendo queste due a sistema e sfruttando la normalizzazione $p_{1}+p_{0}=1$ otteniamo:
$$
\begin{aligned}
	p_{0}(t+1)&=p+(1-2p)p_{0}(t)=p+(1-2p)[p+(1-2p)p_{0}(t-1)]=\\
	&=p+p(1-2p)+(1-2p)^2p_{0}(t-1)=\dots=\\
	&=p[1+(1-2p)+(1-2p)^2+\dots]+(1-2p)^{t+1}p_{0}(0)=\\
	&=p\sum^t_{k=0} (1-2p)^k + (1-p)^{t+1}p_{0}(0)=\\
	&=p \frac{1-(1-2p)^{t+1}}{1-(1-2p)}+(1-2p)^{t+1}p_{0}(0)\\
	&=\frac{1}{2}-\frac{1}{2}(1-2p)^{t+1}+(1-2p)^{t+1}p_{0}(0)\\
\implies p_{0}(t)&=\frac{1}{2}+(1-2p)^t\left[ p_{0}-\frac{1}{2} \right]
\end{aligned}
$$
Abbiamo che $0<p<1$ (escludo gli uguali altrimenti ottengo un processo deterministico), pertanto $|1-2p|<1$ e va a $0$ per $t\to \infty$.
Dunque abbiamo:
$$
	\lim_{ t \to \infty } p_{0}(t)=\frac{1}{2}=\pi_{0}
$$
Indipendentemente dalle mie condizioni iniziali.

Risultato notevole: se $\vec{p}(0)=\vec{\pi}$ allora trovo che $\vec{p}(t)=\vec{p}(0)=\vec{\pi}$

**Lezione Associata:** [[6.Catene di Markov discrete]]