
**Prerequisiti:** alcune delle proprietà della funzione Digamma:
[[Definizione e proprietà della funzione Digamma]]

La funzione $\psi(z)$ calcolata in $z=1$ è una costante, $\gamma$, che prende il nome di costante di Eulero-Mascheroni.
$$
	\psi(1)=\Gamma'(1)=-\gamma=0.577\dots
$$
Da qui possiamo facilmente calcolare il valore della funzione Digamma in interi e seminteri:
$$
	\psi(n+1)=\frac{1}{n}+\psi(n)=\frac{1}{n}+\frac{1}{n-1}+\psi(n-1)+\dots=\sum^n_{k=1} \frac{1}{k}-\gamma
$$
Per $z=\frac{1}{2}$ possiamo scrivere:
$$
	\psi\left( \frac{1}{2} \right)+\psi(1)+2\log 2 =2\psi(1)
$$
Da cui:
$$
	\psi\left( \frac{1}{2} \right)=-\gamma-2\log2
$$
Per seminteri generici:
$$
	\psi\left( z+\frac{1}{2} \right)=\frac{1}{n-\frac{1}{2}}+\psi\left( n-\frac{1}{2} \right)=\dots=2\sum^n_{k=1} \frac{1}{2k-1} -\gamma-2\log 2
$$


**Lezione associata:** [[5. Funzione Digamma]]