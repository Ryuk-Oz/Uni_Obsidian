
**Funzione Zeta di Riemann**

$$
	\zeta(s)=\sum^\infty_{n=1} \frac{1}{n^s}\qquad s\in \mathbb{C} \quad \mathrm{Re}(s)>0
$$
Una formulazione alternativa della zeta è la seguente:
$$
	\zeta(s)=\prod_{p} \left( 1-\frac{1}{p^s} \right)^{-1} \qquad \mathrm{Re}(s)>1
$$
per il momento a prendiamo per buona. Con $p$ si intendono i numeri primi, questa rappresentazione si chiama Prodotto di Eulero.

(Vedi su appunti Frau la dimostrazione della convergenza della produttoria).
$$
	\frac{1}{\zeta(s)}=\prod_{p}\left( 1-\frac{1}{p^s} \right)
$$
$$
	\prod_{n=1}^\infty(1+a_{n}) \qquad \text{converge } \iff \sum^\infty_{n=1} a_{n} \quad \text{converge assolutamente}
$$
.
.
.
.
.


Verifichiamo che le due rappresentazioni coincidano.
Moltiplichiamo la $\zeta$ per $(1-z^{-s})$:
$$
	\begin{aligned}
	\zeta(s)(1-2^{-s})&= \sum^\infty_{n=1} n^{-s}-\sum^\infty_{\text{n pari}}(2n)^{-s}=\sum_{\text{n dispari}} n^{-s}\\
	\zeta(s)(1-2^{-s})(1-3^{-s})&=\sum_{\text{n dispari}}n^{-s}-\sum_{\text{ n dispari}} (3n)^{-s}=\sum_{n\neq 2k,3k} n^{-s}\\
	\zeta(s)(1-2^{-s})(1-3^{-s})(1-5^{-s})\dots(1-p_{N}^{-s})&=1+p^{-s}_{N+1}+\dots
	\end{aligned}
$$
Iterando su tutti i numeri primi otteniamo:
$$
	\zeta(s)\prod_{p}(1-p^{-s})=1 \implies \zeta(s)=\prod_{p}(1-p^{-s})^{-1}
$$
Questo serve anche a dimostrare l'esistenza di infiniti numeri primi:

**Dim**:
Ipotizziamo per assurdo che esistano $N$ numeri primi con $p_{N}$ numero primo più grande.
Allora potrei scrivere:
$$
	\zeta(s)\prod_{p=2,3,\dots p_{N}}(1-p^{-s})=1\implies \zeta(s)=\prod_{p=2,3,\dots p_{N}}\left( \frac{p^s-1}{p^s} \right)^{-1}=\prod_{p=2,3,\dots p_{N}} \left( \frac{p^s}{p^s-1} \right)
$$
Questo implicherebbe:
$$
	\zeta(1)=\prod_{p=2,3,\dots p_{N}} \frac{p}{p-1}=A \qquad \text{numero complesso}
$$
Ma sappiamo che $\zeta(1)\to \infty$. Il che è assurdo. $\blacksquare$


Dal prodotto di Eulero vediamo che per $\mathrm{Re}(s)>1$ la $\zeta(s)$ non si annulla mai.
Dunque $\zeta(s)$ è analitica e non nulla per $\mathrm{Re}(s)>1$.

Come sempre cerchiamo una rappresentazione integrale della $\zeta$.

Partiamo dalla seguente osservazione:
$$
	\frac{\Gamma(s)}{\alpha^s}=\frac{1}{\alpha^s}\int^\infty_{0} dx \, e^{ -x } x^{s-1}=\int^\infty_{0} \frac{dx}{\alpha} e^{ -x } \left( \frac{x}{\alpha} \right)^{s-1}=\int^\infty_{0} dt \, t^{s-1} e^{ -\alpha t }
$$
Questo ci permette di scrivere la rappresentazione di Schwinger di $\frac{1}{\alpha^s}$.
$$
	\frac{1}{\alpha^s}=\frac{1}{\Gamma(s)} \int^\infty_{0} dt\, t^{s-1} e^{ -\alpha t }
$$
Il tutto sempre nella regione di convergenza della $\Gamma$. Questo è un trucco abbastanza standard usato nel calcolo di diagrammi di Feynman.
Scriviamo ora:
$$
	\begin{aligned}
	\Gamma(s)\zeta(s)=\sum^\infty_{n=1} \frac{\Gamma(s)}{n^s} = \sum^\infty_{n=1} \int^\infty_{0} dt \, t^{s-1} e^{ -nt }
	\end{aligned}
$$
La serie degli integrali converge uniformemente:
$$
	\sum^\infty_{n=1} \left\lvert \int\dots \right\rvert \leq \sum^\infty_{n=1} \int^\infty_{0} dt\, e^{ -nt } t^{\mathrm{Re}(s)-1}=\sum^\infty_{n=1} \frac{\Gamma(\mathrm{Re}(s))}{n^s}=\Gamma(\mathrm{Re}(s))\sum^\infty_{n=1} \frac{1}{n^s}<\infty
