
### Proprietà delle catene di Markov

- una catena è detta reversibile se la probabilità di ossevrare una certa sequenza $P(x_{0},x_{1},\dots,x_{n})$ è uguale alla probabilità della sequenza inversa $P(x_{n},\dots \times_{1},x_{0})$.
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
Se una catena soddisfa il bilancio dettagliato $\implies$ la catena è ERGODICA e la probabilità invariante $\vec{\pi}$ soddifa:
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

### Modello di Ehrenfest (Paul e Tatiana)

Consideriamo $N$ molecole in un box diviso in 2 settori $A$ e $B$ .

Prendo una pallina a caso e le cambio la scatola.
Siano $k(t)$ le palline nel settore $A$ e $N-k(t)$ nel settore B.
Come evolve $k(t)$?
$k$ può aumentare o diminuire di uno ad ogni passo, con probabilità data dall'estrazione casuale di una pallina dai box.
Posso descrivere la matrice di transizione del processo nel seguente modo
$$
	\begin{aligned}
	(B\to A) &\quad W_{k,k+1}=\frac{N-k}{N}\\
	(A\to B) &\quad W_{k,k-1}= \frac{k}{N}
	\end{aligned}
$$
Di fatto si tratta di un Random Walk 1-D, "con un potenziale attrattivo", perchè la probabilità varia in modo tale da riportarmi verso lo stato di equilibrio centrale.
$0$ e $N$ sono dunque barriere riflettenti.
Come possiamo calcolare la distribuzione stazionaria?
$$
	\pi_{k}=\sum_{i}\pi_{i}W_{ik}=\pi_{k-1}W_{k-1,k}+\pi_{k+1}W_{k+1,k}
$$
Studiamo come va per valori di $k$ diversi:
$$
	\begin{cases}
	k=0 & \pi_{0}=\pi_{1}W_{10} \\
	 & \pi_{1}=\pi_{0}W_{01}+\pi_{2}W_{21} \\
	 & \pi_{2}=\pi_{1}W_{12}+\pi_{3}W_{32} \\
	 & \dots
	\end{cases}
$$
Posso risolvere per sostituzioni successive e fissare $\pi_{0}$ con la normalizzazione.
$$
	\begin{cases}
	\pi_{1}=\frac{1}{W_{10}}\pi_{0}=N\pi_{0} \\
	\pi_{2}=\frac{1}{W_{21}}(\pi_{1}-\pi_{0}W_{01})=\frac{N}{2}(N\pi_{0}-1\cdot\pi_{0})=\frac{N(N-1)}{2} \pi_{0} \\ \\
	\pi_{3}=\frac{1}{W_{32}}(\pi_{2}-\pi_{1}W_{12})=\frac{N}{3}\left( \frac{N(N-1)}{2} \pi_{0}-N\pi_{0} \frac{N-1}{N}\right)= \frac{N(N-1)(N-2)}{3\cdot 2} \pi_{0} \\
	\dots \\
	\pi_{k}= \frac{N!}{k! (N-k)!}\pi_{0}=\binom{N}{k}\pi_{0}
	\end{cases}
$$
Troviamo $\pi_{0}$ con la normalizzazione:
$$
	\sum_{k}\pi_{k}=\pi_{0}\sum_{k} \frac{N!}{k!(N-k)!}=\pi_{0} 2^N=1\implies \pi_{0}=\frac{1}{2^N}
$$
Dunque:
$$
	\pi_{k}=\frac{1}{2^N} \frac{N!}{k!(N-k)!} 
$$
Distribuzione binomiale con un picco in $\frac{N}{2}$.
Questa è esattamente la stessa distribuzione che otterremmo mettendo a caso le palline nei 2 box.

Il modello di Eherenfest è una catena reversibile, verifichiamolo:
$$
	\pi_{i}W_{ij}=\pi_{j}W_{ji}
$$
Nel nostro caso questo si riconduce a:
$$
	\pi_{k}W_{k,k+1}=\pi_{k+1}W_{k+1,k}
$$
cioè:
$$
	\frac{1}{2^N} \frac{N!}{k!(N-k)!} \frac{N-k}{N}=\frac{1}{2^N} \frac{N!}{k!(N-k-1)!} \frac{N-k-1}{N}
$$
Semplificando otteniamo:
$$
	\frac{1}{k!(N-k-1)!}=\frac{1}{k!(N-k-1)!}
