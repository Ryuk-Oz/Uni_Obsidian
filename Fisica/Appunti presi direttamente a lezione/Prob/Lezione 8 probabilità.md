
### Problemi di non convergenza

Non sempre troviamo che $\lim_{ t \to \infty }p_{i}(t)=\pi_{i}$.
L'esempio classico è un RW asimmetrico su di un n-ciclo.
Consideriamo una variabile che assume $n$ valori, $x=\{ 0,1,2,\dots,n-1 \}$.
$$
	\begin{cases}
	W_{i,i+1}=p \\
	W_{i,i-1}=1-p
	\end{cases} \quad W_{ij}=0 \text{ se } j \neq i-1,i+1
$$
è un ciclo nel senso che posso saltare solo allo stato precedente o al successivo, in un ciclo appunto.

![[Pasted image 20261027001655.png|404]]

Per simmetria $\pi_{i}=\frac{1}{n}$ (tutti gli stati sono equiprobabili).
Infatti:
$$
	\pi_{j}=\frac{1}{n}=\sum_{i} W_{ij}\pi_{i}=\frac{1}{n}\sum_{i}W_{ij}=\frac{1}{n}[W_{j-1,j}+W_{j+1,j}]=\frac{1}{n}(p+1-p)=\frac{1}{n}
$$
Ma non è detto che $\lim_{ t \to \infty }p_{i}(t)=\pi_{i}(t)$.

Consideriamo ad esempio un 4-ciclo:
$n=4$ e $p=\frac{1}{2}$ con condizione iniziale $\vec{p}(0)=(1,0,0,0)$.
Dopo un passo avrò: $\vec{p}(1)=\left( 0, \frac{1}{2}, 0, \frac{1}{2} \right)$.
Dopo due passi avrò: $\vec{p}(2)=\left( \frac{1}{2}, 0, \frac{1}{2}, 0 \right)$.
E così via:
$\vec{p}(3)=\left( 0, \frac{1}{2}, 0, \frac{1}{2} \right)$ ecc...
il limite per $t\to \infty$ non converge alla distribuzione stazionaria, $\vec{\pi}=\left( \frac{1}{4}, \frac{1}{4}, \frac{1}{4}, \frac{1}{4} \right)$.
Se fossi partito dalla distribuzone stazionaria ci sarei rimasto.
Dunque posso concludere che la convergenza dipende anche dalle condizioni iniziali e che l'esistenza di una sitribuzione stazionaria non basta a garantirne la convergenza.

### Barriere

Occupiamoci di catene con stati dotati di probabilità di transizione particolari.

**Barriera assorbente**

Per rendere chiara l'idea, immaginiamo il modello del random walk 1-d che ad un certo punto incontra un muro sul quale la particella si incolla.
Diciamo che uno stato $0$ è una barriera assordbente se:
$$
	W_{0i}=0 \quad \forall i\neq0 \qquad W_{00}=1
$$
![[Pasted image 20261027225928.png|607]]

**Barriera Riflettente (completamente)**

Una barriera si dice completamente riflettente se:
$$
	W_{00}=0 \quad \text{e esiste un altro stato } i /W_{0i}=1
$$
Cioè non posso restare in 0. Esistono anche barriere parzialmente assorbenti ma sono poco interessanti.

Un esempio classico di barriera assorbente è il modello riproduttivo, la barriera assorbente è lo stato in cui tutti i batteri sono morti e nessuno può riprodursi.
Le barriere riflettenti sono invece barriere di natura prettamente fisica.

**Esempio: Giocatore in Rovina**

Il giocatore entra con un certo capitale di partenza e decide di uscire dal casinò solo in due casi, o se arriva a 0 o se raggiunge un certo capitale, in caso contrario continua.

Consideriamo come capitale iniziale $j$ e voler raggiungere un capitale $c$.

Ogni passo gioco un'unità $1$ e vinco con probabilità $p$. (Perdo con probabilità $1-p$).

$$
	\begin{cases}
	W_{i,i+1}=p \\
	W_{i,i-1}=1-p
	\end{cases}
$$
Di fatto si tratta di un random walk discreto in $d=1$ con 2 barriere assorbenti, $0$ e $c$.

Definiamo l'evento fallimento:
$$
	F:x  \text{ raggiunge } 0 \text{ prima di raggiungere } c
$$
Da quello che abbiamo studiato sui RW sappiamo che la varianza si allarga nel tempo (processo diffusivo), dunque arriverò sicuramente a $0$ o a $c$.
Il fallimento può essere formalizzato nel seguente modo:
Cioè $\exists t /\quad x_{t}=0 \quad \text{e} \quad x_{s}<c \quad \text{per} \quad s<t$. 
Osserviamo come la definizione del fallimento non dipenda dal tempo.

Voglio calcolare la probabilità del fallimento partendo da uno stato $0<j<t$.
$$
\begin{aligned}
	P[F|x_{0}=j]&=P[F|x_{1}=j-1]W_{j,j-1}+P[F|x_{1}=j+1]W_{j,j+1}\\
	&=(1-p)P[F|x_{1}=j-1]+pP[F|x_{1}=j+1]
