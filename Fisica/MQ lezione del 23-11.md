
Equazione di shrodinger radiale:
$$
	-\frac{\hbar^2}{2\mu}\left( \frac{d^2}{dr^2}+\frac{2}{r} \frac{d}{dr} \right)\varphi(r)+\left( V(r)+ \frac{\hbar l(l+1)}{2\mu r^2} \right)\varphi(r)=E\varphi(r)
$$
Possiamo passare all'EdS ridotta definendo:
$$
	\chi(r)\equiv r\varphi(r)\implies \varphi(r)=\frac{\chi(r)}{r}
$$
e:
$$
	\begin{aligned}
	\frac{d\varphi}{dr}&=-\frac{1}{r^2} \chi(r)+\frac{1}{r} \frac{d\chi}{dr}\\
	\frac{d^2\varphi}{dr^2} &=\frac{2}{r^3} \chi(r) -\frac{2}{r^2} \frac{d\chi}{dr} +\frac{1}{r} \frac{d^2\chi}{dr^2}
	\end{aligned}
$$
sostituendo nell'edS il pezzo cinetico si semplifica a $\frac{1}{r} \frac{d^2\chi}{dr^2}$.
Il termine cinetico contiene un $\frac{1}{r}$ ma questo è presente anche nel termine potenziale e al di là dell'uguale (all'interno di $\varphi(r)$) e posso semplificarlo.
Dunque:
$$
	\frac{d^2\chi}{dr^2}+\left[  \frac{2\mu}{\hbar^2}(E-V(r))-\frac{l(l+1)}{r^2} \right]\chi(r)=0
$$
Possiamo fare alcune considerazioni:
1. il termine $\frac{l(l+1)}{r^2}$ è un potenziale repulsivo proporzionale al momento angolare, si tratta dunque del termine centrifugo (barriera centrifuga).
$$
	V_{eff}(r)\equiv V(r)+ \frac{\hbar^2l(l+1)}{2\mu r^2}
$$
2. Un ICOC è costituita da $\{ H,L^2,L_{z} \}$. Infatti:
$$
	[L^2,p_{r}^2]=0\implies\left[ L^2,|\vec{p}|^2=p_{r^2}+\frac{|\vec{L}|^2}{r^2} \right]\implies[L^2,H]=0
$$
in quanto $H=\frac{|\vec{p}|^2}{2\mu}+V(r)$.
In modo analogo $[L_{z},H]=0$ e sappiamo già che $[L^2,L_{z}]=0$.
Nel caso classico avrei 6 osservabili, come atteso nel caso quantistico ne ho 3.

3. $\varphi(r)\to \varphi_{nl}(r)$ e ($E\to E_{n}$ per STATI legati). 
   La soluzione generale sarà:
$$
   	\psi(r,\theta,\varphi)=\sum_{n,l,m} c_{nlm} \varphi_{nl}(r)Y^{m}_{l}(\theta,\varphi)
   $$
4. Normalizzazione in coordinate polari sferiche:
$$
\begin{aligned}
	1&=(\psi_{nlm}, \psi_{nlm})\equiv \int d^3r |\psi_{nlm}|^3 \\
&=\int^\infty_{0} dr\, r^2\, |\varphi_{nl}|^2 \underbrace{\int^1_{-1} d\cos \theta \int^{2\pi}_0 d\varphi\, |Y_{l}^m(\theta,\varphi)|^2}_{=1} =\\
&=\int^\infty_{0} dr\, |\chi_{nl}|^2
\end{aligned}
$$
5. Condizioni al contorno per $\chi_{nl}(r)$
$$
	\chi_{nl}(r)\underset{r\to \infty}{\to} 0, \qquad \chi_{nl}(r)\sim r^{-\alpha},\, \text{con } \alpha> \frac{1}{2}
$$
$$
	\chi_{nl}(r)\underset{r\to 0}{\to}0
   $$
   L'ultima richiesta non dipende dalla normalizzabilità ma è richiesta affinchè $\varphi_{nl}(r) \in \mathcal{D}(p_{r}^2)$.

### Atomi idrogenoidi

