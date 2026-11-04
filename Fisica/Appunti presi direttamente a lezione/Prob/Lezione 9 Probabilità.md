
La probabilità di raggiungere una barriera è legata all'equazione di Kolmogorov Backward:
$$
	u_{j}=\sum_{k} W_{jk}u_{k}\quad \text{ ovvero } \quad \vec{u}=W\vec{u}
$$
Al contrario, la probabilità invariante è soluzione dell'equazione di Kolmogorov Forward:
$$
	\vec{\pi}=\vec{\pi}W
$$
Osservazione:
le $\pi_{j}$ sono normalizzate ma le $u_{j}$ no! La backward non mantiene la normalizzazione.

**Uscita da due barriere**

Studiamo la probabilità di uscire dalle barriere in generale, non da una barriera specifica

Caso simmetrico ($p=\frac{1}{2}$).

Parto da uno stato $0\leq j\leq c$. Lo studio è esattamente lo stesso ma cambiano le condizioni al contorno. Nello studio di uscita da una barriera qualsiasi queste diventano:
$u_{0}=1$, $u_{c}=1$.
Sappiamo già la soluzione della B-Kolmogorov nel caso simmetrico:
$$
	u_{j}=c_{1}+jc_{2}
$$
Imponiamo le nuove condizioni al contorno:
$$
	\begin{cases}
	u_{0}=c_{1}=1 \\
	u_{c}=c_{1}+c\, c_{2}=1
	\end{cases}
$$
Risolvendo troviamo $u_{j}=1$. L'uscita nel caso di random walk simmetrico con due barriere finite è garantita!

Qual è il tempo medio di uscita?
Definiamo $T_{j}=$ numero di passi per raggiungere la barriera (in 0 o c) partendo da $j$.
Risulta ovvio che $T_{0}=T_{c}=0, \, T_{j}\geq 0$.
La relazione di ricorrenza per i tempi di uscita è:
$$
	T_{j}=T_{j-1}W_{j,j-1}+T_{j+1}W_{j,j+1}+1
$$
Il fattore $+1$ è quello che mi va a contare l'incremento temporale.
Nel caso simmetrico ho:
$$
	T_{j}=\frac{1}{2} T_{j-1}+\frac{1}{2} T_{j+1}+1
$$
Proviamo a risolvere quest'equazione ricordando il legame tra derivata e incrementi discreti.
Definiamo $d_{j}\equiv T_{j}-T_{j-1}$
A questo punto:
$$
	\begin{aligned}
	T_{j}-T_{j-1}&=\frac{1}{2}T_{j-1}+\frac{1}{2}T_{j+1}+1-T_{j-1}\\
	d_{j}&=1+\frac{1}{2}T_{j+1}-\frac{1}{2}T_{j-1}=1+\frac{1}{2}(T_{j+1}-T_{j})+\frac{1}{2} (T_{j}-T_{j-1})\\
	d_{j}&=1+\frac{1}{2}d_{j+1}+\frac{1}{2}d_{j}\\
	\implies d_{j+1}&=d_{j}-2
	\end{aligned}
$$
Siamo passati da 3 a 2 indici, che è più comodo da studiare.
Studiamo il caso per $j=1$ per poi generalizzare.
$$
	\begin{cases}
	j=1 & T_{1}=d_{1} \\
	j=2 & d=T_{2}-T_{1}=T_{2}-d_{1}\implies T_{2}=d_{1}+d_{2} \\
	\dots \\
	j \text{ generico}  & T_{j}=\sum^j_{k=1} d_{k}
	\end{cases}
$$
Ricaviamo i $d_{k}$:
$$
	\begin{cases}
	d_{2}=d_{1}-2 \\
	d_{3}=d_{2}-2=d_{1}-4 \\
	\dots \\
	d_{k}=d_{1}-2(k-1)
	\end{cases}
$$
Sostituendo in $T_{j}$:
$$
	T_{j}=\sum^j_{k=1} [d_{1}-(k-1)2]=d_{1}j-2\sum^{j-1}_{k=0} k
$$
Sappiamo fare questa somma grazie a gauss:
$$
	T_{j}=jT_{1}-\frac{2(j-1)j}{2}=jT_{1}-j(j-1)
$$
Applichiamo le condizioni al contorno
$$
	0=T_{c}=cT_{1}-c(c-1)\implies T_{1}=c-1
$$
Alla fine otteniamo:
$$
	T_{j}=j(c-j)
$$
Il tempo di uscita scala in modo quadratico, come l'andamento lineare della varianza, anche questo è un risultato generale per processi diffusivi.
Per $j=\frac{c}{2}$ abbiamo:
$$
	T_{\frac{c}{2}}= \frac{c^2}{4}=\left( \frac{c}{2} \right)^2
$$

### Proprietà generali delle catene di Markov

