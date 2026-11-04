

Supponiamo di avere una funzione definita tramite una serie di taylor in $0$.
$$
	f(z)=\sum^\infty_{k=0} a_{k} z^k
$$
con raggio di convergenza $\rho=\lim_{ k \to \infty } |\frac{a_{k}}{a_{k+1}}|$.
Prendo ora $\Phi(z)$ , Trasformata di Borel di $f(z)$:
$$
	\Phi(z)=\sum^\infty_{k=0} \frac{a_{k}}{k!} z^k
$$
Questa serie ha raggio di convergenza infinito:
$$
		\rho=\lim_{ k \to \infty } | \frac{a_{k}}{k!} \frac{(k+1)!}{a_{k+1}}|=\infty
$$
Posso sfruttare questo integrale per continuare analiticamente $f(z)$ tramite il seguente integrale:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } \Phi(zt) \left( =\frac{1}{z} \mathcal{L}_{\frac{1}{z}}(\Phi) \right)
$$
posso dimostrare molto facilmente che per $|z|<\rho$, $I(z)=f(z)$.
$$
	I(z)=\int^\infty_{0} dt \, e^{ -t } \sum^\infty_{k=0} \frac{a_{k}}{k!} t^k z^k = \sum^\infty_{k=0} \frac{a_{k}}{k!}z^k \underbrace{\int^\infty_{0} dt\, e^{ -t }t^k}_{\Gamma(k+1)}=\sum^\infty_{k=0}a_{k}z^k 
$$

Prendiamo ora $f(z)=\sum z^k$. Facciamo nuovamente la trasformata di Borel:
$$
	\Phi(z)=\sum^\infty_{k=0} \frac{z^k}{k!}=e^{z }
$$
Ragionando come prima:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } e^{zt} = \int^\infty_{0}dt \, e^{ -t(1-z) }=\frac{1}{1-z}
$$
In questo modo possiamo trovare continuazioni di $f(z)$ in forma chiusa.

Perchè ci interessa ora? Posso fare ragionamenti analoghi anche con sviluppi asintotici.
Consideriamo uno sviluppo asintotico:
$$
	f(z)=\sum_{k=0}^\infty a_{k}z^k \qquad \text{che non converge}
$$
A questo punto posso fare la trasformata di Borel:
$$
	\Phi(z)=\sum^\infty_{k=0} a_{k} \frac{z_{k}}{k!} \quad \text{generalmente converge in } D
$$
Nel caso in cui la trasformata di Borel converga, posso calcolare $I(z)=f(z)$, "continuazione analitica dello sviluppo asintotico". $f(z)$ è lo sviluppo asintotico di $I(z)$.
In questo caso si dice che la serie è sommabile alla Borel.

Facciamo un esempio concreto.
$$
	f(z)=\sum^\infty_{k=0} k! (-1)^k z^k \implies \Phi(z)=\sum^\infty_{k=0}(-1)^k z^k =\frac{1}{1+z}
$$
Dunque:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } \frac{1}{1+tz}
$$
è la somma di Borel della mia serie divergente.
Paciocchiamo l'integrale:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } \frac{1}{\frac{1}{z}+t}=\frac{1}{z} \int^\infty_{\frac{1}{z}} dw\, e^{ 1/z \;-\;w } \frac{1}{w}=\frac{1}{z}e^{ 1/z } \int_{\frac{1}{z}}^\infty dw\,\frac{e^{ -w }}{w}=\frac{1}{z}e^{ 1/z } \Gamma\left( 0, \frac{1}{z} \right)
$$
Dove $\Gamma\left( 0, \frac{1}{z} \right)$ è la gamma incompleta (VAI A VEDERLA).
Laddove ci fosse una singolarità/taglio/punto di diramazione sul cammino di integrazione, l'integrale contenente la trasformata di Borel è ill-defined.

Ad esempio:
$$
	f(z)=\sum^\infty_{k=1} (k-1)! z^k\implies \Phi(z)=\sum^\infty_{k=0} \frac{z^k}{k}=-\log(1-z)
$$
$\Phi(z)$ ha un taglio sull'asse reale da $1$ a $\infty$.
$$
	I(z)=-\int^\infty_{0} e^{ -t } \log(1-zt)\,dt
$$
Ho sempre un punto di diramazione sul cammino di integrazione, indipendentemente dalla scelta del taglio. Questo mi inserisce un'ambiguità, il cammino sta sopra o sotto il taglio.
Passando sopra il punto di diramazione trovo $I_{+}$, passando sotto trovo $I_{-}$.
$$
	\Delta I=\int^\infty_{1} e^{ -t } 2\pi i\, dt= e^{ -1/z } 2\pi i
$$
L'ambiguità comincia in $1$, tra $0$ e $1$ non ho differenaa tra il logaritmo sopra e sotto
Dunque $I_{+}$ e $I_{-}$ diffferiscono di un termine che va esponenzialmente a $0$ per $z\to 0$, in totale analogia a quanto avevamo constatato precedentemente su funzioni diverse con lo stesso sviluppo asintotico.

**Lezione Associata:** [[7. Sviluppi Asintotici]]