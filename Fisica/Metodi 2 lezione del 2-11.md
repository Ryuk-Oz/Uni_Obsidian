
Oggi si parla di sviluppi asintotici yey.

Si tratta del prototipo dei risultati che otteniamo sviluppando i risultati ottenuti da una lagrangiana contenente un parametro piccolo (?).
Dobbiamo capire bene cosa cambia da uno sviluppo di Taylor.

**Ripasso:**
Riprendiamo la differenza tra $O$-grande e $o$-piccolo.
Siano $f(z)$, $\varphi(z)$ analitiche in $D\subset \mathbb{C}$, $z_{0}\in [D]$ (cioè $z_{0} \in D$ oppure $z_{0}\in \partial D$).
- Diciamo che $f(z)=O(\varphi(z))$ per $z\to z_{0}$, $z\in D$ ($z$ tende a $z_{0}$ da dentro a $D$) se:
  $\exists I_{\delta}(z_{0})\, / \, | \frac{f(z)}{\varphi(z)}|$ è limitato $\forall z\in D\cap I_{\delta}(z_{0})$. Cioè $|f(z)|<A|\varphi(z)|$.
  Cioè localmente le due funzioni vanno allo stesso modo.
Nel caso in cui $z_{0}\in D$  $z$ può arrivare a $z_{0}$ da ogni direzione e ritrovo la definizione standard di limite.
Nel caso in cui $z_{0}\in\partial D$, $z$ può arrivarci solo da alcune direzioni. 
Devo tenere in considerazione entrambe le situazioni, per questo motivo prendo l'intersezione e non semplicemente $I_{\delta}(z_{0})$.
- Diciamo che $f(z)=o(\varphi(z))$ per $z\to z_{0}$, $z\in D$ se:$$\underset{z\in D}{\lim_{ z \to z_{0} }} \frac{f(z)}{\varphi(z)}=0$$Si tratta di un limite direzionale, cioè $\forall\varepsilon \; \exists I_{\delta}(x_{0}) \, / \,|f(x)|<\varepsilon\; \forall z\in D\cap I_{\delta}(z_{0})$

### Successione asintotica

Consideriamo una successione $\{ \varphi_{l}(z) \}$, $l=0,1,\dots$ regolari in $D$.
Diciamo che $\{ \varphi_{l}(z) \}$ è una successione asintotica per $z\to z_{0}$ $z\in D$, $z_{0}\in[D]$ se:
$$
	\varphi_{n}(z)=o(\varphi_{n-1}(z))
$$
Achtung: il punto $z_{0}$ che considero non è accessorio!
$\varphi_{l}=(z-z_{0})^l g(z)$ è una successione asintotica per $z_{0}$.
$\varphi_{l}=\frac{g(z)}{z^l}$ è una successione asintotica per $z_{0}=\infty$.

A questo punto posso definire una serie asintotica:
$$
	f(z)\underset{\underset{z\in D}{z\to z_{0}}}{\sim}\sum^\infty_{l=0} a_{l} \,\varphi_{l}(z)
$$
se:
1. $\{ \varphi_{l}(z) \}$ è una successione asintotica per $z\to z_{0}$, $z\in D$
2. Il resto n-esimo:
$$
	R_{n}(z)=f(z)-\sum_{l=0}^{n-1} a_{l}\, \varphi_{l}(z)
$$
   è tale per cui: $R_{n}(z)= o(\varphi_{n-1}(z))$ per $z\to z_{0}$, $z\in D$.
Formalmente è più corretto scrivere $f(z)$ come una somma discreta più il resto n-esimo, in quanto la serie in se per se potrebbe non convergere.

Facciamo un esempio noto, la trasformata di Laplace.
$$
	F(s)=\mathcal{L}_{s}(f)=\int^\infty_{0} e^{ -sx } f(x) dx \qquad \text{analitica per } \mathrm{Re}(s)>\alpha_{0}
