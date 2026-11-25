
### Equazioni differenziali lineari del secondo ordine (a coefficienti costanti)
 $$
	u''(z)+P(z)u'(z)+Q(z)u(z)=0
 $$
 A metodi 1 abbiamo imparato a risolvere equazioni di questo tipo in intorni di punti Fuchsiani, $\xi$.
 Un punto $\xi$ si dice fuchsiano se:
$$
	P(z)\underset{z\to \xi}{\sim} \frac{p(z)}{z-\xi}, \qquad Q(z)\underset{z\to \xi}{\sim} \frac{q(z)}{(z-\xi)^2}
 $$
 In particolare all'$\infty$ distinguiamo i due casi:
 $\infty$ non fuchsiano:
$$
	P(z)\sim \frac{2}{z}+O\left( \frac{1}{z^2} \right) , \qquad Q(z)\sim \frac{B}{z^4}+O\left( \frac{1}{z^5} \right)
 $$
 $\infty$ fuchsiano:
$$
	P(z)\sim \frac{A}{z}+O\left( \frac{1}{z^2} \right), \qquad Q(z)\sim \frac{B}{z^2}+O\left( \frac{1}{z^3} \right)
 $$
 Per studiare l'$\infty$ si usa il seguente cambio di variabile nell'equazione differenziale, $z=\frac{1}{w}$ e la si studia nell'intorno di $w=0$. Ricordandoci di dover tener conto di come agisce il cambio di variabile sulle derivate:
$$
	P(z)\to P\left( \frac{1}{w} \right)=\hat{P}(w)
 $$
 con $\hat{P}$ che è una funzione DIVERSA da $P$.

Quando $P(z)$ e $Q(z)$ sono regolari, l'integrale generale $k_{1} u_{1}(z)+k_{2}u_{2}(z)=u(z)$ è regolare.
Al contrario, dove $P(z)$ e $Q(z)$ sono singolari, in generale lo è anche l'integrale generale.
In particolare nel caso di $\xi$ singolarità fuchsiane sono in grado di trovare 2 parametri $\alpha$ e $\beta$ ($\alpha>\beta$) tali che:
$$
	u(z)=k_{1}u_{1}(z)+k_{2}u_{2}(z)
$$
con $u_{1}(z)=(z-\xi)^\alpha +\sum a_{k}(z-\xi)^k$ e $u_{2}(z)=(z-\xi)^\beta \sum_{k} d_{k}(z-\xi)^k+A\log(z-\xi)$.
Il termine logaritmico è sempre presente laddove $\alpha=\beta$, negli altri casi potrei avere $A=0$.
Come trovo $\alpha$ e $\beta$?
$$
	\begin{cases}
	\lim_{ z \to \xi } (z-\xi)P(z)=p(\xi)=p_{0} \\
	\lim_{ z \to \xi } (z-\xi)^2Q(z)=q_{0}
	\end{cases}
$$
A questo punto risolviamo l'equazione indiciale:
$$
	\rho^2+(p_{0}-1)+q_{0}=0
$$
per trovare $\alpha$ e $\beta$.
(All'infinito l'equazione indiciale è $\rho^2-(p_{0}-1)+q_{0}=0$).

A metodi 1 abbiamo dato in pasto questa soluzione all'equazione differenziale e abbiamo verificato che funzionasse.

### Equazioni totalemente fuchsiane

Oggi ci occupiamo di equazioni TOTALMENTE fuchsiane, cioè equazioni per le quali TUTTE le singolarità sono punti Fuchsiani.

Supponiamo ci siano $n$ punti fuchsiani $\xi_{i}$. $P(z)$ deve essere necessariamente la somma di tanti termini del seguente tipo:
$$
	P(z)=\frac{A_{1}}{z-\xi_{1}}+\frac{A_{2}}{z-\xi_{2}}+\dots+\frac{A_{n}}{z-\xi_{n}}
$$
Nel caso in cui l'infinito sia regolare devo trovare che $\sum_{i} A_{i}=2$ per quanto già visto nelle equazioni non totalmente fuchsiane.

Per $Q(z)$ la forma è meno ovvia. Possiamo iniziare scrivendo:
$$
	Q(z)=\frac{q_{2n-4}(z)}{(z-\xi_{1})^2(z-\xi_{2})^2\dots(z-\xi_{n})^2}
