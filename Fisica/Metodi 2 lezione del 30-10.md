
Nota:
$$
	\zeta(-1)=-\frac{1}{2}B_{2}=-\frac{1}{12}=\sum_{n\geq{0}}n
$$
### Relazioni funzionali per la funzione $\zeta$.

Definisco il seguente integrale:
$$
	I_{N}=\int_{C_{N}} \frac{z^{s-1}}{e^{ z }-1} dz
$$
Dove il cammino $C_{N}$ è il cammino con cerchi concentrici usato per risolvere integrali di funzioni razionali combinate con potenze complesse con punti di diramazione in $0$ e $\infty$.
Poniamo il raggio $R$ della circonferenza esterna pari a:
$$
	R=(2N+1)\pi
$$
![[Pasted image 20261031103102.png]]

La funzione integranda ha poli in $e^{ z }=1 \iff z_{\pm n}=\pm 2\pi in=\begin{cases}2\pi e^{ i \pi/2 }n \\  2\pi e^{ i3\pi/2 }n\end{cases} \, n\in \mathbb{N}$.
Infatti: 
$$
	e^{ z }-1 \underset{z\to z_{+n}}{\sim} 0+ 1\cdot(z-z_{+n})+O((z-z_{+n})^2)
$$
Risolviamo l'integrale col teorema dei residui:
$$
	\begin{aligned}
	I&=\underbrace{-}_{\text{senso orario}} 2\pi i \sum^N_{n=1} \left[ \lim_{ z \to z_{+n} }\left( (z-z_{+n})\, \frac{z^{s-1}}{e^{ z }-1} \right)  +\lim_{ z \to z_{-n} } \left( (z-z_{-n})\, \frac{z^{s-1}}{e^{ z }-1} \right) \right]\\
	&=-2\pi i \sum^N_{n=1} [(2\pi n)^{s-1} e^{ i\pi/2\,(s-1) }+(2\pi n)^{s-1}e^{ i 3\pi/2\, (s-1) }]
	\end{aligned}
$$
Possiamo riscrivere questo integrale in modo alternativo:
$$
	\begin{cases}
	e^{ i \pi/2 \, (s-1)}=e^{ i\pi s/2} (-i)=\frac{e^{ i\pi s }e^{ -i\pi s/2 }}{i} \\
	e^{ i 3\pi/2\, (s-1) }=e^{ i 3\pi/2 }(i)=-\frac{e^{ i\pi s }e^{ -i\pi s/2 }}{i}
	\end{cases}\implies I_{N}=2\pi e^{ i\pi s } \sum^N_{n=1} (2\pi n)^{s-1}(e^{ i\pi s/2 }-e^{ -i\pi s/2 })
$$
Raccogliendo in un seno otteniamo:
$$
	I_{N}=4\pi i (2\pi)^{s-1} e^{ i\pi s } \sin \left( \frac{\pi}{2}s \right)\sum^N_{n=1} n^{s-1}
$$
Tuttavia questo non è l'unico modo di risovere l'integrale.
Posso infatti scomporre $C_{N}=C_{HN}+\Gamma_{N}$ cove $C_{HN}$ è quasi un cammino di Henkel, fatto dalla circonferenza piccola e dai due pezzi rettilinei, e $\Gamma_{N}$ è la circonferenza grande.
$$
	I_{N}=\int_{\Gamma_{N}} fdz+\int_{C_{HN}} f dz
$$
Dunque:
$$
	\int_{\Gamma_{N}} fdz+\int_{C_{HN}} f dz = 4\pi i (2\pi)^{s-1} e^{ i\pi s } \sin \left( \frac{\pi}{2}s \right)\sum^N_{n=1} n^{s-1}
$$
Mandando $N\to \infty$ abbiamo che la serie converge a $\zeta(1-s)$ per $\mathrm{Re}(s)<0$, ulteriormente si può dimostrare che $\int_{\Gamma_{N}}\to{0}$. L'integrale su $C_{HN}$ diventa un integrale sul contorno di Henkel, che sappiamo calcolare.
$$
	I(s)=\int_{C_{H}}=dz \, \frac{z^{s-1}}{e^{ z }-1}=e^{ i\pi s } 2\pi i \frac{\zeta(s)}{\Gamma(1-s)}
$$
Dunque otteniamo:
$$
	e^{ i\pi s } 2\pi i \frac{\zeta(s)}{\Gamma(1-s)} = 4\pi i (2\pi)^{s-1} e^{ i\pi s } \sin \left( \frac{\pi}{2}s \right)\zeta(1-s)