Iniziamo scrivendo il potenziale in gioco:
$$
	v(r)=-\frac{Ze^2}{r}
$$
$Z$ è il numero di protoni. Stiamo lavorando con unità di misura gaussiane, tali che $4\pi\varepsilon_{0}=1$.
Dunque l'hamiltoniana sarà:
$$
	H=-\frac{\hbar^2}{2\mu}\Delta -\frac{Ze^2}{r}
$$
L'equazione radiale ridotta sarà:
$$
	\frac{d^2\chi}{dr^2}+\left[ \frac{2\mu}{\hbar^2}\left( E+\frac{Ze^2}{r} \right)-\frac{l(l+1)}{r^2} \right]\chi(r)=0
$$
Come abbiamo fatto per l'oscillatore armonico, devo rendere l'equazione adimensionale.
Definisco una variabile $\rho\equiv \alpha r$ con $[\alpha]=L^{-1}$.
Come costruisco $\alpha$?
$$
	\alpha\equiv 2 \frac{\sqrt{ -2\mu E }}{\hbar}
$$
(Sto studiando gli stati legati, dunque l'energia è negativa).
I fattori 2 sono inseriti per comodità a posteriori.
$$
	\left[ \frac{\mu E}{\hbar^2} \right] = \frac{ME}{(E\cdot T)^2}=\frac{ME}{T^2}=\frac{1}{L^2}
$$
Sostituiamo nell'equazione.
$$
	\alpha^2 \frac{d^2\chi}{d\rho^2}+\left[ -\frac{\alpha^2}{4}+\frac{2\mu Ze^2}{\hbar^2} \frac{\alpha}{\rho}-\alpha^2 \frac{l(l+1)}{\rho^2} \right]\chi(\rho)=0
$$
divido per $\alpha^2$:
$$
	\frac{d^2\chi}{d\rho^2}-\left[ \frac{1}{4}+\frac{\lambda}{\rho}+\frac{l(l+1)}{\rho^2} \right]\chi(\rho)=0
$$
**OSS:** $\lambda$ dev'essere un numero puro.
$$
	\lambda\equiv \frac{2\mu Ze^2}{\hbar^2} \frac{1}{\alpha} = \frac{Ze^2}{\hbar}\sqrt{ -\frac{\mu}{2E} }
$$
$$
	[\lambda]=\frac{EL}{ET}\sqrt{ \frac{M}{E} }=\frac{L}{T} \frac{T}{M}=1
$$
**OSS:** $\lambda$ nasconde tutto il contenuto fisico riguardante l'atomo di idrogeno, dunque lo spettro dell'atomo dovrà dipendere da $\lambda$.

### Comportamenti asintotici

#### 1. $r\to \infty$

Il comportamento all'infinito lo trovo prendendo il termine dominante.
$$
	\frac{d^2\chi_{AS}}{d\rho^2}-\frac{1}{4}\chi_{AS}(\rho)=0 \implies \chi_{AS}(\rho)\propto e^{ \pm \rho/2 }\to \chi_{AS}(\rho)\sim e^{ -\rho/2 }
$$
Dunque:
$$
	\chi(\rho)\equiv e^{ -\rho/2 }Q(\rho)
$$
Ovviamente escludiamo le $Q(\rho)$ che mi vanno a invertire l'andamento all'infinito.
Risolviamo alla shhrodinger e non alla Heisenberg perchè più semplice.
$$
	\chi'(r)=\left( -\frac{Q(\rho)}{2}+Q'(\rho) \right)e^{ -\rho/2 }
