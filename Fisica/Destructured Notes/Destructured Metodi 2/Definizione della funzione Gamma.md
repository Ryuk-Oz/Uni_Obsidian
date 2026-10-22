
La funzione $\Gamma$ è una "generalizzazione" del fattoriale, ed esistono vari modi per rappresentarla. Iniziamo dalla rappresentazione "standard", quella integrale.
Per farlo, partiamo dalla risoluzione in campo reale di un integrale il cui risultato è noto:
$$
	\begin{aligned}
	I_{0}&=\int_{0}^\infty e^{ -t }dt=1\\
	I_{1}&=\int_{0}^\infty te^{ -t }dt=-te^{ -t }|_{_{0}}^{^\infty}+\int_{0}^\infty e^{ -t }dt=1\\
	I_{2}&=\int_{0}^\infty t^2 e^{ -t }dt=-t^2e^{ -t }|^{^\infty}_{_{0}}+2\int_{0}^\infty te^{ -t }dt=2I_{1}=2\\
	&\dots\\
	I_{n}&=\int_{0}^\infty t^ne^{ -t }dt=-t^ne^{ -t }|^{^\infty}_{_{0}}+n\int_{0}^\infty t^{n-1}e^{ -t }dt=nI_{n-1}=n(n-1)I_{n-2}=n!
	\end{aligned}
$$
Abbiamo trovato un modo alternativo di definire il fattoriale.
Questo è anche l'unico modo per definire in maniera consistente il valore di $0!$

Cosa succede se considero questo stesso integrale per funzioni complesse qualsiasi?
Ottengo la funzione $\Gamma$ di Eulero.
$$
	\Gamma(z)=\int_{0}^\infty e^{ -t }t^{z-1}dt, \qquad z\in \mathbb{C}
$$
Per $z=n\in \mathbb{N}$ ritrovo il risultato di prima: $\Gamma(n+1)=n!$.
Dunque la funzione Gamma è una "simil continuazione analitica" del fattoriale nel piano complesso