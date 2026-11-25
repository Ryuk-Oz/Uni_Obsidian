

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

- **Lemma di Kac**: il tempo medio di ritorno è:
  $E(T_{j})=\langle T_{j} \rangle=\frac{1}{\pi_{j}}$

- una catena è detta **reversibile** se la probabilità di ossevare una certa sequenza $P(x_{0},x_{1},\dots,x_{n})$ è uguale alla probabilità della sequenza inversa $P(x_{n},\dots \times_{1},x_{0})$.
  Questo equivale a chiedere il cosìdetto bilancio dettagliato, cioè:
$$
	\forall i,j \quad \pi_{i}W_{ij}=\pi_{j}W_{ji}
$$
Verifichiamo che le due condizioni siano tra loro equivalenti.

$$
	\begin{aligned}
	\pi_{0} W_{01} W_{12}\dots W_{n-1,n}&=W_{10}\pi_{1}W_{12}\dots W_{{n-1},n} \qquad \text{applicando la definizione di bil. dettagliato}\\
	&=W_{10}W_{21}\pi_{2}\dots W_{n-1,n}\underset{\text{itero}}{=}W_{10}W_{21}\dots W_{n,n-1}\pi_{n}\\
	&=\pi _{n} W_{n,n-1}\dots W_{21}W_{10}
	\end{aligned}
$$
E ci siamo ricondotti alla prima condizione.

Un teorema importante (che non dimostriamo) è il seguente:
Se una catena soddisfa il bilancio dettagliato $\implies$ la catena è ERGODICA e la probabilità invariante $\vec{\pi}$ soddisfa:
$$
	\pi_{i}W_{ij}=\pi_{j}W_{ji}\implies \vec{\pi}=\vec{\pi}W
$$
Infatti:
$$
	\sum_{i} \pi_{i}W_{ij}=\sum_{i} \pi_{j} W_{ji}=\pi_{j}\sum_{i}W_{ji}=\pi_{j}
$$

Una catena di Markov a 2 stati è sempre reversibile.

La dimostrazione è un esercizietto facile.
![[Pasted image 20261020120454.png|526]]
Iniziamo scrivendo la matrice di transizione:
$$
	W=\begin{pmatrix}
	1-p & p \\
	q & 1-q
	\end{pmatrix}
$$
Scriviamo l'equazione di Kolmogorov Forward per la distribuzione stazionaria:
$$
	\vec{\pi}=\vec{\pi}W
$$
Che insieme alla normalizzazione ci fornisce il seguente sistema:
$$
	\begin{cases}
	\pi_{1}=(1-p)\pi_{1}+q\pi_{2} \\
	\pi_{1}+\pi_{2}=1
	\end{cases}
$$
Risolvendo si ottiene subito che:
$$
	\pi_{1}=\frac{q}{p+q}; \qquad \pi_{2}=\frac{p}{p+q}
$$
Ora abbiamo tutti gli ingredienti per verificare il bilancio dettagliato.
$$
	\pi_{1}W_{12}=\pi_{2}W_{21}
$$
cioè:
$$
	\frac{q}{p+q}p=\frac{p}{p+q}q
$$

Al contrario, un $n$-ciclo asimmetrico non è reversibile.

![[Pasted image 20261027001655.png|404]]

Sappiamo già che $\pi_{i}=\frac{1}{n}$. Calcoliamo la matrice stocastica:
$$
	W=\begin{pmatrix}
	0 & p & 0 & 0 & \dots & 1-p \\
	1-p & 0 & p & 0 & \dots & 0 \\
	0 & 1-p & 0 & p & \dots & 0 \\
	\dots & \dots & \dots & \dots & \dots & \dots
	\end{pmatrix}
$$
Verifichiamo il bilancio dettagliato.
$$
	\pi_{i}W_{i,i+1}=\pi_{i+1}w_{i+1,i}
$$
Cioè:
$$
	\frac{1}{n}p=\frac{1}{n}(1-p)
$$


**Lezione Associata:** [[6.Catene di Markov discrete]]