$$
$$
	\chi''(\rho)=\left( \frac{Q(\rho)}{4}-Q'(\rho)+Q''(\rho) \right)e^{ -\rho/2 }
$$
Sostituendo nell'equazione otteniamo:
$$
	Q''(\rho)-Q'(\rho)+\left( \frac{\lambda}{\rho}-\frac{l(l+1)}{\rho^2} \right)Q(\rho)=0
$$
**NB:** $Q(\rho)=Ce^{ \rho }$ è soluzione per $\rho\to \infty$ e dovrò buttarla via, allora $Q(\rho)$ dovrà essere un polinomio.

#### 2. $r\to{0}$

$\rho=0$ è un possibile punto singolare per la soluzione.
Non solo, si tratta di una singolarità fuchsiana!
In particolare troviamo:
$$
	\begin{cases}
	p_{0}=0 \\
	q_{0}=-l(l+1)
	\end{cases}
$$
I comportamenti asintotici di $Q(\rho)$ per $\rho\to 0$ sono determinati dall'equazione indiciale.
$$
	x^2+(p_{0}-1)x+q_{0}=x^2-x-l(l+1)=0\implies x=\begin{cases}
	l+1 \\
	-l
	\end{cases}
$$
Dunque ci sono 2 possibilità:
$$
	Q(\rho)\underset{\rho\to{0}}{\sim} \rho^{l+1}\quad \text{oppure} \quad Q(\rho)\underset{\rho\to 0}{\sim} \rho^{-l}
$$
MA $Q(\rho)= \rho^{-l}$ non va bene perchè abbiamo imposto come condizione al contorno che $\chi(\rho)\to{0}$ nell'origine. Non va bene neanche per $l=0$!

Dunque:
$$
	\chi(\rho)=e^{ -\rho/2 } Q(\rho); \quad Q(\rho)=\rho^{l+1} \sum^\infty_{k=0}c_{k} \rho^k, \quad c_{0}\neq 0
$$
Se la serie non terminasse troverei $Q(\rho)\underset{\rho\to \infty}{\sim}e^{ \rho }$, dunque la serie si deve troncare, cioè $Q(\rho)$ è un polinomio.

Per questo motivo:
$$
\forall, \, \exists n': \forall k>n', \, c_{k}=0 \quad \text{e} \quad c_{n'}\neq 0
$$
$\implies Q(\rho)\sim \rho^{l+1+n'}$ per $\rho\to \infty$.

Sostituisco nell'equazione per $Q(\rho)$ la potenza dominante:
$$
	(l+1+n')(l+n') \rho^{l+n'-1}-(l+1+n')\rho^{l+n'}+\lambda \rho^{l+n'}-l(l+1)\rho^{l+n'-1}=0
$$
Le potenze in $l+n'-1$ soffrono di un contributo dei termini successivi di $Q(\rho)$, al contrario i termini dominanti (potenze in $l+n'$) sono determinati.
Dunque:
$$
	[\lambda-(l+1+n')]\rho^{l+n'}=0\implies \lambda=n'+l+1\equiv n
$$
con $n',l$ interi.
Ma $n$ non è un parametro libero, bensì è vincolato nel seguente modo:
$$
	n\geq l+1 \implies l\leq n-1
$$
Ricordando che:
$$
	\lambda^2 = -\frac{\mu Z^2 e^{ 4 }}{2E\hbar^2}=n^2
$$
Cioè:
>[!abstract] Spettro di un atomo idrogenoide
>
>$$
>	E_{n}=-\frac{\mu Z^2 e^4}{2\hbar^2} \frac{1}{n^2}
>$$

### Degenerazione dell'autovalore $E_{n}$
$$
	D(n)= \sum_{l=0}^{n-1} (2l+1)=2 \frac{n(n-1)}{2}+n=n^2-n+n=n^2
$$
Di norma le degenerazioni sono date da simmetrie. Una simmetria è chiaramente quella per rotazione, ma non basta a spiegare una degenerazione così grande, in realtà c'è un altro gruppo di simmetria "nascosto".

### Funzione d'onda

Ci sono i polinomi di Laguerre.
$$
	\chi_{nl}(\rho)=N_{nl} \rho^{l+1} e^{ -\rho/2 } L_{n-l-1}^{2l+1}(\rho)
$$
con:
$$
	L_{p}^\beta (x)\quad \text{è il polinomio associato di Laguerre, di grado } p
$$
Anche questo ha una funzione generatrice:
$$
	F_{\beta}(x,z)= \frac{1}{(1-z)^{\beta+1}} e^{ -zx/(1-z) }\equiv \sum_{p=0}^\infty L_{p}^{\beta}(x) z^{p}
$$







