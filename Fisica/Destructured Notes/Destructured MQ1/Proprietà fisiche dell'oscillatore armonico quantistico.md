
**ESSENZIALE:** [[Proprietà dei polinomi di Hermite]]

Per studiare le soluzioni dell'oscillatore armonico quantistico possiamo sfruttare le proprietà dei polinomi di Hermite.
$$
	\psi_{n}(\xi)=N_{n}H_{n}(\xi)e^{ -(1/2) \xi^2 }
$$
1. **Ortonormalità**
   Le soluzioni formano un sistema ortogonale in $L^2(\mathbb{R})$ che può essere ortonormalizzato.
   La ragione è che i polinomi di Hermite, con una funzione peso adeguata (in questo caso una funzione gaussiana), soddisfano la seguente identità.
$$
	((H_{n}(\xi)))\equiv \int^\infty_{-\infty} d\xi\, e^{ -\xi^2 } H_{n}(\xi)H_{m}(\xi)=h_{n}\delta_{nm}
   $$
   da adesso useremo $(H_{n})$ anzichè $((H_{n}))$.
   Questo risultato può essere verificato andando a calcolare i coefficienti $h_{n}$ tramite l'uso della funzione generatrice dei polinomi di Hermite.
   Definiamo il seguente integrale.
$$
	\begin{aligned}
	I(z_{1},z_{2})&\equiv \sum^\infty_{n,m=0} \frac{z_{1}^n}{n!} \frac{z_{2}^m}{m!} (H_{n}, H_{m})=\\
	&= \sum^\infty_{n,m=0} \frac{z_{1}^n}{n!} \frac{z_{2}^m}{m!} \int_{-\infty}^{\infty}  \, d\xi\, e^{ -\xi^2 } H_{n}(\xi)H_{m}(\xi) =\\ 
	\text{scambio} &\text{ integrale e sommatoria con Fubini-Tonelli}\\
	&=\int_{-\infty}^{\infty}  \, d\xi\, e^{ -\xi^2 } \sum^\infty_{n=0} \frac{z_{1}^n}{n!}H_{n} \, \sum^\infty_{m=0} \frac{z_{2}^m}{m!}H_{m
	}\\
	\text{sfrutto} &\text{ la funzione generatrice dei polinomi di Hermite:}\\
	&=\int_{-\infty}^{\infty}  \, d\xi \, e^{ -\xi^2 } e^{ -z_{1}^2 +2z_{1}\xi} e^{ -z_{2}^2+2z_{2}\xi }=\\
	&=e^{ -z_{1}^2-z_{2}^2 }\int_{-\infty}^{\infty}  \, d\xi \, \exp[-\xi^2+2(z_{1}+z_{2})\xi]=\\
	&=e^{ -z_{1}^2 }e^{ -z_{2}^2 }e^{ (z_{1}+z_{2})^2 }\int_{-\infty}^{\infty}  \, d\xi \, \exp[-(\xi-(z_{1}+z_{2}))^2]=\\
	&=\sqrt{ \pi } e^{ 2z_{1}z_{2} }=\sqrt{ \pi }\sum^\infty_{n=0} \frac{(2z_{1}z_{2})^n}{n!}
	\end{aligned}
   $$
   Uguagliando l'inizio e la fine dell'integrale abbiamo:
$$
	\sum^\infty_{n,m=0} \frac{z_{1}^n}{n!} \frac{z_{2}^m}{m!} (H_{n},H_{m})=\sqrt{ \pi }\sum^\infty_{n=0} 2^n \frac{(z_{1}z_{2})^n}{n!}
$$
   Allora:
$$
	(H_{n},H_{m})=0 \quad \text{per } n\neq m \qquad\text{e} \qquad (H_{n},H_{m})=h_{n}=\sqrt{ \pi }\,n!\,2^n \quad \text{per } n=m
$$
   A questo punto è banale normalizzare la funzione d'onda.
$$
	\begin{aligned}
	1&=\int_{-\infty}^{\infty}  \, dx \, \lvert \psi_{n}(x) \rvert ^2 = \lvert N_{n} \rvert ^2 \int_{-\infty}^{\infty}  \, dx \, e^{ -\alpha x^2 } (H_{n}(\alpha x))^2 \\
	&=\frac{|N_{n}|^2}{\alpha}\int_{-\infty}^{\infty}  \, d\xi \, e^{ -\xi^2 }(H_{n}(\xi))^2 = \frac{|N_{n}|^2}{\alpha}\sqrt{ \pi }\,n!\,2^n\\
	&\implies N_{n}=\sqrt{ \frac{\alpha}{\sqrt{ \pi }\,2^nn!} } 
	\end{aligned}
