
**Prerequisito:** [[Potenze e radici complesse]]

Occupiamoci di un integrale di una funzione razionale moltiplicata per una potenza complessa, con estremi di integrazione finiti (e coi punti di diramazione negli estremi di integrazione).
$$
	I(\alpha)=\int^b_{a} \left( \frac{x-a}{b-x} \right)^\alpha R(x)\,dx
$$
con $a,b \in \mathbb{R}$.
Come prima studiamo prima un esempio, per poi occuparci del caso generale.
$$
	I(\alpha)=\int^1_{0}dx\, \frac{1}{x}\left( \frac{x}{1-x} \right)^\alpha
$$
Per prima cosa vado a verificare l'esistenza dell'integrale:
- vicino a 0 devo avere: $\mathrm{Re}(\alpha)-1>-1$
- vicino a $1$ devo avere: $-\mathrm{Re}(\alpha)>-1$
cioè: $0<\mathrm{Re}(\alpha)<1$.
Definiamo a questo punto un integrale ausiliario sul piano complesso:
$$
	J(\alpha)=\oint_{\Gamma}dz \, \frac{1}{z}\left( \frac{z}{1-z} \right)^\alpha
$$
Scelgo il taglio della funzione polidroma in modo che vada a coincidere sul cammino di integrazione reale. Inoltre mi metto sul foglio "0" così che l'argomento dell'integrale complesso sia la continuazione analitica dell'argomento dell'integrale reale.

![[Pasted image 20261018165221.png]]

Disegno la curva $\Gamma_{\varepsilon}$ tale che $\Gamma=\lim_{ \varepsilon \to 0 }\Gamma_{\varepsilon}$ coincida con il cammino di integrazione reale. Questo porta alla forma "ad osso di cane".

![[Pasted image 20261018165400.png]]

**OSS:** nel limite in cui $\varepsilon\to 0$ all'interno della curva non ci sono singolarità, ma la curva gira in senso orario, pertanto posso calcolare l'integrale come la somma dei residui al di fuori della curva, che corrisponde alla somma di tutti i residui. Nel nostro caso abbiamo solo il residuo all'infinito.
$$
	\implies J(\alpha)=2\pi i \underset{z=\infty}{\text{Res}}[f(z)]
$$
Come nel caso precedente questo non è l'unico modo di calcolare $J(\alpha)$.
$$
	\begin{aligned}
	J(\alpha)&=\lim_{ \varepsilon \to 0 } \left( \int^{1-\varepsilon}_{\varepsilon} f_{+}(z)dz-\int_{C^0_{z}}f(z) dz + \int_{C^1_{z}}f(z)dz+\int^\varepsilon_{1-\varepsilon}f_{-}(z)dz \right)=\\ 
	&=\int^1_{0}(f_{+}(z)-f_{-}(z))\,dz=\int_{0}^1	dx\, f_{+}(x)(1-e^{ i2\pi \alpha })=I(\alpha)(1-e^{ i2\pi \alpha })\end{aligned}
$$
Dove gli integrali sui cerchi si annullano sempre per i valori di $\alpha$ in cui l'integrale esiste.
Le funzioni $f_{+}$ e $f_{-}$ prese sul foglio 0 nel limite in cui mi trovo sul cammino di integrazione $(0,1)$, assumono valori:
$$
	\begin{cases}
	f_{+}=| \frac{z}{1-z}|^\alpha \\
	f_{-}= | \frac{z}{1-z}|^\alpha e^{ i\alpha 2\pi }
	\end{cases}
$$
e troviamo la formula scritta sopra.
Dunque possiamo calcolare:
$$
	I(\alpha)=\frac{2\pi i}{1-e^{ i 2\pi \alpha }}\underset{z=\infty}{\text{Res}}[f(z)]
