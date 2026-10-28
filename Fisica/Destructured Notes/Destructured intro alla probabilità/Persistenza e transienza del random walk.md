
**Utile:** [[Funzioni Generatrici]]

Un random walk si dice persistente se torna sicuramente in $\vec{x}=0$
Se $d\leq {2}$ il random walk è persistente.
Se $d\geq 3$ il random walk è transiente, cioè c'è una probabilità non nulla di non tornare nell'origine.

Occupiamoci dello studio della persistenza del random walk.

Definisco:
$u(t)\equiv \text{prob che il RW sia in } x=0 \text{ al tempo }t$
$f(t)\equiv \text{probabilità che il RW sia in }x=0\text{ al tempo }t \text{ per la prima volta}$
Dunque possiamo riscrivere $u(t)$ facendo uso di $f(t)$. (Uso il teorema della probabilità completa).
$$
	u(t)=f(t)+f(t-1)u(1)+f(t-2)u(2)+\dots+ f(1)u(t-1) \qquad (1)
$$
Ogni termine rappresenta la probabilità che il RW sia in $x=0$ per la prima volta in $t-s$ e ci ritorni dopo $s$ passi (dunque ci ritorna in $t$).
Da qua concludiamo il risultato (ovvio) che $u(t)\geq f(t)$.
Condizioni iniziali:
- $u(0)=1$ (a $t=0$ mi trovo in $x=0$)
Per risolvere questo problema posso fare uso delle funzioni generatrici:
$$
	F(s)=\sum_{t=0}^\infty s^t f(t), \quad U(s)=\sum_{t=0}^\infty s^t u(t)
$$
Ci sostituisco dentro l'equazione (1).
$$
\begin{aligned}
\sum^\infty_{t=1} s^tu(t)&=\sum^\infty_{t=1}s^t f(t)u(0)+\sum^\infty_{t=1}s^tf(t-1)u(1)+\dots \sum^\infty_{t=1}s^tf(1)u(t-1)+\left( \sum s^t f(0)u(t) \right)=\\ 
	&=\sum_{t=1}^\infty s^t\sum_{k=0}^{t-\not{1}} f(t-u)u(k)
\end{aligned}	
$$
Passando alla somma $t=0$ devo aggiungere un termine pari a 0:
$$
	\sum_{t=1}^\infty s^t u(t)=\sum^\infty_{t=0}s^tu(t)-u(0)=U(s)-1
$$
$$
	\sum_{t=0}^\infty s^t\sum_{k=0}^{t} f(t-k)u(k)=F(s)U(s) \qquad (2)
$$
Sono potuto partire da 0 anzichè 1 perchè il termine in 0 fa 0.
Dimostro l'equazione $(2)$:
$$
	\begin{aligned}
	F(s)U(s)&=\sum^\infty_{p=0}s^p f(p ) \sum^\infty_{q=0}s^qu(q)=\sum^\infty_{p}\sum^\infty_{q}s^{p+q}f(p)u(q)=\sum_{n=0}^\infty s^n \sum_{q=0}^\infty u(q)f(n-q)\\
	\text{quando } q>n &\implies n-q<0, \text{ poichè } f(k)=0\, \forall k\leq 0 \text{ allora ritrovo la forma che volevo dimostrare:}\\
	F(s)U(s)&=\sum_{n=0}^\infty s^n \sum_{q=0}^n u(q) f(n-q)
	\end{aligned}
$$
Dunque alla fine di tutto abbiamo dimostrato che $F(s)U(s)=U(s)-1$.

Definiamo bene la persistenza:
$$
	\text{persistenza} \iff f\equiv \sum_{t=0}^\infty f(t)=1
$$
Posso riscriverlo anche come:
$$
	f=\lim_{ s \to 1 } F(s)=1
$$
Riprendendo i risultati di prima ottengo che:
$$
	U(s)=\frac{1}{1-F(s)}
$$
Posso allora riformulare la persistenza come:
$$
	\lim_{ s \to 1 } U(s)\to +\infty
$$
Cioè se il random walk è persistente ritorno infinite volte nell'origine.
Quest'ultima condizione è "facile" da verificare
Consideriamo il limite in cui $t\gg 1$
$$
	u(t)\simeq p_{t}(0)
$$
dove:
$$
	p_{t}(x)=\frac{1}{\sqrt{ 2\pi t }}e^{ -x^2/(2t) } \quad (d=1)
$$
$$
	U(1)=\lim_{ T \to \infty } \sum^T_{t=0} u(t) \simeq \lim_{ T \to \infty } \int_{0}^T \frac{1}{\sqrt{ 2\pi t }}dt=\lim_{ T \to \infty } \frac{2}{\sqrt{ 2\pi }}T^{1/2}=\infty
$$
Estendendo il problema a dimensioni superiori vado semplicemente a considerare una gaussiana in $d$ dimensioni.
$$
	p_{t}(x)=\frac{1}{(2\pi t)^{d/2}}e^{ -|\vec{x}|^2/(2t) } \qquad \vec{x}=\text{vettore } d \text{ dimensionale}
$$
Ma a noi interessa solo il fattore di normalizzazione.
$$
	U(1)=\lim_{ T \to \infty } \int^T_{0} \left( \frac{1}{2\pi t} \right)^{d/2}\simeq \lim_{ T \to \infty } \int_{0}^T \frac{dt}{t^{d/2}} = \begin{cases}
	T^{1/2}\to \infty \quad d=1 \\
	\ln T\to \infty \quad d=2 \\
	\frac{1}{T^{1/2}}<\infty \quad  d=3
	\end{cases}
$$
Dunque per $d\geq3$ il random walk non è persistente.

In particolare in $d=3$ ho:
$$
	U(1)\simeq {1},51\dots\quad \text{ e } \quad f=0.34
$$
Cioè $34 \%$ di probabilità di ritornare nell'origine.

**Lezione Associata:** [[5. Moto Browniano e Random Walk]]