$$
2. **Calcolo dei valori medi e delle relazioni di indeterminazione**
   Tramite ragionamenti sulla parità delle funzioni in gioco si ottiene facilemente (sto integrando in un intervallo simmetrico funzioni dispari):
$$
	\langle x \rangle _{n} \equiv \int_{-\infty}^{\infty}  \, dx \, \psi^*_{n} x\psi_{n}=0
   $$
$$
	\langle p \rangle _{n}\equiv \int_{-\infty}^{\infty}  \, dx \, \psi^*_{n}\, \left( -i \hbar \frac{d}{dx} \right)\, \psi_{n}=0
   $$
   Il calcolo dei momenti quadri non è altrettanto banale.
$$
	\begin{aligned}
		\langle x^2 \rangle _{n} &\equiv \int_{-\infty}^{\infty}  \, dx \, x^2\, (\psi_{n}(x))^2 = N_{n}^2 \int_{-\infty}^{\infty}  \, dx\,e^{ -\alpha^2 x^2}H_{n}^2(x) x^2 =\\
		&=\frac{N_{n}^2}{\alpha^3} \int_{-\infty}^{\infty}  \, d\xi \, e^{ -\xi^2 } \xi^2  H_{n}^2(\xi)
	\end{aligned}
   $$
   Per calcolare l'integrale possiamo sfruttare la relazione di ricorrenza dei polinomi di Hermite.
   $$
	\xi H_{n}(\xi)=\frac{1}{2} H_{n+1}(\xi)+nH_{n-1}(\xi)
   $$
   Da questa otteniamo: 
$$
	[\xi H_{n}(\xi)]^2 = \frac{1}{4} H^2_{n+1}(\xi)+n^2 H_{n-1}^2(\xi)+\text{termini dispari che si annullano nell'integrale}
   $$
   Dunque: 
$$
	\begin{aligned}
	\langle x^2 \rangle _{n} &= \frac{N_{n}^2}{\alpha^3} \left( \frac{1}{4}h_{n+1} +n^2h_{n-1}\right)=\\
	&= \frac{1}{\alpha^2} \frac{1}{\sqrt{ \pi }2^nn!}\left( \frac{1}{4} \sqrt{ \pi } 2^{n+1} (n+1)!+n^2 \sqrt{ \pi }2^{n-1}(n-1)! \right)=\\
	&= \frac{1}{\alpha^2} \left( \frac{1}{2}(n+1)+\frac{n}{2} \right)=\frac{\hbar}{m\omega}\left( n+\frac{1}{2} \right) 
	\end{aligned}
   $$
   Per calcolare il momento quadro dell'impulso potremmo integrare con la forza bruta, tuttavia esiste un modo molto più veloce che fa uso del teorema di Ehrenfest.
   Ricordiamo la definizione dell'energia potenziale elastica:
$$
	\langle V(x) \rangle _{n}=\frac{1}{2} m\omega^2 \langle x^2 \rangle _{n}=\frac{1}{2}\left( n+\frac{1}{2} \right)\hbar \omega = \frac{E_{n}}{2}
   $$
   Per il teorema del viriale abbiamo:
$$
	\frac{1}{2m}\langle p^2 \rangle _{n}=\langle T \rangle _{n}=\langle E-V(x) \rangle _{n}=\frac{E_{n}}{2}
   $$
   Dunque:
$$
	\langle p^2 \rangle _{n}=m\left( n+\frac{1}{2} \right)\hbar \omega
   $$
   A questo punto possiamo verificare la relazione di indeterminazione:
$$
	(\Delta x)_{n}(\Delta p)_{n}=\sqrt{ \langle x^2 \rangle _{n} }\sqrt{ \langle p^2 \rangle _{m} }=\sqrt{ \left( n+\frac{1}{2} \right) \frac{\hbar}{m\omega} }\sqrt{ \left( n+\frac{1}{2} \right)\hbar m\omega}=\left( n+\frac{1}{2} \right)\hbar
   $$
   Lo stato di minima energia è quello che minimizza questao prodotto, cioè $\psi_{0}(x)$ che è una funzione gaussiana e ha $(\Delta x \Delta p)_{0}=\frac{\hbar}{2}$.

**Lezione Associata:** [[4.Oscillatore armonico quantistico]]