$$
Ci resta da calcolare il residuo. Per farlo andiamo a sviluppare la funzione all'infinito.
Poichè $f(z)$ ha uno zero semplice all'infinito, possiamo svilupparla con taylor. Scriviamola prima in modo più semplice.
$$
	f(z)=\frac{1}{z}\left( \frac{z}{1-z} \right)^\alpha=\frac{1}{z}\left( \frac{1}{\frac{1}{z}-1} \right)^\alpha=\frac{1}{z}\left[ \frac{(-1)^\alpha}{\left( 1-\frac{1}{z} \right)^\alpha} \right]
$$
Parte di questo lo sappiamo sviluppare:
$$
	\left( 1-\frac{1}{z} \right)^{-\alpha} =\sum_{k=0}^\infty \binom{-\alpha}{k}\left( -\frac{1}{z} \right)^k \sim 1+\frac{\alpha}{z}+\dots
$$
Dunque $\frac{1}{z} \left( 1-\frac{1}{z} \right)^\alpha \sim \frac{1}{z}+\frac{\alpha}{z^2}+\dots$.
Sappiamo che il residuo all'infinito è pari a meno il coefficiente del termine $z^{-1}$ dello sviluppo. Ci resta da capire solo più a cosa corrsiponde di preciso $(-1)^\alpha$.
Il termine $(-1)^\alpha$ esce dalla funzione polidroma e dipende da come varia la differenza tra gli angoli $\varphi_{0}$ e $\varphi_{1}$ andando all'infinito sul foglio zero.
Per la nostra scelta di angoli (cioè per la nostra scelta di far corrispondere il taglio al cammino di integrazione) si ha $\varphi_{0}-\varphi_{1}=\pi \implies(-1)^\alpha=|-1|\cdot e^{ i\pi \alpha }=e^{ i\pi \alpha }$.
Per cui:
$$
	f(z)\sim e^{ i\pi \alpha }\left( \frac{1}{z}+\frac{\alpha}{z^2}+\dots \right)
$$
$$
	\implies\underset{z=\infty}{\text{Res}}[f(z)]=-e^{ i\pi \alpha }
$$
e troviamo:
$$
	I(\alpha)=-2\pi i \frac{e^{ i\pi \alpha }}{1-e^{i 2\pi \alpha }}=\frac{\pi}{\sin(\pi \alpha)}
$$

Occupiamoci ora del caso generale:

$$
	I(\alpha)=\int^b_{a} \left( \frac{x-a}{b-x} \right)^\alpha R(x) \, dx \quad a,b \in \mathbb{R};\, b>a
$$
Per prima cosa verifico l'esistenza dell'integrale, poi scrivo l'integrale ausiliario complesso:
$$
	J(\alpha)=\oint_{\Gamma} dz\, R(z) \left( \frac{z-a}{b-z} \right)^\alpha
$$
Come ho fatto prima scelgo il taglio della funzione polidroma sul cammino di integrazione reale e come curva $\Gamma$ scelgo quella a "osso di cane". In questo modo trovo che:
$$
	J(\alpha)=2\pi i \sum_{\text{tutti}}\text{Res}[f(z)]
$$
Inoltre continua a valere il fatto per cui:
$$
	J(\alpha)=\int^b_{a} dz\, (f_{+}(z)-f_{-}(z))=I(\alpha)(1-e^{ i 2\pi \alpha })
$$
Dunque otteniamo:
$$
	I(\alpha)=\frac{2\pi i}{1-e^{ i 2\pi \alpha }}\sum_{\text{tutti}}\text{Res}[f(z)]
$$

**OSS:** tramire un cambio di variabile "furbo", cioè tramite una trasformazione di Moebius, è sempre possibile ricondursi da questo caso a quello precedente.
$$
\int^b_{a}dx\, R(x)\left( \frac{x-a}{b-x} \right)^\alpha \underset{y=\frac{x-a}{b-x}}{=}\int^\infty_{0} dy\, \frac{b-a}{(1+y)^2}R\left( \frac{a+by}{1+y} \right)y^\alpha=\int^\infty_{0}dy\, R'(y)\,y^\alpha
$$

**Lezione Associata:** [[3.Soluzione ad integrali reali sfruttando funzioni polidrome]]