$$
Converge per $\mathrm{Re}(s)>1$.

Dunque possiamo sommare sotto il segno di integrale:
$$
	\Gamma(s)\zeta(s)=\int^\infty_{0} dt\, t^{s-1} \sum^\infty_{n=1} e^{ -nt }=\int^\infty_{0} dt\, t^{s-1} \left( \frac{1}{1-e^{ -t }}-1 \right)=\int dt\, t^{s-1} \frac{e^{ -t }}{1-e^{ -t }}
$$
Dunque:
>[!Abstract] Rappresentazione integrale di $\zeta(s)$
>
>$$
>	\zeta(s)=\frac{1}{\Gamma(s)}\int^\infty_{0} dt \, \frac{t^{s-1}}{e^{ t }-1}
>$$

$\Gamma(s)$ non ha zeri per $\mathrm{Re}(s)>0$ e l'integrale converge per $\mathrm{Re}(s)>1$, la regione di convergenza è la setssa di $\Gamma$. 
(Infatt l'integrando per $\underset{t\to{0}}{\sim} t^{s-2}\to \mathrm{Re}(s-2)>-1\implies \mathrm{Re}(s)>1$)

Come posso costruire una rappresentazione integrale che sia una continuazione analitica di $\zeta(s)$?

Adottiamo un approccio simile a quello usato per la $\Gamma$.

Considero:
$$
	\begin{aligned}
	I(s)&=\int_{C_{H}} dz \, \frac{z^{s-1}}{e^z-1}
	\end{aligned}
$$
Promuovendo $t$ al piano complesso ottengo come funzione integranda una funzione polidroma.
$z^s$ polidroma ha un taglio tra 0 e $\infty$ e posso considerare sul piano un cammino non banale, il cammino usato per l'[[Integrale di Henkel]].
Con questo cammino, $I(s)$ è analitica $\forall s\in \mathbb{C}$.
Studiamo la parentela di questo oggetto con la $\zeta(s)$.
Visto che $I(s)$ esiste per ogni $s$, prendiamo $s$ tale che $\mathrm{Re}(s)>1$.
$$
	\begin{aligned}
	I(s)&=\int_{-\infty}^\varepsilon f_{+} dz +\int _{C_{\varepsilon}} f\, dz +\int_{\varepsilon}^\infty f_{-} dz\\
	&\underset{\varepsilon\to{0}}{=} \int_{0}^\infty (f_{-}(t)-f_{+}(t)) \, dt
	\end{aligned} 
$$
Con:
$$
	\begin{cases}
	f_{+}=\frac{t^{s-1}}{e^{ t }-1} \\
	f_{-}= \frac{t^{s-1}}{e^{ t }-1} e^{ i 2\pi s }
	\end{cases}
$$
Dunque:
$$
	I(s)=(e^{ i2\pi s }-1)\zeta(s)\Gamma(s)
$$
E posso scrivere:

>[!abstract] Continuazione della $\zeta(s)$ tramite cammino di Henkel
>
>$$
>	\zeta(s)=\frac{I(s)}{\Gamma(s)} \frac{1}{e^{ i 2\pi s }-1}=\frac{I(s)}{\Gamma(s)} \frac{e^{ -i\pi s }}{2i \sin \pi s}
>$$

Tralasciando i valori interi di $s$, dove sia la $\Gamma$ che il seno danno problemi, ho trovato una rappresentazione valida ovunque.

Sfruttando l'identità:
$$
	\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin \pi s}\implies \frac{1}{\Gamma(s)\sin \pi s}=\frac{\Gamma(1-s)}{\pi}
$$
Posso riscrivere la Zeta come:
$$
	\zeta(s)=\frac{e^{ -i 2\pi s }}{2i\pi} \Gamma(1-s)I(s)
$$

Studiamo cosa succede nei valori interi di $s$.
Per $s$ intero l'argomento di $I(s)$ non è più polidromo e il cammino di Henkel si riduce al cerchio centrato in 0.
$s=n \in \mathbb{Z}$
$$
	I(n)=\oint_{0} dz\, \frac{z^{n-1}}{e^{ z }-1}
$$
Per calcolare questo integrale devo calcolarne il residuo in $0$.
Per comodità riscrivo l'integrale come:
$$
	I(n)=\oint_{0} dz\, z^{n-2} \frac{z}{e^{ z }-1}
$$
Osseviamo che $\frac{z}{e^{ z }-1}\underset{z\to{0}}{\sim}1$ è regolare, ergo la singolarità deve provenire da $z^{n-2}$.
Si osserva subuto che:
$$
	\begin{cases}
	I(n)=0 \qquad \forall n\geq 2 \\
	I(1)=2\pi i \text{Res}|_{z=0} = 2\pi i
	\end{cases}
