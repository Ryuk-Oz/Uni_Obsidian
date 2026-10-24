
**Prerequisito:** [[Potenze e radici complesse]]

Iniziamo dallo studio di una classe di integrali in particolare:
$$
	I(\alpha)=\int_{0}^\infty dx\, x^\alpha R(x); \quad R(x)=\text{funzione razionale}
$$
Studiamo prima un esempio concreto per poi considerare il caso generale.
$$
	I(\alpha)=\int^{+\infty}_{0}dx\, \frac{x^{\alpha-1}}{1+x}
$$
Per prima cosa dobbiamo occuparci di studiare l'esistenza dell'integrale.
$$
	\begin{cases}
	\text{all'}\infty:\;\mathrm{Re}(\alpha-2)<-1\\ \\
	\text{a }0:\, \mathrm{Re}(\alpha-1)<-1
	\end{cases}\implies 0<\mathrm{Re}(\alpha)<1
$$
Non devo fare studi ulteriori sui poli di $\frac{1}{1+x}$ perchè sto valutando l'integrale tra 0 e $\infty$ dove la funzione è sempre regolare.
A questo punto considero un secondo integrale, uguale all'altro ma su variabile complessa.
$$
	J(\alpha)=\oint_{\Gamma}dz\, \frac{z^{\alpha-1}}{1+z}
$$
dove la curva $\Gamma$ è quella rappresentata in figura.

![[Pasted image 20261008231659.png]]

Adesso, esistono 2 modi per calcolare questo integrale, usandoli entrambi possiamo ottenere la soluzione dell'integrale di partenza $I(\alpha)$.
1. Uso il teorema dei residui.
$$
	J(\alpha)=2\pi i \sum_{\text{sing. al finito}} \text{Res}[f(x)]=2\pi i\text{Res}[f(z)]_{-1}=2\pi i\lim_{ z \to -1 } z^{\alpha-1}
   $$
   In generale il numeratore è polidromo: 
   $$
	z^{\alpha-1}=|z|^{\alpha-1}e^{ i\theta(\alpha-1) }e^{ i 2 \pi n(\alpha-1) }=\frac{1}{z}|z|^\alpha e^{ i\theta \alpha }e^{ i 2\pi n \alpha }
   $$
   la curva $\Gamma$ mi va a fissare il taglio, in questo caso $0\leq \theta< 2\pi$.
$$
	z^{\alpha-1}|_{z=-1}=-e^{ i\pi \alpha }e^{ i 2\pi n\alpha }\implies J(\alpha)=-2\pi ie^{ i\pi \alpha }e^{ i 2\pi n \alpha }
   $$

2. Studio $J(\alpha)$ come il limite per $\varepsilon\to 0$ e $R\to \infty$ di $\Gamma$:$$
	J(\alpha)=\underset{R\to \infty}{\lim_{ \varepsilon \to 0 } }\int_{\Gamma_{\varepsilon R}}f(z)dz=\underset{R\to \infty}{\lim_{ \varepsilon \to 0 } }\left[ \int^R_{\varepsilon}f_{+}(z)dz +\int_{C_{R}}f(z)dz+\int_{R}^\varepsilon f_{-}(z)dz-\int_{C_{\varepsilon}}f(z)dz\right]
   $$
   All'interno di tale limite gli integrali sulle due circoncerenze tendono a $0$ in quanto rispettano le condizioni del lemma di Jordan (all'$\infty$ $f$ va a zero più velocemente di $\frac{1}{z}$ e a $0$ si annulla più velocemente di $z$).   $$
	\begin{aligned}
	\implies J(\alpha)&=\underset{R\to \infty}{\lim_{ \varepsilon \to 0 } }\left[ \int^R_{\varepsilon}f_{+}(z)dz +\int_{R}^\varepsilon f_{-}(z)dz\right]=\int_{0}^\infty dz\,(f_{+}(z)-f_{-}(z))\\
	&=\int_{0}^\infty dx\, \frac{x^{\alpha-1}}{1+x}e^{ i 2\pi n(\alpha-1) }(1-e^{ i 2\pi(\alpha-1) })\underset{\text{foglio 0}}{=}\int^\infty_{0}dx\, \frac{x^{\alpha-1}}{1+x}(1-e^{ i 2\pi \alpha })\\
	&=I(\alpha)(1-e^{ i 2\pi \alpha })
	\end{aligned}
   $$
  alla fine abbiamo considerato solo il foglio 0 perchè le funzioni in campo reale vivono sul foglio zero.
$$
	I(\alpha)=\frac{J(\alpha)}{1-e^{ i 2\pi \alpha }}
   $$
   se $J(\alpha)$ lo sappiamo calcolare coi residui.
$$
	I=-\frac{2\pi ie^{ i\pi \alpha }}{1-e^{ i 2\pi \alpha }}=\frac{2\pi i}{e^{ -i\pi \alpha }-e^{ i\pi \alpha }}=\frac{\pi}{\sin \pi \alpha}
   $$
   Il risultato finale è reale, come ci aspettiamo da un integrale che nasce su $\mathbb{R}$.

A questo punto andiamo a descrivere il processo nel caso più generale:
$$
	I(\alpha)=\int_{0}^\infty dx\, x^\alpha R(x); \quad R(x)=\text{funzione razionale}
$$
1. Studio l'esistenza dell'integrale: 
   $$
   	\begin{aligned}
	R(x)&\underset{x\to \infty}{\sim}Ax^k \quad f\sim x^{\alpha} \to \mathrm{Re}(\alpha+k)<-1\\
	R(x)&\underset{x\to 0}{\sim}Ax^l \quad f \sim x^\alpha \to \mathrm{Re}(\alpha+l)>-1	\end{aligned}
   $$
2. Scelgo $\Gamma$ e calcolo l'integrale ausiliario $J(\alpha)$ nei 2 diversi modi, prima coi residui, poi come:
   $$
   	J(\alpha)=\int_{0}^\infty dz(f_{+}-f_{-})=\int_{0}^\infty dz\, (x^\alpha R(x)-x^\alpha R(x)e^{ i 2\pi \alpha })= I(\alpha)(1-e^{ i 2\pi \alpha })
   $$
   Alla fine otteniamo:
$$
	I(\alpha)= \frac{1}{1-e^{ i 2\pi \alpha }}\sum_{\text{al finito}} \text{Res}[z^\alpha R(z)|_{0}]
$$

**Lezione Associata:** [[3.Soluzione ad integrali reali sfruttando funzioni polidrome]]
