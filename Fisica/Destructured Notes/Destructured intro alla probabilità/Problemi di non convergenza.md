
Non sempre troviamo che $\lim_{ t \to \infty }p_{i}(t)=\pi_{i}$.
L'esempio classico è un RW asimmetrico su di un n-ciclo.
Consideriamo una variabile che assume $n$ valori, $x=\{ 0,1,2,\dots,n-1 \}$.
$$
	\begin{cases}
	W_{i,i+1}=p \\
	W_{i,i-1}=1-p
	\end{cases} \quad W_{ij}=0 \text{ se } j \neq i-1,i+1
$$
è un ciclo nel senso che posso saltare solo allo stato precedente o al successivo, in un ciclo appunto.

![[Pasted image 20261027001655.png|404]]

Per simmetria $\pi_{i}=\frac{1}{n}$ (tutti gli stati sono equiprobabili).
Infatti:
$$
	\pi_{j}=\frac{1}{n}=\sum_{i} W_{ij}\pi_{i}=\frac{1}{n}\sum_{i}W_{ij}=\frac{1}{n}[W_{j-1,j}+W_{j+1,j}]=\frac{1}{n}(p+1-p)=\frac{1}{n}
$$
Ma non è detto che $\lim_{ t \to \infty }p_{i}(t)=\pi_{i}(t)$.

Consideriamo ad esempio un 4-ciclo:
$n=4$ e $p=\frac{1}{2}$ con condizione iniziale $\vec{p}(0)=(1,0,0,0)$.
Dopo un passo avrò: $\vec{p}(1)=\left( 0, \frac{1}{2}, 0, \frac{1}{2} \right)$.
Dopo due passi avrò: $\vec{p}(2)=\left( \frac{1}{2}, 0, \frac{1}{2}, 0 \right)$.
E così via:
$\vec{p}(3)=\left( 0, \frac{1}{2}, 0, \frac{1}{2} \right)$ ecc...
il limite per $t\to \infty$ non converge alla distribuzione stazionaria, $\vec{\pi}=\left( \frac{1}{4}, \frac{1}{4}, \frac{1}{4}, \frac{1}{4} \right)$.
Se fossi partito dalla distribuzone stazionaria ci sarei rimasto.
Dunque posso concludere che la convergenza dipende anche dalle condizioni iniziali e che l'esistenza di una sitribuzione stazionaria non basta a garantirne la convergenza.

**Lezione Associata:** [[6.Catene di Markov discrete]]