$$
Il polinomio $q_{2n-4}(z)$ non è completamente determinato. (Il grado del polinomio è $2n-4$ per accomodare il caso di infinito regolare).
Posso riscriverlo in serie come:
$$
	Q(z)=\sum_{i=1}^n \left( \frac{\hat{B}i}{(z-\xi_{i})^2}+ \frac{C_{i}}{(z-\xi_{i})} \right)
$$
Se l'$\infty$ è fuchsiano queste forme variano leggermente.

**Oss:** nell'intorno di un singolo punto il ragionamento di Fuchs che abbiamo rivisto in precedenza continua ad essere valido.

Possiamo dimostrare che conoscendo la posizione dei punti fuchsiani la funzione $P$ è completamente determinata ma lo stesso non vale per $Q$. Possiamo determinare i coefficienti $\hat{B}_{i}$ ma non i coefficienti $C_{i}$. Infatti:
$$
	\begin{cases}
	p_{0}=\lim_{ z \to \xi_{i} } P(z)(z-\xi_{i})=A_{i} \\
	q_{0}=\lim_{ z \to \xi_{i} } Q(z)(z-\xi_{i})^2=\hat{B}_{i}  
	\end{cases}
$$
risolvendo l'equazione indiciale:
$$
	\rho^2+(A_{i}-1)\rho + \hat{B}_{i}=0
$$
e troviamo $\alpha_{i}\beta_{i}=\hat{B}_{i}$ e $\alpha_{i}+\beta_{i}=1-A_{i}$.
**Oss:**
$$
	\sum^n_{i=1} (\alpha_{i}+\beta_{i})=\sum^n_{i=1} (1-A_{i})=n-2
$$
(nel caso in cui l'eq. sia regolare all'infito).
Dunque i vari $\alpha_{i}, \beta_{i}$ non sono tra loro indipendenti ma dipendono dai valori di $\alpha_{j}, \beta_{j}$.

Dunque la condizione di fuchsianità TOTALE restringe enormemente il numero di soluzioni possibili.

Proviamo a vedere cosa succede incrementando gradualmente il numero di punti Fuchsiani.

### 1 punto fuchsiano

Iniziamo dal caso a 1 punto fuchsiano e supponiamo che questo punto sia $z=\infty$.
Se l'unico punto fuchsiano è $z=\infty$ allora $P(z)$ e $Q(z)$ devono essere regolari $\forall z$ al finito, e:
$$
	P \underset{z\to \infty}{\sim} \frac{A}{z}+\dots, \qquad Q(z)\underset{z\to \infty}{\sim} \frac{B}{z^2}+\dots
$$
Dunque sono regolari anche all'infinito.
L'unica funzione regolare ovunque che sia annulla all'infinito è:
$$
	P=Q=0
$$
e l'equazione diventa banale:
$$
	u''(z)=0\implies u(z)=az+b
$$

Studiamo ora il caso di un punto fuchsiano in $z=\xi$.
$$
	P(z)=\frac{p(z)}{z-\xi}= \frac{A}{z-\xi}
$$
$$
	Q(z)=\frac{q(z)}{(z-\xi)^2} = \frac{B}{(z-\xi)^2}
$$
A questo punto imponiamo che l'$\infty$ si regolare e otteniamo $A=2$ e $B=0$.
l'equazione diventa:
$$
	u''+\frac{z}{z-\xi}u'=0 \implies u(z)=\frac{a_{1}}{z-z_{0}}+a_{0}
$$
Facendo un cambio di variabile (trasformazione di Moebius) del tipo:
$$
	w=\frac{1}{z-\xi}
$$
ritroviamo un equazione per $w$ con punto fuchsiano all'infinito e regolare al finito.

### 2 punti fuchsiani

Iniziamo dallo studio del caso in cui $0$ e $\infty$ sono punti fuchsiani.

Iniziamo guardando lo $0$.
$$
	P(z)\sim O\left( \frac{1}{z} \right), \quad P(z)=\frac{A}{z}+c_{0}+c_{1}z+\dots
$$
$$
	Q(z)\sim O\left( \frac{1}{z^2} \right),\quad Q(z)=\frac{B}{z^2}+\frac{d_{-1}}{z}+d_{0}z+d_{0}+d_{1}z+\dots
$$
Intorno all'$\infty$ troviamo invece:
$$
	P(z)\sim O\left( \frac{1}{z} \right),\quad P(z)=\frac{\hat{A}}{z}+\frac{a_{2}}{z^2}+\dots
$$
$$
	Q(z)\sim O\left( \frac{1}{z^2} \right), \quad \frac{\hat{B}}{z^2}+\frac{b_{3}}{z^3}+\dots