$$
Cioè la pallina salta a sinistra e a destra come vuole.

Questo viola il secondo principio della termodinamica? No, se studiamo l'andamento di $k$, ci accorgiamo che questo è irreversibile e possiamo legarlo all'entropia.

**Evoluzione di $k(t)$**.

$$
	k(t+1)=k(t)\pm1 
$$
Con $+1$ con probabilità $W_{k,k+1}$ e probabilità di $-1$ pari a $W_{k,k-1}$.
Supponiamo di partire da una certa condizione iniziale $k(0)$ e studiamo il valore medio delle realizzazioni su processi ripetuti partendo dalla stessa condizione iniziale:
$$
	\begin{aligned}
	\langle k(t+1) \rangle &=\langle k(t) \rangle +1\cdot W_{k,k+1}-1\cdot W_{k,k-1}\\
	&=\langle k(t) \rangle +\frac{N-\langle k \rangle}{N}-\frac{\langle k \rangle }{N}=1+\langle k(t) \rangle \left( 1-\frac{2}{N} \right)
	\end{aligned}
$$
Questa la so risolvere.
$$
	\langle k(t+1) \rangle -\frac{N}{2}=1+\langle k(t) \rangle \left( 1- \frac{2}{N} \right)-\frac{N}{2}=\left( 1-\frac{2}{N} \right)\left[ \langle k(t)\rangle- \frac{N}{2}  \right]
$$
Ho ottenuto un'equazione per $x(t)\equiv\langle k(t) \rangle-\frac{N}{2}$ che è omogenea e di più facile risoluzione.
$$
	x(t+1)=\left( 1-\frac{2}{N} \right)x(t)\implies x(t)=x(0)\left( 1-\frac{2}{N} \right)^t
$$
Dunque:
$$
	\langle k(t) \rangle -\frac{N}{2}=\left[ k(0)-\frac{N}{2} \right]\left( 1-\frac{2}{N} \right)^t=\left[ k(0)-\frac{N}{2} \right]e^{ t\ln(1-2/N) }
$$
Per $N\gg 1$ posso espandere il logaritmo:
$$
	\langle k(t) \rangle -\frac{N}{2}=\left[ k(0)-\frac{N}{2} \right]e^{ -(2/N)\cdot t }
$$
Cioè, anche se il modello è reversibile ho:
$$
	\lim_{ t \to \infty } \langle k(t) \rangle =\frac{N}{2}
$$
Considerando i tempi collisionali tra molecole di un gas, troviamo che un gas si ridistribuisce molto velocemente.
Questo in meccanica statistica è il teorema $H$ di Boltzmann.

**Esempio**, problema del collezionista.

Supponendo che ci sia un album da completare con $s$ figurine, quante figurine ($n$) devo comprare per completare l'album?
Ovviamente $n\geq s$.

Per $s=2$ ho solo 2 stati possibili, $(T,C)$. Quante figurine devo comprare in media? Riformulato in termini di lanci di moneta: quanti lanci devo fare per ottenere sia $T$ che $C$?
$$
	\underbrace{TTT\dots }_{N-1}C \qquad\text{o} \qquad \underbrace{CCC\dots}_{N-1}T 
$$
Sia $P(T)=p$ e $P(C)=1-p=q$.
La probabilità di $n$ lanci è:
$$
	P_{n}=p^{n-1} q+ q^{n-1} p
$$
Il valore medio di lanci è:
$$
	\langle n \rangle =\sum^\infty_{n=2} n(p^{n-1} q+q^{n-1}p)
$$
Separo in 2 la sommatoria:
$$
	\sum^\infty_{n=2} n p^{n-1} q=q \frac{d}{dp} \sum p^n = q \frac{d}{dp} \left[ \frac{1}{1-p} \right]=q\left( \frac{1}{(1-p)^2}-1 \right)=q\left( \frac{1}{q^2}-1 \right)=\frac{1}{q}-q
$$
L'altra metà si calcola per simmetria.
Così otteniamo:
$$
	\langle n \rangle =\frac{1}{q}-q+\frac{1}{p}-p=\frac{1}{p}+\frac{1}{q}-1
$$
Se $p=q=\frac{1}{2}$ troviamo $\langle n \rangle=3$.

### Teorema di fluttuazione

Se avanza tempo nelle lezioni successive

### Esercizi vari

