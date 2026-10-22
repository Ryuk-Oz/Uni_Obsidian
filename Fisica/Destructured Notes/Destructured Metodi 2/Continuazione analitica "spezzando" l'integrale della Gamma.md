
**Utile da rivedere:** [[Continuazione analitica]]

Un altro modo per continuare analiticamente la funzione $\Gamma$ è quello di spezzarla in 2 integrali:
$$
	\Gamma(z)=\underbrace{\int^1_{0} e^{ -t }t^{z-1} dt}_{P(z)}+\underbrace{\int_{1}^\infty e^{ -t }t^{z-1}dt}_{Q(z)}
$$
La funzione $Q(z)$ è analitica ovunque, dunque possiamo studiare i problemi di $\Gamma$ nel semipiano negativo andando a studiare come si comporta $P(z)$.
Andiamo a sviluppare $P(z)$ nel proprio dominio di convergenza
$$
	P(z)=\int^1_{0} dt\, t^{z-1} \underbrace{\sum^\infty_{k=0} \frac{(-1)^k}{k!}t^k}_{\text{converge uniformemente}}
$$
Visto che la serie converge uniformemente posso scambiare la serie con l'integrale.
$$
\begin{aligned}
P(z)&=\sum^\infty_{k=0} \frac{(-1)^k}{k!} \int^1_{0} dt \, t^{z+k-1}=\\
&=\sum^\infty_{k=0} \frac{(-1)^k}{k!} \frac{t^{z+k}}{z+k}|^{^1}_{_{0}}
\end{aligned}
$$
Scambiando sommatoria e integrale posso riscrivere $P(z)$ in una somma di termini che esistono per ogni valore di $z$ tale che $\mathrm{Re}(z+k)>0$. Cioè ho trovato una nuova continuazione analitica di $\Gamma(z)$.
$$
	P(z)=\sum^\infty_{k=0} \frac{(-1)^k}{k!} \frac{1}{z+k}
$$
Siamo riusciti a riscrivere $P(z)$ come una somma infinita di termini ciascuno dei quali ha un polo semplice in un intero negativo.

![[Pasted image 20261021150457.png]]

Si vede ad occhio come $P(z)$ sia analitica ovunque tranne che in questi poli.
Posso sempre andare a studiare il residuo di $P(z)$ studiandone lo sviluppo:
$$
	P(z) \underset{z=-n}{\to}(-1)^n\frac{1}{n!} \frac{1}{z+n}+\underbrace{\Omega(z+n)}_{\text{funzione analitica in } z=-n}
$$
Questo mette in evidenza la formula per il residuo: $\text{Re}= \frac{(-1)^n}{n!}$.
Anche $\Gamma(z)$ segue esattamente lo stesso pattern, basta aggiungere $Q(z)$ a $\Omega$ ottenendo una nuova funzione analitica $\tilde{\Omega}$.
$$
	\Gamma(z) \underset{z=-n}{\to} (-1)^n\frac{1}{n!} \frac{1}{z+n}+\underbrace{\tilde{\Omega}(z+n)}_{\text{funzione analitica in } z=-n}
$$


**Lezione associata:** [[4.Funzione Gamma di Eulero]]