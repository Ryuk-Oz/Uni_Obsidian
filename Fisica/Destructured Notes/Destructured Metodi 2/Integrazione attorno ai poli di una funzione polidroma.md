Studiamo l'integrale attorno a poli di una funzione polidroma analizzando un semplice esempio:
$$
	I=\oint_{\gamma}dz\, \frac{\cos(\pi z)}{\log z-i\pi}; \quad \gamma:|z+1|\leq \frac{1}{2}
$$
Se la curva su cui integro non passa per il taglio allora continua a valere il teorema di Cauchy. Scelgo dunque un taglio che non mi dia fastidio, ad esempio $0\leq \theta\leq 2\pi$

![[Pasted image 20261008225457.png]]

A questo punto, sfruttando le nozioni di Metodi 1 so calcolare l'integrale su ogni foglio. Ma il mio risultato varia tra diversi fogli. Cerchiamo i possibili poli, cioè i punti in cui il denominatore si annulla.
$$
\begin{aligned}
(\log z-i\pi)|_{n}&=\log |z|e^{ i\theta }e^{ i 2\pi n } -i\pi =\log |z|+i\theta+i 2\pi \theta-i\pi\\
\text{cerco i poli} &\implies \log |z|+i\theta+i2\pi \theta-i\pi \overset{?}{=}0
\end{aligned}
$$
Perchè il risultato sia uguale a $0$, i termini dipendenti da $z$ e $\theta$ devono annullarsi separatamente.
$$
	\log |z|=0\implies |z|=1
$$
$$
	i\theta+i 2\pi n-i\pi=0 \implies \theta=\pi-2\pi n
$$
Ma abbiamo detto $0\leq \theta< 2\pi$ pertanto il denominatore si può annullare solo per $n=0$, cioè in $\theta=\pi$, che equivale a $z=-1$. Negli altri fogli il denominatore non si annulla mai.
La funzione è regolare $\forall\,n>0$ e l'integrale si annulla su ognuno di quei piani.
Nel piano $0$ possiamo calcolare l'integrale usando il teorema dei residui.
$$
	\oint dz\dots=2\pi i \text{Res}\left[ \frac{\cos(\pi z)}{\log z+i\pi} \right]=2\pi i \lim_{ z \to -1 } (z+1) \frac{-1}{(-1)(z+1)}=2\pi i
$$
A denominatore abbiamo sviluppato il logaritmo: 
$$\log z+i\pi=(\log z+i\pi)|_{z=-1}+(z+1) \frac{1}{z}|_{z=-1}+\dots=-1(z+1)$$
Alla fine otteniamo che l'integrale vale $2\pi i$ sul primo foglio e 0 in tutti gli altri fogli


**Lezione Associata:** [[2.Funzioni polidrome]]