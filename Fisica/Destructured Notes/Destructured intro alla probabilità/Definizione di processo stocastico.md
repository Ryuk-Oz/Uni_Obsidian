
Le leggi cinematiche classiche sono descritte da equazione differenziali:
$$
	\frac{dx}{dt}=F(x)
$$
Evoluzione temporale di un sistema data dalle condizioni iniziali.

I processi stocastici sono analoghi ma c'è anche una dipendenza da una variabile aleatoria.
$$
	\frac{dx}{dt}=F(x,u) \qquad \text{con }u \text{ variabile aleatoria}
$$
In questo caso la soluzione, data una condizione iniziale, smette di essere unica.
Cerco la probabilità di trovare una certa soluzione a un dato tempo:
$$
	P(x),t = \begin{cases}
	x(0) \overset{u^{(1)}}{\to} x_{1} (t) \\
	\dots \\
	x(0)\overset{u^{(n)}}{\to}x_{n}(t)
	\end{cases}
$$
Formalizziamo meglio cosa succede da un punto di vista matematico: in analogia con eventi deterministici studiamo la variazione tremporale di una quantità, in questo caso studiamo come la probabilità varia nel tempo. Analogamente al caso deterministico, ogni evento dipende dall'evento precedente.

I processi stocastici sono definibili in più categorie:
- **Catene di Markov**, sia lo stato $x$ che il tempo $t$ sono discreti, l'esempio classico è l'evoluzione di una popolazione
- **Master Equation**, stato discreto ma tempo continuo
- **Processi stocastici continui** (ed equazione di Fokker-Planck), in cui sia lo stato $x$ che il tempo $t$ sono variabili continue. (Processi di questo tipo furono introdotti per primi da Einstein nel 1906).

**Lezione Associata:** [[5. Moto Browniano e Random Walk]]