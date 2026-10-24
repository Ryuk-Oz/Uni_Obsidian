
Consideriamo la soluzione generale all'oscillatore armonico quantistico e introduciamo una condizione iniziale interessante:
$$
	\psi(x,t)=\sum^\infty_{n=0} c_{n} \psi_{n}(x)e^{ -\frac{i}{\hbar} E_{n}t }\underset{E_{n}=\left( n+\frac{1}{2} \right)\hbar \omega}{=}e^{ -i\omega t/2 }\sum^\infty_{n=0}c_{n}\psi_{n}(x)e^{ -in\omega t }
$$
Prendo come condizione iniziale la gaussiana normalizzata e centrata in $x=x_{0}$:
$$
	\psi(x,0)=\sqrt{ \frac{\alpha}{\sqrt{ \pi }} } \exp\left[ -\frac{1}{2}\alpha^2(x-x_{0})^2 \right]
$$
Studiamo l'evoluzione temporale di tale pacchetto (cioè ne determiniamo i coefficienti $c_{n}$).
$$
	\begin{aligned}
	c_{n}&=(\psi_{n},\psi)=\int_{-\infty}^{\infty}  \, dx \, \psi^*_{n}(x)\psi(x,0)=\frac{N_{n}}{\alpha}\int_{-\infty}^{\infty}  \, d\xi \, H_{n}(\xi) e^{ -(1/2)\xi^2 } \sqrt{ \frac{\alpha}{\sqrt{ \pi }} } e^{ -(1/2)(\xi-\xi_{0})^2 }=\\
	&=\frac{1}{\sqrt{ \pi 2^n n! }}\int_{-\infty}^{\infty}  \, d\xi \,H_{n}(\xi)\exp\left[ -\frac{1}{2}\xi^2 -\frac{1}{2}(\xi-\xi_{0})^2\right]\equiv\\
	&\equiv \frac{1}{\sqrt{ \pi 2^n n!}} I_{n}(\xi_{0})
	\end{aligned}
$$
Possiamo calcolare questo integrale in forma chiusa sfruttando la funzione generatrice $S(z,\xi)$.
Definiamo:
$$
	\begin{aligned}
	I(z,\xi_{0})&\equiv \sum^\infty_{m=0} \frac{z^m}{m!} \int_{-\infty}^{\infty}  \, d\xi \,H_{n}(\xi) \exp\left[ -\frac{1}{2}\xi^2-\frac{1}{2}(\xi-\xi_{0})^2 \right]=\sum^\infty_{m=0} \frac{z^m}{m!} I_{m}(\xi_{0})=\\
	&= \int_{-\infty}^{\infty}  \, d\xi \, S(z,\xi) \exp\left[ -\frac{1}{2}(\xi-\xi_{0})^2-\frac{1}{2}\xi^2 \right]=\\
	&= \int_{-\infty}^{\infty}  \, d\xi \, \exp\left[ -z^2+2z\xi-\xi^2+\xi \xi_{0}-\frac{1}{2}\xi_{0}^2 \right]=\\
	&=e^{ \frac{1}{2}\xi_{0}^2-z^2 } \int_{-\infty}^{\infty}  \, d\xi \exp \underbrace{\left[-\xi^2+2\xi\left( z+\frac{\xi_{0}}{2}\right)\right]}_{-\left( \xi-z-\frac{\xi_{0}}{2} \right)^2+\left( z+\frac{\xi_{0}}{2} \right)^2} =\\
	&=\sqrt{ \pi } \exp\left[ -\frac{1}{2}\xi_{0}^2 -z^2+z^2+\frac{\xi_{0}^2}{4}+z\xi_{0}\right]=\sqrt{ \pi }\exp\left[ z\xi_{0}-\frac{1}{4}\xi_{0}^2 \right]\\
	&=\sqrt{ \pi } e^{ -\frac{\xi_{0}^2}{4} }\sum^\infty_{m=0} \frac{z^m}{m!} \xi_{0}^m
	\end{aligned}
$$
Dunque:
$$
	I_{m}(\xi_{0})=\sqrt{ \pi } e^{ -\xi_{0}^2/4 } \xi_{0}^m
$$
Ne segue che:
$$
	c_{n}=\frac{1}{\sqrt{ \pi 2^n n! }}\sqrt{ \pi }\xi_{0}^n \exp\left[ -\frac{\xi_{0}^2}{4} \right]
$$
Possiamo quindi scrivere la funzione d'onda al tempo $t$.
$$
	\psi(x,t)=e^{ -(i/2)\omega t }e^{ -(1/4)\alpha^2 x_{0}^2}\sum^\infty_{n=0} \frac{1}{\sqrt{ 2^n n!}} (\alpha x_{0})^n \sqrt{ \frac{\alpha}{\sqrt{ \pi }2^n n!} } H_{n}(\alpha x)e^{ -(1/2) \alpha^2 x^2 }e^{ -in\omega t }
