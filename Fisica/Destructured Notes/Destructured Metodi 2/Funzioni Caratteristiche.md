
**Def:** Una funzione caratteristica per una variabile aleatoria è una funzione che, presa una qualunque distribuzione di probabilità $p(x)$, detta distribuzione caratteristica, viene definita nel seguente modo:
$$
	\phi_{x}(t)\equiv \int e^{ itx } p(x)\, dx = E[e^{ itx }]
$$
Di fatto si tratta della trasformata di fourier della distribuzione, normalizzata.
Per quanto già ampiamente discusso nei corsi di metodi abbiamo che:
$$
	p(x)\equiv \frac{1}{2\pi} \int e^{ -itx } \phi_{x}(t) dt
$$
Consideriamo ora $N$ variabili aleatorie indipendenti $x_{1},x_{2},\dots x_{N}$; dotate di funzione caratteristica $\phi_{x_{i}}(t)$.
La somma delle variabili aleatorie $z=x_{1}+x_{2}+\dots+x_{N}$ ha comne funzione caratteristica:
$$
	\phi_{z}(t) = \prod^N_{j=1} \phi_{j}(t) = E(e^{ it(x_{1}+\dots+x_{N}) })=E(e^{ itx_{1} },\dots,e^{ itx_{N} })
$$
Poichè abbiamo preso le variabili indipendenti otteniamo ulteriormente:
$$
	\phi_{z}(t)=E(e^{ itx_{1} })E(e^{ itx_{2} })\dots E(e^{ itx_{N} })
$$
Se $y=ax+b$ abbiamo:
$$
	\phi_{y}(t)=e^{ itb }\phi_{x}(at)
$$
La dimostrazione di questo fatto è banale.

**Lezione Associata:** [[4.Distribuzioni di Probabilità continue (di variabili aleatorie)]]