$$
Per studiare gli altri valori di $n$ sviluppiamo $\frac{z}{e^{ z }-1}$.
$$
	\begin{aligned}
	\frac{z}{e^{ z }-1}&=\frac{z}{z+\frac{1}{2}z^2+\frac{1}{3!}z^3+\dots}=\frac{1}{1+\left( \frac{1}{2}z+\frac{1}{3!}z^2+\frac{1}{4!}z^3+\dots \right)}=\\
	&= 1-\left( \frac{1}{2}z+\frac{1}{3!}z^2+\dots \right)+\left( \frac{1}{2}z+\frac{1}{3!}z^2+\dots \right)^2-\left( \frac{1}{2}z+\frac{1}{3!}z^2+\dots \right)^3+\dots=\\
	&=1-\frac{1}{2}z+z^2\left( -\frac{1}{6}+\frac{1}{4} \right)+z^3\left( -\frac{1}{6\cdot4}+\frac{1}{6}-\frac{1}{8}\right)+O(z^4)=\\
	&=1-\frac{1}{2}z+\frac{1}{12}z^2+O(z^4)
	\end{aligned}
$$
In base all'ordine che mi interessa devo tenere o meno le parentesi successive dopo lo sviluppo della frazione.
In realtà questo è uno sviluppo famoso (è la funzione generatrice dei numeri di Bernoulli):
$$
	\frac{z}{e^{ z }-1}=\sum^\infty_{n=0} \frac{1}{n!} B_{n} z^n
$$
Dove i coefficienti $B_{n}$ sono i numeri di Bernoulli.
$$
	B_{0}=1, \quad B_{1}=-\frac{1}{2}\quad B_{2}=\frac{1}{6} \quad B_{3}=0
$$
Si può dimostrare che tutti i numeri di Bernoulli dispari maggiori di 3 sono nulli:
**Dim:**
$$
	\begin{aligned}
	\frac{z}{e^{ z }-1} &= 1-\frac{z}{2}+\sum^\infty_{n=2} \frac{1}{n!}B_{n}z^n\\
	\frac{z}{e^{ z }-1}+\frac{z}{2}&=1+\sum^\infty_{n=2} \frac{1}{n!} B^n z^n=\frac{z}{2}\left( 1+\frac{z}{e^{ z }-1} \right)=\frac{z}{2} \frac{e^z+1}{e^z-1}=\frac{z}{2} \frac{e^{ z/2 }+e^{ -z/2 }}{e^{ z/2 }-e^{ -z/2 }}
	\end{aligned}
$$
Abbiamo ottenuto una funzione pari:
$$
	\frac{z}{2} \frac{e^{ z/2 }+e^{ -z/2 }}{e^{ z/2 }-e^{ -z/2 }}
$$
Dunque anche $1+\sum^\infty_{n=2} \frac{1}{n!} B^n z^n$ è pari, e non ho i coefficienti dispari per $n\geq 3$. $\blacksquare$


Possiamo sfruttare i numeri di Bernoulli per riscrivere $I(n)$:
$$
	I(n)=\oint_{0} dz\, z^{n-2} \frac{z}{e^{ z }-1}= \sum^\infty_{k=0} \frac{1}{k!} B_{k} \oint_{0} dz \, z^{n+k-2}=2\pi i\sum^\infty_{k=0} \frac{1}{k!}B_{k} \delta_{k,1-n}
$$
e otteniamo:
$$
	\begin{cases}
	n=2,3,4\dots \qquad &I(n)=0 \\
	n=1 \qquad &I(1)=2\pi iB_{0}=2\pi i \\
	n=0 \qquad &I(0)=2\pi i B_{1}=2\pi i\left( -\frac{1}{2} \right) \\
	n=-2l \quad l=1,2,\dots \qquad &I(-2l)=2\pi i \frac{1}{(2l+n)!}B_{2l+n}=0 \\
	n=-2l+1\quad l=1,2,\dots \qquad &I(-2l+1)=2\pi i \frac{1}{(2l)!}B_{2l}
	\end{cases}
$$

Sostituendo questi risultati in:
$$
	\zeta(s)=\frac{e^{ -i 2\pi s }}{2i\pi} \Gamma(1-s)I(s)
$$
Troviamo che:
$$
	\begin{cases}
	\zeta(n) \quad n\geq{2}  & \text{regolare} \neq{0} \\
	\zeta(s)\underset{s\to{1}}{\sim} \frac{e^{ -i\pi }}{2\pi i} \frac{\Gamma(1)}{I(1)}\sim \frac{1}{s-1}  & \text{polo semplice in } s=1 \\
	\zeta(0)=\frac{1}{2\pi i} 2\pi i\left( -\frac{1}{2} \right)=-\frac{1}{2}  & \text{posso regolarizzare la somma di tutti gli uno e fa } -\frac{1}{2}
	\end{cases}
$$
Prova a calcolare la somma di tutti gli interi