$$
Ricordiamo che:
$\mathcal{L}_{s}(f')=s\mathcal{L}_{s}(f)-f(0)$, da cui troviamo:
$$
	\mathcal{L}_{s}(f^{(n)})=s^n \underbrace{\mathcal{L}_{s}(f)}_{F(s)}-f(0)s^{n-1}-f'(0)s^{n-2}-\dots f^{(n-1)}(0)
$$
Pertanto posso riscrivere $F(s)$ come uno sviluppo asintotico:
$$
	F(s)=\frac{f(0)}{s}+\frac{f'(0)}{s^2}+\dots \frac{f^{(n-1)}(0)}{s^n}+\frac{1}{s^{n}} \mathcal{L}_{s}(f^{(n)}) \sim \sum^\infty_{l=0} \frac{f^{(l)}(0)}{s^{l+1}} \quad \text{per } s\to \infty
$$
ovviamente $s\to \infty$ dalla porzione di piano in cui $F(s)$ è definita ($\mathrm{Re}(s)>\alpha_{0}\equiv D$).
 A CASA rifletti su come mai $\frac{\mathcal{L}_{s}(f^{(n)})}{s^n}=o\left( \frac{1}{s^n} \right)$, rendendo lo sviluppo legittimo.

Facciamo un esempio concreto:
$$
	f(x)=\frac{1}{1+x}=\sum^\infty_{n=0} (-1)^n x^n =\sum^\infty_{n=0} \frac{1}{n!} \left( \frac{d^nf}{dx^n} \right)_{0} x^n
$$
$f^{(n)}(0)=n!(-1)^n$, dunque:
$$
	F(s)\sim \sum^\infty_{l=0} \frac{(-1)^nn!}{s^{n+1}} \qquad \text{per } s\in D, \,s\to \infty
$$
La serie chiaramente non converge per $s\to \infty$.
Verifichiamo se sia possibile o meno scriverne uno sviluppo asintotico cioè se:
$$
	R_{n}(s)=\frac{\mathcal{L}_{s}(f^{(n)})}{s^n}\sim o\left( \frac{1}{s^n} \right)
$$
Sfruttando la definizione di trasformata di Laplace:
$$
	R_{n}(s)=\frac{1}{s^n}\int^\infty_{0} dx\, e^{ sx } \frac{(-1)^nn!}{(1+x)^{n+1}}=(-1)^nn!\int^\infty_{0}dx\, \frac{e^{ sx }s}{(s+sx)^{n+1}}
$$
Mi metto sull'asse reale e faccio un cambio di variabile, $s\in \mathbb{R}_{+}$, $s>\alpha_{0}$. Sia $sx=y$.
$$
	R_{n}(s)=(-1)^n n! \int^\infty_{0} dy\, \frac{e^{ -y }}{(s+y)^{n+1}}
$$
Posso maggiorarla:
$$
	|R_{n}(s)|\leq n! \int^\infty_{0} dy\, \frac{e^{ -y }}{|(s+y)^{n+1}|}\leq \frac{n!}{s^{n+1}} \int^\infty_{0} e^{ -y }dy
$$
Quanto è legittimo prendere $s\in \mathbb{R}_{+}$? Prendessi $s$ complesso, andrei a integrare su una retta inclinata, ma per $\mathrm{Re}(s)>\alpha_{0}$ l'argomento dell'esponenziale è analitico allora posso sempre deformare questa retta sulla retta reale. (Cioè posso continuare analiticamente l'integrale che abbiamo appena calcolato su tutto $D$)

**OSS:** non è detto che prendendo più termini la precisione aumenti. Esiste un numero ottimale oltre il quale la precisione inizia a calare.

Qual è il numero ottimale di termini (nell'esempio che abbiamo appena svolto)?
$$
	|a_{n}|=\frac{n!}{s^{n+1}}=\frac{\sqrt{ 2\pi n }e^{ -n }n^n}{s^{n+1}}
$$
Cerchiamo il punto stazionario di questo coefficiente:
$$
	\partial_{n} \frac{n!}{s^{n+1}}=\frac{\partial_{n}n!s^{n+1}-n!\partial_{n}s^{n+1}}{s^{n+2}}=0
$$
Calcoliamo le derivate:
$$
	\partial_{n}s^{n+1}=s^{n+1}\log s \qquad \partial_{n}n^n=\partial _{n} e^{ n\log n }=n^n(\log n +1)
$$
Dunque:
$$
	\sqrt{ 2\pi } \partial_{n}(n^{1/2} e^{ -n } n^n)=\dots=\sqrt{ 2\pi }n!\left( \frac{1}{2n}+\log n \right)
$$
FAI PASSAGGI INTERMEDI
Allora:
$$
	\partial_{n}|a_{n}|=\frac{1}{2n}+\log n-\log s=0 \qquad \text{cioè} \qquad n_{0}e^{ 1/2n_{0} }\sim s
$$
per $n\to \infty$ trovo: $n_{0}\sim s$.
Come faccio a sapere se questo sia proprio un minimo:
$$
	\frac{(n-1)!}{s^n}> \frac{n!}{s^{n+1}}\quad \text{e}\quad \frac{1>n}{s} \quad \text{per} \quad n<s
$$

**ROBA MOLTO IMPORTANTE:**
Data una funzione $f(z)$ lo sviluppo asintotico per $z\to z_{0}$ con $z\in D$ è unico.
La dimostrazione è facile sfruttando la definizione di resto n-esimo.
$$
	R_{n}(z)=f(z)-\sum_{l=0}^{n-1} a_{l}\, \varphi_{l}(z)=o(\varphi_{n-1})
$$
Se lo sviluppo è unico, i coefficienti assumono un valore univoco. Per dimostrarlo, iniziamo calcolando il resto 1-esimo di $f(z)$:
$$
	R_{1}(z)=f(z)-a_{0}\varphi_{0}=o(\varphi_{0})
$$
Cioè:
$$
	\underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)-a_{0}\varphi_{0}(z)}{\varphi_{0}(z)}=0 \implies \underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)}{\varphi_{0}(z)}=a_{0}