- Si dice che uno stato $j$ è **accessibile** dallo stato $i$ se e solo se $\exists t>0:\,  W^t_{ij}>0$.
  con $W_{ij}^t=\underbrace{W_{i,i_{1}}W_{i_{1},i_{2}}\dots W_{i_{t-1,j}}}_{t\text{ volte}}$
- La catena è detta **irriducibile** se ogni stato è accessibile da ogni stato
- Uno stato è detto **persistente** (o ricorrente) se partendo da se stesso ritorna con probabilità 1, è **transiente** se ho prob$>0$ di non tornare.
Esempio: catena di Markov a 3 stati con matrice stocastica:
$$
	W=\begin{pmatrix}
	1-p & p & 0 \\
	0 & 0 & 1 \\
	0 & q & 1-q
	\end{pmatrix}
$$
![[Pasted image 20261028113953.png|600]]
- 1 non è accessibile
- La catena è riducibile
- 1 è transiente
- 2 e 3 sono persistenti
è riducibile perchè dopo essere uscito da 1 posso ridurla a una catena a 2 stati, posso cioè "spezzare la catena".

Riprendiamo l'esempio del RW simmetrico con barriere:
Si nota facilmente che $\forall j \quad 0<j<c$ è transiente, mentre $0$ e $c$ sono persistenti

Una proprietà generale è che in ogni catena di markov FINITA almeno uno stato è persistente.
Al contrario, se gli stati sono infiniti, la catena può essere tutta transiente, ad esempio il RW asimmetrico ($p \neq 0$) sulla retta infinita è transiente.
Il caso simmetrico è invece persistente.
L'esempio ovvio è quello in cui mi sposto solo in una direzione e sono sicuro di nornare nello stato $0$.
Se $p> \frac{1}{2}$ ho probabilità finita di non tornare.

Dimostriamolo:

Ricordiamo l'esempio con barriere asimettrico:
$$
	P[0|j]=u_{j}= \frac{\left( \frac{1-p}{p} \right)^j-\left( \frac{1-p}{p} \right)^c}{1-\left( \frac{1-p}{p} \right)^c}
$$
Se $c\to \infty$ troviamo:
$$
	\left( \frac{1-p}{p} \right)^c\to 0
$$
Dunque:
$$
	u_{j}=\left( \frac{1-p}{p} \right)^j
$$
La probabilità di non arrivare in $0$ partendo da $j$ è:
$$
	p_{j}=1-u_{j}=1-\left( \frac{1-p}{p} \right)^j
$$
Preso come stato iniziale $X_{0}=0$ e $X_{1}=1$ con probabilità $p$ abbiamo che la probabilità di non tornare in 0 da 1 è:
$$
	P_{NR}=p\left( 1-\frac{1-p}{p} \right)=p \frac{p-1+p}{p}=2p-1
$$
se $p=\frac{1}{2}$ ritrovo $P_{NR}=0$. Se $p=1$ trovo $P_{NR}=1$.
Qual è la distribuzione invariante di questa catena?
$\vec{\pi}=\vec{\pi}W$, allora:
$$
	\begin{aligned}
	\pi_{1}&=\sum^3_{j=1}\pi_{j}W_{j{1}}=\pi_{1}(1-p)+\pi_{2}\cdot 0+\pi_{3} \cdot 0 \implies \pi_{1}=0\\
	\pi_{2}&= \pi_{1} p+\pi_{3}q=\pi_{3}q \\
	\pi_{3}&=\pi_{2}+\pi_{3}(1-q)
	\end{aligned}
$$
e troviamo $\vec{\pi}=\left( 0, \frac{q}{1+q}, \frac{1}{1+q} \right)$.

- Una catena si dice **periodica** se i tempi di ritorno su uno stato $i$ sono multipli di un periodo.
  $$W_{i,i}^{kT}>0, \quad W_{i,i}^t=0 \quad \forall t \neq T$$
  un esempio che abbiamo visto è quello del RW ciclico.

- Una catena è **ergodica** se il numero di stati è finito, gli stati sono tutti persistenti e la catena è irriducibile non periodica.
$$
	\exists t:\quad \forall i,j \in \Omega \quad W_{ij}^t>0
  $$
  Catene ergodiche arrivano con sicurezza alla distribuzione invariante.

Sia $A$ una osservabile, cioè una funzione dello stato che assume valore $A$; se $x=j$, se la catena è ergodica:
$$
	\lim_{ t \to \infty } \frac{1}{t} \sum^{t-1}_{k=0} A_{jk}=\sum_{i}A_{i}\pi_{i}
$$

Sia $A:  A_{i}=1 \text{ e } A_{k}=0\text{ se } k\neq i$. Con $i\in \Omega$, allora:
$$
	\lim_{ t \to \infty } \frac{1}{t} \sum^{t-1}_{k=0} A_{jk}=\pi_{i}
$$
Cioè la distribuzione invariante mi da la frazione di tempo spesa da uno stato in $i$.