$$
Se queste sono le uniche singolarità, allora il raggio di convergenza dei due sviluppi è $\infty$, pertanto:
$$
	\begin{cases}
	P(z)=\frac{A}{z} \\
	Q(z)=\frac{B}{z^2}
	\end{cases}
$$
Se questo è vero, l'equazione diventa:
$$
	u''+\frac{A}{z}u'+\frac{B}{z^2}u=0
$$
A questo punto, è facile osservare che sotto il cambio di variabile $z=e^{ w }$, l'equzione diventa:
$$
	\frac{d^2u}{dw^2}+(A-1) \frac{du}{dw}+Bu=0
$$
che è un equazione a coefficienti costanti.

Questa la sappiamo risolvere. Risolviamo l'equazione indiciale:
$$
	\rho^2+(A-1)+B=0\implies \alpha,\beta
$$
se $\alpha \neq \beta$ abbiamo:
$$
	u(\omega)=k_{1}e^{ \alpha \omega }+k_{2}e^{ \beta \omega }\to u(z)=k_{1}z^\alpha+k_{2}z^\beta
$$
se $\alpha=\beta$:
$$
	u(\omega)=k_{1}e^{ \alpha \omega }+k_{2}\omega e^{ \alpha \omega }\to u(z)=k_{1}z^\alpha+k_{2}\log z \, z^\alpha
$$
Risolvendo con il metodo di Fuchs e trovando la relazione di ricorrenza per i $c_{k}$ otterremmo gli stessi risultati (fai come esercizio).

All'infinito l'equazione indiciale è $\rho^2-(A-1)\rho + q=0$ e le soluzioni sono $-\alpha,-\beta$.

Discorsi analoghi si possono fare fissando 2 punti fuchsiani qualunque.

### 3 punti Fuchsiani

considero $\xi_{1}, \xi_{2}, \xi_{3}$ tutti al finito. Sappiamo che:
$$
	P(z)=\frac{A_{1}}{z-\xi_{1}}+\frac{A_{2}}{z-\xi_{2}}+\frac{A_{3}}{z-\xi_{3}}
$$
e $Q(z)$ si può scrivere come:
$$
	Q(z)=\frac{1}{\prod^3_{i=1} (z-\xi_{i})}\left[ \frac{B_{1}}{z-\xi_{1}}+\frac{B_{2}}{z-\xi_{2}}+\frac{B_{3}}{z-\xi_{3}} \right]
$$
All'infinito questa va come $\sim \frac{B_{1}+B_{2}+B_{3}}{z^4}$, cioè $\infty$ è regolare.

Calcoliamo l'equazione indiciale in un punto fuchsiano generico:
$$
	p_{0}=\lim_{ z \to x_{i} } P(z)(z-\xi_{i})=Ai
$$
$$
	q_{0}=\lim_{ z \to \xi_{i} }Q(z)(z-\xi_{i})^2 = \frac{B_{i}}{(\xi_{i}-\xi_{i+1})(\xi_{i}-\xi_{i-1})}=\hat{B}_{i} 
$$
A questo punto:
$$
	\rho^2+(A_{i}-1)\rho + \hat{B}_{i}=0
$$
e otteniamo:
$$
	\begin{cases}
	\alpha_{i}\beta_{i}=\hat{B}_{i} \\
	\alpha_{i}+\beta_{i}=1-A_{i}
	\end{cases}
$$

Se come punti fuchsiani avessi scelto $\xi_{1},\xi_{2}, \infty$ avrei avuto:
$$
		P(z)=\frac{A_{1}}{z-\xi_{1}}+\frac{A_{2}}{z-\xi_{2}}+\frac{A_{3}}{z-\xi_{3}}
$$
$$
		Q(z)=\frac{1}{\prod^3_{i=1} (z-\xi_{i})}\left[ \frac{B_{1}}{z-\xi_{1}}+\frac{B_{2}}{z-\xi_{2}}+C \right]
$$
A questo punto ricalcoliamo l'equazone indiciale (per il punto attorno all'infinito):
$$
	\begin{cases}
	p_{0}=\lim_{ z \to \infty }  zP(z)=A_{1}+A_{2} \\
	q_{0}=\lim_{ z \to \infty } z^2Q(z)=C
	\end{cases}
$$
dunque:
$$
	\rho^2-(A_{1}+A_{2}-1)\rho +C=0
$$
$$
	\begin{cases}
	\alpha_{3}\beta_{3}=C \\
	\alpha_{3}+\beta_{3}=A_{1}+A_{2}-1
	\end{cases}