$$
Analogamente:
$$
	R_{2}=f(z)-a_{0}\varphi_{0}(z)-a_{1}\varphi_{1}(z)=o(\varphi_{1}(z))
$$
Cioè:
$$
		\underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)-a_{0}\varphi_{0}(z)-a_{1}\varphi_{1}(z)}{\varphi_{1}(z)}=0 \implies \underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)-a_{0}\varphi_{0}}{\varphi_{1}(z)}=a_{1}
$$
E così via:
$$
	a_{n}=\lim_{ z \to z_{0} } \frac{\left( f-\sum^{n-1}_{l=0} a_{l}\varphi_{l} \right)}{\varphi_{n}}
$$

Tuttavia non vale il contrario. Preso uno sviluppo asintotico, non possiamo ricostruire $f$ in maniera univoca (CERCA DI CAPIRE PERCHè).

Facciamo un esempio:
$z\to \infty$ e $D=\left\{  z\in\mathbb{C} \, / \, |argz|<\frac{\pi}{2}-\delta \right\}$ (semipiano positivo con assi verticali leggermente inclinati).
Prendo come successione asintotica: $\left\{  \varphi_{l}=\frac{1}{z^l}  \right\}$.
Considero $e^{ -z }$:
$$
	a_{0}=\underset{z\in D}{\lim_{ z \to \infty } } e^{ -z }=0 \qquad a_{1}=\underset{z\in D}{\lim_{ z \to \infty } } \frac{e^{ -z }}{\frac{1}{z}}=0
$$
Continuando si trova:
$$
	a_{n}=\underset{z\in D}{\lim_{ z \to \infty } } e^{ -z }z^n=0
$$
Dunque: $e^{ z }\sim{0}$ per $z\to \infty$, $z\in D$.
Dunque, considerando $f(z)$:
$$
	f(z)=\sum^\infty_{l} a_{l} \frac{1}{z^l}
$$
posso sempre trovare una funzione $g(z)=f(z)+kz^m e^{ -z }\sim \sum^\infty_{l=0} a_{l} \frac{1}{z^l}$ per $z\to \infty$, $z \in D$.
In fisica, termini di questo tipo, che non emergono da uno sviluppo asintotico, sono noti come termini non perturbativi.



Supponiamo ora di avere una funzione definita tramite una serie di taylor in $0$.
$$
	f(z)=\sum^\infty_{k=0} a_{k} z^k
$$
con raggio di convergenza $\rho=\lim_{ k \to \infty } |\frac{a_{k}}{a_{k+1}}|$.
Prendo ora $\Phi(z)$ , Trasformata di Borel di $f(z)$:
$$
	\Phi(z)=\sum^\infty_{k=0} \frac{a_{k}}{k!} z^k
$$
Questa serie ha raggio di convergenza infinito:
$$
		\rho=\lim_{ k \to \infty } | \frac{a_{k}}{k!} \frac{(k+1)!}{a_{k+1}}|=\infty