\end{aligned}
$$
Introduciamo la probabilità di fallimento:
$$
	u_{j}=P[F|x_{0}=j]=(1-p)u_{j-1}+p u_{j+1}
$$
E abbiamo ottenuto un'equazione alle differenze finite (analogo discreto di un'equazione differenziale).
Ovviamente $u_{0}=1$ e $u_{c}=1$, queste sono le nostre condizioni al contorno
Equazioni di questo tipo sono difficili da studiare, ma possiamo sfruttare quello che sappiamo sulle equazioni differenziali lineari.
So che le equazioni differenziali lineari hanno soluzioni esponenziali, allora provo a cercare una soluzione di tipo esponenziale, tipo $u_{j}=\alpha^j$.
(Analogo a $e^{ \alpha t }$ per ODE lineari).
Sostituiamo la soluzione nell'equazione:
$$
\begin{aligned}
\alpha^j&=(1-p)\alpha^{j-1}+p\alpha^j\\
1&=(1-p) \frac{1}{\alpha}+p\alpha \\
&\alpha^2 p-\alpha+q=0 \qquad q=1-p\\ 
\implies \alpha&= \frac{1\pm \sqrt{ 1-4pq }}{2p}= \frac{1\pm(1-2p)}{2p}
\end{aligned}
$$
Le due soluzioni sono $\alpha=1$ e $\alpha=\frac{1-p}{p}$.
La soluzione generale sarà:
$$
	u_{j}=c_{1} \left(\frac{1-p}{p}\right)^j+c_{2}
$$
Fisso le 2 costanti con le condizioni al contorno:
$$
	\begin{cases}
	u_{0}=c_{1}+c_{2}=1 \\
	u_{c}=c_{1} \left( \frac{1-p}{p} \right)^c+c_{2}=0
	\end{cases}
$$
Risolvendo il sistema troviamo:
$$
	\begin{cases}
	c_{1}= \frac{1}{1-\left( \frac{q}{p} \right)^c} \\
	c_{2}=-\frac{\left( \frac{q}{p} \right)^c}{1-\left( \frac{q}{p} \right)^c}
	\end{cases}
$$
La soluzione generale è dunque:
$$
	u_{j}=\frac{1}{1-\left( \frac{q}{p} \right)^c} \left(\frac{1-p}{p}\right)^j -\frac{\left( \frac{q}{p} \right)^c}{1-\left( \frac{q}{p} \right)^c} = \frac{ \left( \frac{q}{p} \right)^j-\left( \frac{q}{p} \right)^c }{1-\left( \frac{q}{p} \right)^c}
$$
Questa è la probabilità di fallire partendo da uno stato $j$.

Distinguiamo 2 casi:

**Gioco equo**: $p=\frac{1}{2}$ e $q=\frac{1}{2}$, allora $\frac{q}{p}$=1
    In questo caso troviamo: $\alpha=\frac{q}{p}=1$, le 2 soluzioni elementari coincidono
    e la soluzione generale diventa $u_{j}=c_{1}+c_{2}j$
    Imponendo le condizioni al contorno troviamo $u_{j}=1-\frac{j}{c}$.

Nel caso di gioco equo il risultato è ovvio:

![[Pasted image 20261028000250.png|390]]

La probabilità di fallire è lineare, più $j$ è vicino a $c$ più alta è la probabilità di vincita e si abbassa quella di fallimento.

**Gioco non equo:** $p<q$
    Se il gioco è non equo, anche un piccolo svantaggio porta sicuramente alla rovina.

Per capire meglio il significato della formula che abbiamo già trovato, andiamo a sostituire dei valori numerici, tramite un esempio concreto, il **Gioco della roulette**.

Nel gioco della roulette ho 18 rossi, 18 neri e un verde.
Ipotizziamo di scommettere sempre sul nero.
$p=\frac{18}{37}\simeq 0.486 < \frac{1}{2}$ Il gioco è non equo, anche se di poco.
Scegliamo $j=500$ euro e $c=1000$ euro.
$\frac{q}{p}=\frac{19}{18}>1$.
Riprendo la formula di prima:
$$
	u_{500}=\frac{\left( \frac{q}{p} \right)^{500}-\left( \frac{q}{p} \right)^{1000}}{1-\left( \frac{q}{p} \right)^{1000}}\simeq 1-1.8 \cdot 10^{-12}
$$
Dunque la probabilità di vincere vale circa $1.8 \cdot 10^{-12}$.
Da un POV fisico il fallimento è praticamente certo.
Dunque la strategia migliore per raddoppiare è puntare tutto la prima volta, in questo caso la probabilità di vittoria è $0.486$, anche se è una strategia poco divertente.

Generalizzando quanto discusso fin'ora troviamo che la probabilità di raggiungere una barriera è:
$$
	u_{j}=\sum_{i} W_{j,i}u_{i}
$$
Con annesse condizioni al contorno.
In forma matriciale questa è $\vec{u}=W\vec{u}$ , contrario di $\vec{\pi}=\vec{\pi}W$.
La prima prende il nome di Equazione di Kolmogorov Backward, la seconda Forward.