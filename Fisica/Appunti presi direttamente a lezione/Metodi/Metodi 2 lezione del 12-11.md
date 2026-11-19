
### Metdodo della fase stazionaria

Consideriamo un integrale:
$$
	I(t)=\int^b_{a} e^{ ith(x) }g(x) dx,\quad [a,b]\in \mathbb{R}, \quad h(x),g(x)\in \mathbb{R}
$$
Ma l'esponenziale è complesso $\implies g(x)$ viene integrato con una fase.

Riprendiamo il lemma di Riemann:
$$
	\lim_{ t \to \infty } I(t)=0
$$
cioè $I(t)=o(1)$, con adeguate ipotesi su $h(x)$.
"La funzione oscilla molte volte e ogni contributo si cancella con il proprio opposto".
Non sappiamo con che andamento $I(t)$ vada a 0.

Partiamo dal caso in cui $h'(x)\neq0,\, \forall x\in[a,b]$. Allora posso riscrivere l'integrale come:
$$
	I(t)=\int^b_{a} (e^{ ith(x) }ith'(x)) \frac{g(x)}{ith'(x)}\, dx
$$
Il primo termine è $\frac{d}{dx}e^{ ith(x) }$ e posso integrare per parti.
$$
	\begin{aligned}
	I(t)&=e^{ ith(x) }\frac{g(x)}{ith'(x)}|^{^a}_{_{b}}-\int^b_{a} dx \, e^{ ith(x) } \frac{g(x)}{ith'(x)}\\
	&=\frac{1}{it}\left[ \frac{e^{ ith(b) }g(b)}{h'(b)} -\frac{e^{ ith(a) }g(a)}{h'(a)}\right]-\frac{1}{it}J
	\end{aligned}