$$
Raccogliamo i termini in modo più furbo.
$$
	\psi(x,t)=\sqrt{ \frac{\alpha}{\sqrt{ \pi }} }\exp\left[ -\frac{1}{2} \alpha^2 x^2-\frac{1}{4} \alpha^2 x_{0}^2-\frac{i}{2}\omega t \right] \underbrace{\sum^\infty_{n=0} \frac{H_{n}(\alpha x)}{n!}\left( \frac{\alpha x_{0}}{2}e^{ -i\omega t } \right)^n}_{S\left( z=\frac{\alpha x_{0}}{2}e^{ -i\omega t }, \alpha x \right)}
$$
Ma sappiamo anche che:
$$
	S\left( z=\frac{\alpha x_{0}}{2}e^{ -i\omega t }, \alpha x \right)=\exp\left[ -\frac{\alpha^2x_{0}^2}{4} e^{ -2i\omega t }+\alpha^2x_{0}x e^{ -i\omega t } \right]
$$
E abbiamo finalmente ottenuto una forma esplicita per $\psi(x,t)$.
$$
	\psi(x,t)=\sqrt{ \frac{\alpha}{\sqrt{ \pi }} }\exp\left[ -\frac{1}{2} \alpha^2 x^2-\frac{1}{4} \alpha^2 x_{0}^2-\frac{i}{2}\omega t -\frac{1}{4}\alpha^2x_{0}^2e^{ -2i\omega t }+\alpha^2x_{0}xe^{ -i\omega t }\right] \equiv \sqrt{ \frac{\alpha}{\sqrt{ \pi }} }\exp[R+iJ]
$$
L'unica parte rilevante al calcolo della probabilità di posizione è la componente reale $R$.
$$
	\begin{aligned}
	R&=-\frac{1}{2}\alpha^2x^2 -\frac{1}{4} \alpha^2 x_{0}^2 (1+\cos{2}\omega t)+\alpha^2x_{0}x\cos \omega t\\
	&=-\frac{1}{2}\alpha^2x^2 -\frac{1}{2}\alpha^2x_{0}^2 \cos^2\omega t+\alpha^2 x_{0}x\cos \omega t=-\frac{1}{2}\alpha^2 (x-x_{0}\cos \omega t)^2
	\end{aligned}
$$
Quindi la densità di probabilità di posizione è:
___
$$
	\rho(x,t)=\frac{\alpha}{\sqrt{ \pi }} \exp[-\alpha^2(x-x_{0}\cos \omega t)^2]
$$
___
Ovviamente per $t=0$ ritroviamo la condizione iniziale.

Da questa forma finale possiamo trarre una conclusione molto interessante:
    Il pacchetto gaussiano oscilla senza allargarsi con la frequenza classica $\omega$ e con ampiezza $x_{0}$

**Oss:** tutti gli stati stazionari contribuiscono alla soluzione ma il contributo maggiore è dato dallo stato stazionario con l'energia corrispondente a quella classica (nel limite di grande $n$).

Verifichiamo questo fatto calcolando il valore massimo assumibile dai coefficienti $c_{n}$ al variare di $n$.
Partiamo dall'energia:
$$
	E_{n}=\left( n+\frac{1}{2} \right)\hbar \omega \equiv \frac{1}{2}m\omega^2x_{0}^2
$$
Nel limite in cui $n\to \infty$ abbiamo:
$$
	n \sim \frac{1}{2\hbar} m\omega x_{0}^2
$$
Passiamo quindi ai coefficienti:
$$
	c_{n}= \frac{1}{\sqrt{ 2^n n! }}(\alpha x_{0})^n e^{ -(\alpha^2x_{0}^2)/4 }
$$
Per semplicità passiamo al logaritmo:
$$
	\ln c_{n}=n\ln \alpha x_{0} - \frac{n}{2}\ln 2 -\frac{1}{2} \ln n!-\frac{1}{4}\alpha^2x_{0}^2
$$
Facciamo uso dell'approssimazione di Stirling: $\ln n! \sim n\ln n-n$ per $n\to \infty$.
Dunque:
$$
	\ln{c_{n}} \underset{n\to \infty}{\sim}n\left( \ln \alpha x_{0}-\frac{1}{2}\ln 2+\frac{1}{2}-\frac{1}{2}\ln n \right)+O(\ln n)
$$
Ne segue che:
$$
	\frac{ \partial \ln c_{n} }{ \partial n }  \sim \ln(\alpha x_{0})-\frac{1}{2}\ln 2+\frac{1}{2}- \frac{1}{2}\ln n-\frac{1}{2}
$$
La derivata si annulla quando:
$$
	\ln n=\ln\left( \frac{\alpha^2x_{0}^2}{2} \right) \implies n=\frac{1}{2} \frac{m\omega}{\hbar}x_{0}^2
$$
Come avevamo precedentemente previsto.
(Vedi quest'ultima parte sul griffith che non mi è chiarissima).

**Lezione Associata:** [[4.Oscillatore armonico quantistico]]