$$
Cioè:
$$
	\zeta(s)= (2\pi)^{s-1} 2 \sin\left( \frac{\pi s}{2} \right) \Gamma(1-s) \zeta(1-s)
$$
Tale rappresentazione ha validità in $\mathbb{C}-\{ \mathrm{Re}(s) \in [0,1] \}$ nel senso della continuazione analitica. La fascia in cui $\zeta$ non è definita viene detta fascia critica.

Studiamo questa rappresentazione della $\zeta$ intorno ad alcuni punti.

- $\zeta(s) \underset{s\to1}{\sim}2 \frac{1}{1-s} \zeta(1-s)\sim \frac{a}{s-1}$ perchè $\zeta(0)=-\frac{1}{2}$ e $\Gamma(z) \underset{z\to{0}}{\sim} \frac{1}{z}$
- $\zeta(s)\underset{s\to 2n}{\sim}2^{2n} \pi^{sn-1} \underbrace{\sin\left( \frac{\pi}{2}s \right) \Gamma(1-s)}_{\text{finita}}\zeta(1-s)$. Infatti:
$$
	\begin{cases}
	\Gamma(1-s)= \frac{\Gamma(m+1-s)}{(1-s)\dots(m-s)} \overset{m=2n}{=} \frac{\Gamma(2n+1-s)}{(1-s)\dots(2n-s)} \overset{s\to{2}n}{\sim} \frac{(-1)^{2n}\Gamma(1)}{(2n-1)(2n-2)\dots(s-2n)}= \frac{1}{(2n-1)!(s-2n)} \\
	\sin \left( \frac{\pi s}{2} \right) \overset{s\to{2}n}{\sim} \cos\left( \frac{\pi s}{2} \right) \frac{\pi}{2} (s-2n)=(-1)^n \frac{\pi}{2} (s-2n)
	\end{cases}
$$
  Sostituendo lo sviluppo di trova:
$$
	\zeta(s) \underset{z\to{2}n}{\sim} \frac{2^{2n-1}\pi^{2n}(-1)^n}{(2n-1)!} \zeta(1-2n)
  $$
  Ricordandoci che:
$$
	\zeta(s)=\frac{e^{ -i 2\pi s }}{2i\pi} \Gamma(1-s) I(s)\overset{s=2n}{=} \frac{1}{2\pi i} \Gamma(2n) 2\pi i \frac{1}{2n!} B_{2n} = \frac{B_{2n}}{2n}
  $$
  Troviamo:
$$
	\zeta(2n)= \frac{(2\pi)^n(-1)^n}{2\cdot(2n)!} B_{2n}
  $$
Per $s\to {2}n+1$, non posso dire nulla perchè perchè $\zeta(1-s)=0$ ($B_{2n+1}=0$).

Sempre nella relazione funzionale, possiamo studiare gli zeri di $\zeta(s)$. Da quanto appena studiato inferiamo un assenza di zeri per $\mathrm{Re}(s)>1$. Per $\mathrm{Re}(s)<0$ invece?
$$
	\begin{cases}
	\Gamma(1-s)\neq 0  & \text{sempre} \\
	\sin\left( \frac{\pi}{2}s \right)=0  &  \text{per } s=2m, \; m\in \mathbb{Z} \\
	\zeta(1-s) \neq 0 & \text{perchè per } \mathrm{Re}(1-s)>1 \; \text{non si annulla}
	\end{cases}
$$

Dunque la $\zeta$ ha zeri solo negli interi negativi pari al di fuori della banda $[0,1]$.
All'interno della banda, Riemann ha ipotizzato la presenza di zeri non banali sulla retta $\mathrm{Re}(s)= \frac{1}{2}$.

![[Pasted image 20261031164516.png]]

### Funzione Zeta di Hurwitz

La funzione zeta di Hurwitz è una generalizzazione della funzione zeta di Riemann.
$$
	\begin{aligned}
	&\zeta(a,s)=\sum_{n\geq 1} \frac{1}{(n+a)^s}=\frac{1}{\Gamma(s)}\int_{0}^\infty dz\, \frac{z^{s-1}e^{ -az }}{1-e^{ -z }}=\frac{e^{ -i\pi s }}{2\pi i} \Gamma(1-s)I(a,s)\\
	& \text{con } \; I(a,s)=\int_{C_{H}} \frac{z^{s-1}e^{ -az }}{1-e^{ z }} dz
	\end{aligned}
$$