$$
con:
$$
	J=\int^b_{a} dx\, e^{ ith(x) } \frac{d}{dx}\left( \frac{g(x)}{h'(x)} \right)
$$
Che va di nuovo a zero per il lemma di Riemann: $J(t)=o(1)$.
Dunque:
$$
	I(t)=O\left( \frac{1}{t} \right) \sim \frac{1}{t}
$$
Dunque la maggior parte del contributo viene dagli estremi.

Cosa succede se ci sono dei punti in $[a,b]$ nei quali $h'(x)=0$?
$$
	\exists x_{0}:h'(x_{0})=0
$$
Definisco $f(z)=ih(z)$ (è definita per mezzo della continuazione analitica in campo complesso di $h(x)$), e l'integrale diventa:
$$
	\int_{\gamma}e^{ tf(z) }g(z)dz
$$
con $\gamma$ cammino reale. E mi sono ricondotto allo studio del punto a sella.
$\gamma$ passa già per il punto stazionario, ma ci passa in maniera corretta?
Se così non fosse, posso deformare il cammino in modo da passare per $x_{0}$ nel modo giusto?
$f'(z)=ih'(z), \quad f'(z)=0\to h'(z)=0,\;z=x_{0}$.
$f''(z)=ih''(z)$.
Riprendendo la rischiesta della lezione precedente:
$$
	\mathrm{Re}f(z)-\mathrm{Re}f(x_{0})<0
$$
Questo equivale a chiedere:
$$
	-\mathrm{Im}h(z)+\mathrm{Im}h(x_{0})<0\implies-\mathrm{Im}h(z)<0\to \mathrm{Im}h(z)>0
$$
NOTA: $\mathrm{Im}f(x_{0})=0$!
Che angolo devo imporre per soddisfare tale condizione?
Sviluppiamo $h(z)$:
$$
	h(z)=h(x_{0})+\frac{1}{2}h''(x_{0})(z-x_{0})^2+\dots
$$
Procedendo come ieri:
$$
	\frac{1}{2}h''(x_{0})=Ae^{ i\alpha },\quad z-x_{0}=\rho e^{ i\varphi },\;-\delta<\rho <\delta
$$
Se ora calcolo la parte immaginaria di $h(z)$ trovo:
$$
	\mathrm{Im}h(z)=A\rho^2 \sin(\alpha+2\varphi)>0
$$
Dunque scegliendo il caso migliore possibile, $\sin(\dots)=1$, troviamo:
$$
	\alpha+2\varphi=\frac{\pi}{2}+2k\pi\implies \varphi=\frac{\pi}{4}-\frac{\alpha}{2}+k\pi
$$
Nel caso in cui $h''(x_{0})> 0$, scegliamo $\alpha=0$. Qualora $h''(x_{0})<0$, scegliamo $\alpha=\pi$. Questo ci lascia con 2 soli possibili valori di $\varphi$.
$$
	\begin{cases}
	\varphi=\frac{\pi}{4}, & \alpha=0 \\
	\varphi=-\frac{\pi}{4}, & \alpha=\pi
	\end{cases}
$$
![[Pasted image 20261112111641.png]]

Sostituiamo il risultato che abbiamo ottenuto sull'angolo all'interno dello sviluppo di $h(z)$:
$$
	h(z)=h(z_{0})+ iA\rho^2+\dots
$$
Sostituendo tutto in $I(t)$, il contributo dominante è dato solo dall'intorno del punto stazionario. Sostituendo i vari sviluppi ci escono ovviamente dei termini gaussiani.
$$
\begin{aligned}
	I(t)&=\int_{x_{0}-\delta}^{x_{0}+\delta} e^{ it(h(x_{0})+1/2\,h''(x_{0})(z-z_{0})^2+\dots) } (g(x)+g_{1}(z-x_{0})+\dots)\,dz\\
	&\sim e^{ \pm i \pi/4 } e^{ ith(x_{0}) } \int^\infty_{-\infty} d\rho \, e^{ -tA\rho^2 }g(x_{0})=e^{ \pm i\pi/4 } e^{ ith(x_{0}) } g(x_{0}) \sqrt{ \frac{\pi}{At} }
\end{aligned}
$$
il fattore $e^{ \pm i\pi/4 }$ esce dal cambio di variabile nel differenziale.

Osservazione: Con la mia curva posso evitare di passare per altri punti in cui la parte immaginaria di $h(z)$ si annulla. Ma esistono 2 punti per i quali siamo costretti a passare in cui la parte immaginaria di $h(z)$ si annulla, i 2 estremi!
Ma abbiamo già calcolato il contributo di questi termini, e contribuisce in modo minore, come $O\left( \frac{1}{t} \right)$.

Facciamo un esempio.

$$
	I(\lambda)=\int^3_{0} x e^{ i\lambda [(x^3/3)-x]}\, dx,\quad \lambda\to \infty
$$
$h(x)=\frac{1}{3}x^3-x\to h'(x)=x^2-1=0\to x=\pm1$
Potrei passare anche per $x=-1$ deformando la curva. Per il momento escludiamolo, per studiarlo meglio più avanti.
$h''(x)=2x\to h'(1)=2>0, \quad \varphi= \frac{\pi}{4}$
$$
	z-1=\rho e^{ i\pi/4 },\quad dz=e^{ i\pi/4 }d\rho
$$
$$
	\begin{aligned}
	h(z)&=\frac{1}{3}z^3-z=\frac{1}{3}(\rho e^{ i\pi/4 }+1)^3-\rho e^{ i\pi/4 }-1=\\
	&=\frac{1}{3}(\rho^3e^{ i 3\pi/4 }+3\rho^2 e^{ i\pi/2 }+3\rho e^{ i\pi/4 }+1)-\rho e^{ i\pi/4 }-1=\\
	&=-\frac{2}{3}+i\rho^2+\frac{1}{3}\rho^3 e^{ i{3}\pi/4 }
	\end{aligned}
$$
Dunque:
$$
	\begin{aligned}
	I(\lambda)&=e^{ -i 2\lambda/3 } e^{ i \pi/4 }\int e^{ -\lambda \rho^2 }e^{ i\lambda/3\;\rho^3 e^{ i 3\pi/4 } } (\rho e^{ i\pi/4 }+1)d\rho=\\
	&=e^{ i\pi/4 } e^{ -i 2\lambda/3 } \int d\rho e^{ -\lambda \rho^2 }\left[ \left( 1+\frac{i\lambda}{3} \rho^3 e^{ i_{3}\pi/4 } -\frac{1}{2} \frac{\lambda^2}{9} \rho^6 e^{ i 3\pi/2 }+\dots\right)(1+\rho e^{ i\pi/4 }) \right]
	\end{aligned}
$$
Proviamo a calcolare l'ordine 0 ed l'ordine 1, tenendo in considerazione anche il contributo dato dagli estremi di integrazione.
$$
	\begin{aligned}
	I(\lambda)&\sim e^{ i\pi/4 } e^{ -i 2\lambda/3 } \int d\rho e^{ -\lambda \rho^2 } \left[ 1-\frac{i\lambda}{3}\rho^4+\frac{i}{18}\lambda^2 \rho^6+\dots \right]\sim\\
	&\sim e^{ i\pi/4 } e^{ -i 2\lambda/3 }\sqrt{ \frac{\pi}{\lambda} }\left( 1-\frac{i\lambda}{3} \frac{3}{4} \frac{1}{\lambda^2}+\frac{15}{8}\frac{i}{18} \lambda^2\right)=\\
	&=e^{ i\pi/4 } e^{ -i 2\lambda/3 }\sqrt{ \frac{\pi}{\lambda} }\left( 1-\frac{i{7}}{48} \frac{1}{\lambda} \right)
	\end{aligned}
$$
A questo andrebbe aggiunto il contributo degli estremi. AGGIUNGILO A CASA!

Affrontiamo l'altro problema che abbiamo temporaneamente ignorato.
Perchè non posso deformare la mia curva per passare in $x=-1$?

Studiamolo in modo esplicito.
$$
	\mathrm{Im}(h(z)-h(-1))=0
$$
sappiamo che $\mathrm{Im}h(-1)=0$. Allora studio solo $\mathrm{Im}h(z)$.
$$
	\mathrm{Im}h(z)= \mathrm{Im}\left( \frac{1}{3} z^3-z \right)=\mathrm{Im}\left[ \frac{1}{3} (x^3+i 3x^2y-3xy^2-iy^3)-x-iy \right]=0
$$
E otteniamo:
$$
	x^2y- \frac{1}{3} y^3-y=0 \implies y\left( x^2-\frac{1}{3}y^2-1 \right)=0
$$
che ha come soluzioni:
$$
	\{ y=0 \}\cup \left\{  x^2-\frac{1}{3}y^2=1  \right\}
$$
FAI IL DIEGNO CON L'IPERBOLE A CASA

Per passare $-1$ devo sempre attraversare zone proibite.

Esempio difficile ma utile per MQ2

$$
	I(z)=\int_{\gamma} e^{ zt -1/3\, t^3} \, dt
$$
Questo integrale definisce la funzione di Airy:
$$
	\frac{1}{2\pi i}I(z)=A_{i}(z)
$$
Riscriviamo $t$ esplicitando parte reale e complessa.
$$
	\begin{cases}
	t=x+iy=|t|e^{ i\varphi } \\
	t^3=x^3+i 3x^2y-3xy^2-iy^3=|t|^3(\cos{3}\varphi+i\sin 3\varphi)
	\end{cases}
$$
Voglio che l'integrale esista, dunque mi interessano le curve che a $\pm \infty$ stiano nelle regioni in cui $\mathrm{Re}\,t^3>0$.
Se voglio parte reale positiva devo imporre $\cos 3\varphi>0$, cioè:
$$
	-\frac{\pi}{2}<3\varphi< \frac{\pi}{2}\to \begin{cases}
	-\frac{\pi}{6}<\varphi< \frac{5}{6}\pi \\
	\frac{\pi}{2}<\varphi< \frac{5}{6}\pi \\
	\frac{7}{6}\pi < \varphi< \frac{3}{2}\pi
	\end{cases}
$$
DISEGNA LE 3 REGIONI!
Scegliamo come curva $\gamma$ un retta parallela all'asse immaginario, con parte reale negativa. Posso parametrizzare una curva di questo tipo come:
$$
	\gamma: \tau\to t=i\tau-\varepsilon
$$
Questa scelta corrisponde ad una funzione di Airy di prima specie.
Faccio il seguente cambio di variabile:
$$
	t=\sqrt{ z }w\implies \begin{cases}
	zt=z^{3/2} w \\
	t^3= z^{3/2} w^3 \\
	dt= \sqrt{ z }dw
	\end{cases}
$$
Con $z \in \mathbb{R}_{+}$ il cammino di integrazione resta lo stesso (RIFLETTI SU QUESTO PUNTO).
$$
	I(t)=\sqrt{ z }\int_{\gamma} dw\, e^{ z^{3/2}(w-1/3\, w^3) }
$$
abbiamo:
$$
	f(w)=w- \frac{1}{3}w^3\to f'(w)=1-w^2,\; f'(w)=0 \iff w=\pm 1
$$
$$
	f''(w)=-2w\to f''(-1)=2 \implies \alpha=0 \; \text{e}\; \varphi=\frac{\pi}{2}
$$
Cioè devo attraversare il punto stazionario passando verticalmente.
Facendo il ragionamento locale dell'altro giorno attorno a $w=-1$ troviamo che il cammino migliore è quello che passa verticalmente per il punto dall'alto verso il basso, e non quello che sale, scende e risale.
(Ho trovato praticamente il caso di prima a segni alternati quindi scelgo il punto opposto).
Continuiamo con il metodo che abbiamo sviluppato negli ultimi giorni:
$$
	(w+1)=i\rho=\rho e^{ i \pi/2 }\implies w=-1+i\rho
$$
dunque:
$$
	f(w)=-\frac{2}{3}-\rho^2+O(\rho^3)
$$
Da cui:
$$
	\begin{aligned}
	I(z)&=\sqrt{ z }\int_{\gamma} dw\, e^{ z^{3/2}(w-1/3\, w^3) } \underset{z\to \infty}{\sim} \sqrt{ z } \int^\infty_{-\infty} id\rho\, e^{ -2/3 \, z^{3/2}} e^{ -z^{3/2} \rho^2 }=\\
	&= i\sqrt{ z } e^{ -2/3\, z^{3/2} } \sqrt{ \frac{\pi}{z^{3/2}} }\mathrm{Im}(h(z)-h(1))=i\sqrt{ \pi }z^{-1/4} e^{ -2/3\; z^{3/2} }
	\end{aligned}
$$
Cosa succede per $z \in \mathbb{R}_{-}$?
Faccio il seguente cambio di variabile: $z=-\hat{z},\; \hat{z}\in \mathbb{R}_{+}$.
$$
	I(\hat{z})=\int_{\gamma} dt\, e^{ -\hat{z} t- t^3/3 }
$$
Ma a questo punto devo cambiare il cambio di variabile:
$$
	t=\sqrt{ \hat{z} } w
$$
e ottengo:
$$
	I(\hat{z})=\int_{\gamma} dw\; e^{ \hat{z}^{3/2}(-w-1/3\; w^3) }
$$
la mia funzione $f(w)$ è cambiata!
$$
	f(w)=-w-\frac{1}{3}w^3\to f'(w)=-1-w^2
$$
e $f'(w)=0$ solo quando $w=\pm i$.
Come procedo ora?