$$
Posso sfruttare questo integrale per continuare analiticamente $f(z)$ tramite il seguente integrale:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } \Phi(zt) \left( =\frac{1}{z} \mathcal{L}_{\frac{1}{z}}(\Phi) \right)
$$
posso dimostrare molto facilmente che per $|z|<\rho$, $I(z)=f(z)$.
$$
	I(z)=\int^\infty_{0} dt \, e^{ -t } \sum^\infty_{k=0} \frac{a_{k}}{k!} t^k z^k = \sum^\infty_{k=0} \frac{a_{k}}{k!}z^k \underbrace{\int^\infty_{0} dt\, e^{ -t }t^k}_{\Gamma(k+1)}=\sum^\infty_{k=0}a_{k}z^k 
$$

Prendiamo ora $f(z)=\sum z^k$. Facciamo nuovamente la trasformata di Borel:
$$
	\Phi(z)=\sum^\infty_{k=0} \frac{z^k}{k!}=e^{z }
$$
Ragionando come prima:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } e^{zt} = \int^\infty_{0}dt \, e^{ -t(1-z) }=\frac{1}{1-z}
$$
In questo modo possiamo trovare continuazioni di $f(z)$ in forma chiusa.

Perchè ci interessa ora? Posso fare ragionamenti analoghi anche con sviluppi asintotici.
Consideriamo uno sviluppo asintotico:
$$
	f(z)=\sum_{k=0}^\infty a_{k}z^k \qquad \text{che non converge}
$$
A questo punto posso fare la trasformata di Borel:
$$
	\Phi(z)=\sum^\infty_{k=0} a_{k} \frac{z_{k}}{k!} \quad \text{generalmente converge in } D
$$
Nel caso in cui la trasformata di Borel converga, posso calcolare $I(z)=f(z)$, "continuazione analitica dello sviluppo asintotico". $f(z)$ è lo sviluppo asintotico di $I(z)$.
In questo caso si dice che la serie è sommabile alla Borel.

Facciamo un esempio concreto.
$$
	f(z)=\sum^\infty_{k=0} k! (-1)^k z^k \implies \Phi(z)=\sum^\infty_{k=0}(-1)^k z^k =\frac{1}{1+z}
$$
Dunque:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } \frac{1}{1+tz}
$$
è la somma di Borel della mia serie divergente.
Paciocchiamo l'integrale:
$$
	I(z)=\int^\infty_{0} dt\, e^{ -t } \frac{1}{\frac{1}{z}+t}=\frac{1}{z} \int^\infty_{\frac{1}{z}} dw\, e^{ 1/z \;-\;w } \frac{1}{w}=\frac{1}{z}e^{ 1/z } \int_{\frac{1}{z}}^\infty dw\,\frac{e^{ -w }}{w}=\frac{1}{z}e^{ 1/z } \Gamma\left( 0, \frac{1}{z} \right)
$$
Dove $\Gamma\left( 0, \frac{1}{z} \right)$ è la gamma incompleta (VAI A VEDERLA).
Laddove ci fosse una singolarità/taglio/punto di diramazione sul cammino di integrazione, l'integrale contenente la trasformata di Borel è ill-defined.

Ad esempio:
$$
	f(z)=\sum^\infty_{k=1} (k-1)! z^k\implies \Phi(z)=\sum^\infty_{k=0} \frac{z^k}{k}=-\log(1-z)
$$
$\Phi(z)$ ha un taglio sull'asse reale da $1$ a $\infty$.
$$
	I(z)=-\int^\infty_{0} e^{ -t } \log(1-zt)\,dt
$$
Ho sempre un punto di diramazione sul cammino di integrazione, indipendentemente dalla scelta del taglio. Questo mi inserisce un'ambiguità, il cammino sta sopra o sotto il taglio.
Passando sopra il punto di diramazione trovo $I_{+}$, passando sotto trovo $I_{-}$.
$$
	\Delta I=\int^\infty_{1} e^{ -t } 2\pi i\, dt= e^{ -1/z } 2\pi i
$$
L'ambiguità comincia in $1$, tra $0$ e $1$ non ho differenaa tra il logaritmo sopra e sotto
Dunque $I_{+}$ e $I_{-}$ diffferiscono di un termine che va esponenzialmente a $0$ per $z\to 0$, in totale analogia a quanto avevamo constatato precedentemente su funzioni diverse con lo stesso sviluppo asintotico.





