
Studiamo il modello più semplificato di tutti, quello di una buca di potenziale di profondità infinita.

![[Pasted image 20261017111825.png]]

Nelle zone $I$ e $III$ abbiamo che $\beta\to \infty$ perchè il potenziale è infinito nei salti, pertanto ho probabilità nulla di trovare la particella in una regione classicamente proibita. 
$$
	\psi_{I}(x)=\psi_{III}=0
$$
Occupiamoci dunque dello studio della sola regione permessa.
$$
	\frac{d^2\psi}{dx^2}+k^2\psi(x)=0
$$
cerchiamo soluzioni reali, quindi scriviamo la soluzione generale in termini di seni e coseni anzichè di esponenziali.
$$
	\psi(x)=A\sin kx+B\cos kx \quad \text{con } k=\sqrt{ \frac{2mE}{\hbar^2} }
$$
Imponiamo la continuità di $\psi(x)$, poichè il gradino di potenziale è infinito, non facciamo alcunchè sulla derivata.
$$
	\begin{cases}
	\psi(0)=0=B \\
	\psi(a)=0=A\sin(ka) \implies ka=n\pi \text{ e } k_{n}=\frac{n\pi}{a}; \, n\in \mathbb{N}, \, n\neq_{0}
	\end{cases}
$$
Cioè, abbiamo fissato i 2 estremi, trovando come soluzione un'onda stazionaria.
$$
	\psi_{n}(x)=A\sin\left( \frac{n\pi}{a}x \right)
$$
Cerchiamo la costante $A$ normalizzando. (NOTA BENE: Dopo aver imposto la continuità devo sempre trovare una costante libera che poi andrò a ricavare imponendo la normalizzazione).
$$
	\begin{aligned}
	1&=\int_{0}^adx\,|A|^2\sin^2\left( \frac{n\pi}{a}x \right) \\
	&=|A|^2 \frac{a}{2} \implies A=\sqrt{ \frac{2}{a} }
	\end{aligned}
$$
Dunque la funzione d'onda finale è:
$$
	\psi_{n}(x)=\sqrt{ \frac{2}{a} }\sin\left( \frac{n\pi}{a}x \right)
$$
I livelli energetici permessi sono invece:
$$
	E_{n}=\frac{k_{n}^2\hbar^2}{2m}= \frac{(n\pi \hbar)^2}{2ma^2}
$$
Cioè le particelle legate ammettono uno spettro discreto.

Osservazioni varie sulle soluzioni ottenute:
- Le $E_{n}$ sono non degeneri, come ci aspoettiamo dagli autovalori di $\hat{H}$
- Le $\psi_{n}$ hanno parità definita rispetto al centro della buca, come atteso
- Le $\psi_{n}$ hanno $n+1$ nodi tra le barrire della buca. 
- La soluzione per $n=0$ non è accettabile altrimenti avrei $E_{0}=0$ e la particella sarebbe ferma, cioè la particella avrebbe posizione e impulsi ben definiti, il che viola il principio di indeterminazione.
- Nel limite classico ho: $E_{n+1}-E_{n}=\frac{\pi^2\hbar^2}{2ma^2}[(n+1)^2-n^2]=\frac{\pi^2\hbar^2}{2ma^2}(2n+1)$ 
  $\implies \frac{E_{n+1}-E_{n}}{E_{n}}=o\left( \frac{1}{n} \right)$. Per oggetti microscopici ho $n\gg{1}$, dunque non vedo la differenza tra gli spettri energetici e lo spettro mi sembra continuo.

Come varia l'interpretazione probabilistica nel limite classico? Osserviamo graficamente la situazione quantistica e classica a confronto:

![[Pasted image 20261017115651.png]]

cioè $\rho_{\text{classica}}=\frac{1}{a}$. Ora prendiamo la densità di probabilità quantistica e mandiamola a infinito, poi calcoliamo il valore medio.

![[Pasted image 20261017115829.png]]

Abbiamo riottenuto il risultato classico.

A questo punto, sappiamo che la soluzione generale all'EdS per potenziali per buche di potenziale infinite è:
$$
	\psi(x,t)=\sum_{n=1}^\infty C_{n}\psi_{n}(x)e^{ -\frac{i}{\hbar}E_{n}t }
$$
Possiamo dimostrare che questa soluzione trovi effettivamente tutte le soluzioni del caso che abbiamo studiato? Dall'analisi discreta di Fourier sappiamo che seni e coseni formano una base di $L^2(0,a)$ pertanto siamo sicuri che in questo modo sia possibile trovare tutte le soluzioni.
Non solo, $L^2(0,a)$ ammette anche un prodotto scalare, tramite cui possiamo verificare l'ortogonalità della base:
$$
	\begin{aligned}
	(\psi_{m},\psi_{n})&\equiv \int^a_{0} dx \,\psi^*_{m}(x)\psi_{n}(x)=\frac{2}{a}\int^a_{0}dx \sin\left( \frac{m\pi}{a}x \right)\sin\left( \frac{n\pi}{a}x \right)=\\
	&=\frac{2}{a}\int^a_{0}dx \, \frac{1}{2} \left[ \cos\left( \frac{(m-x)\pi}{a}x\right) -\cos\left( \frac{(n-x)\pi}{a}x \right) \right] =\delta_{mn}
	\end{aligned}
$$
Ulterioremente, con il teorema di Dirichlet, è possibile dimostrare che le due funzioni sono anche ortonormali.


**Lezione Associata:** [[3.Studio di potenziali costanti in d=1]]