$$
E troviamo effettivamente 
$$
	\sum^3_{i=1}\alpha_{i}+\beta_{i}=3-2=1
$$

### Simbolo di Riemann

Il comportamento della soluzione dipende dai 3 punti singolari, e dalle soluzioni all'equazione indiciale. Queste informazioni sono racchiuse nel simbolo di Riemann.
$$
	P \begin{Bmatrix}
	\xi_{1} & \xi_{2} & \xi_{3} \\
	\alpha_{1} & \alpha_{2} & \alpha_{3}  & z\\
	\beta_{1} & \beta_{2} & \beta_{3}
	\end{Bmatrix}
$$
Questi simboli permettono di semplificare notevolemente la soluzione.
Posso ad esempio scambiare le colonne del simbolo di riemann, infatti i punti del piano complesso non sono ordinati.
Altre proprietà meno ovvie sonmo se le seguenti:
$$
		P \begin{Bmatrix}
	\xi_{1} & \xi_{2} & \xi_{3} \\
	\alpha_{1} & \alpha_{2} & \alpha_{3}  & z\\
	\beta_{1} & \beta_{2} & \beta_{3}
	\end{Bmatrix}=P \begin{Bmatrix}
	\xi_{1}' & \xi_{2}' & \xi_{3}' \\
	\alpha_{1} & \alpha_{2} & \alpha_{3} & z' \\
	\beta_{1} & \beta_{2} & \beta_{3}
	\end{Bmatrix}
$$
dove ho applicato una trasformazione di moebius:
$$
	z'=\frac{az+b}{cz+d}, \qquad \xi_{i}'= \frac{a\xi_{i}+b}{c\xi_{i}+d}
$$
Con un po' di conti questo si può verificare (prova a casa).
Possiamo dimostrarlo facilemte localmente:
$$
	\begin{aligned}
	(z'-\xi_{i}')^{\alpha_{i}}&=\left( \frac{az+b}{cz+d}-\frac{a\xi_{i}+b}{c\xi_{i}+d} \right)^{\alpha_{i}}\\ 
	&=\frac{(\cancel{acz\xi_{i}}+adz+bc\xi_{i}+\cancel{bd}-\cancel{ac\xi_{i}z}-ad\xi_{i}-czb-\cancel{bd})^{\alpha_{i}}}{(cz+d)(c\xi_{i}+d)}\\
	&=\frac{((ad-bc)z-(ad-bc)\xi_{i})^{\alpha_{i}}}{(cz+d)(c\xi_{i}+d)}= \frac{(ad-bc)^ {\alpha_{i}}(z-\xi_{i})^{\alpha_{i}}}{(cz+d)(c\xi_{i}+d)}\underset{z\to \xi_{i}}{\sim} K(z-\xi_{i})^{\alpha_{i}}
	\end{aligned}
$$
Un altra propretà utile è:
$$
\begin{aligned}
	P \begin{Bmatrix}
	\xi_{1} & \xi_{2} & \xi_{3} \\
	\alpha_{1} & \alpha_{2} & \alpha_{3}  & z\\
	\beta_{1} & \beta_{2} & \beta_{3}
	\end{Bmatrix} = (z-\xi_{1})^{\gamma_{1}}(z-\xi_{2})^{\gamma_{2}}(z-\xi_{3})^{\gamma_{3}}P\begin{Bmatrix}
	\xi_{1} & \xi_{2} & \xi_{3} \\
	\alpha_{1}-\gamma_{1} & \alpha_{2}-\gamma_{2} & \alpha_{3}-\gamma_{3} & z \\
	\beta_{1}-\gamma_{1} & \beta_{2}-\gamma_{2} & \beta_{3}-\gamma_{3}
	\end{Bmatrix}
\end{aligned}
$$

Con $\gamma_{1}+\gamma_{2}+\gamma_{3}=0$
...
...
$$
	\hat{u}=k_{1}(z-\xi_{1})^{\alpha_{1}-\gamma_{1}} \sum^\infty_{k=0} c_{k}(z-\xi_{1})^k+k_{2}(z-\xi_{2})^{\beta_{1}-\gamma_{1}}\sum_{k=0}^\infty d_{k}(z-\xi_{1})^k+\dots
$$
Così facendo posso andare ad annullare degli indici.
e posso sempre ricondurmi al caso di simbolo di Riemann:
$$
	P=\begin{Bmatrix}
	0 & 1 & \infty \\
	0 & 0 & a & z \\
	1-c & c-a-b & b
	\end{Bmatrix}
$$

