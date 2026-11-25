
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

Osservazione:
le $\pi_{j}$ sono normalizzate ma le $u_{j}$ no! La backward non mantiene la normalizzazione.

**Uscita da due barriere**

Studiamo la probabilità di uscire dalle barriere in generale, non da una barriera specifica

Caso simmetrico ($p=\frac{1}{2}$).

Parto da uno stato $0\leq j\leq c$. Lo studio è esattamente lo stesso ma cambiano le condizioni al contorno. Nello studio di uscita da una barriera qualsiasi queste diventano:
$u_{0}=1$, $u_{c}=1$.
Sappiamo già la soluzione della B-Kolmogorov nel caso simmetrico:
$$
	u_{j}=c_{1}+jc_{2}
$$
Imponiamo le nuove condizioni al contorno:
$$
	\begin{cases}
	u_{0}=c_{1}=1 \\
	u_{c}=c_{1}+c\, c_{2}=1
	\end{cases}
$$
Risolvendo troviamo $u_{j}=1$. L'uscita nel caso di random walk simmetrico con due barriere finite è garantita!

Qual è il tempo medio di uscita?
Definiamo $T_{j}=$ numero di passi per raggiungere la barriera (in 0 o c) partendo da $j$.
Risulta ovvio che $T_{0}=T_{c}=0, \, T_{j}\geq 0$.
La relazione di ricorrenza per i tempi di uscita è:
$$
	T_{j}=T_{j-1}W_{j,j-1}+T_{j+1}W_{j,j+1}+1
$$
Il fattore $+1$ è quello che mi va a contare l'incremento temporale.
Nel caso simmetrico ho:
$$
	T_{j}=\frac{1}{2} T_{j-1}+\frac{1}{2} T_{j+1}+1
$$
Proviamo a risolvere quest'equazione ricordando il legame tra derivata e incrementi discreti.
Definiamo $d_{j}\equiv T_{j}-T_{j-1}$
A questo punto:
$$
	\begin{aligned}
	T_{j}-T_{j-1}&=\frac{1}{2}T_{j-1}+\frac{1}{2}T_{j+1}+1-T_{j-1}\\
	d_{j}&=1+\frac{1}{2}T_{j+1}-\frac{1}{2}T_{j-1}=1+\frac{1}{2}(T_{j+1}-T_{j})+\frac{1}{2} (T_{j}-T_{j-1})\\
	d_{j}&=1+\frac{1}{2}d_{j+1}+\frac{1}{2}d_{j}\\
	\implies d_{j+1}&=d_{j}-2
	\end{aligned}
$$
Siamo passati da 3 a 2 indici, che è più comodo da studiare.
Studiamo il caso per $j=1$ per poi generalizzare.
$$
	\begin{cases}
	j=1 & T_{1}=d_{1} \\
	j=2 & d=T_{2}-T_{1}=T_{2}-d_{1}\implies T_{2}=d_{1}+d_{2} \\
	\dots \\
	j \text{ generico}  & T_{j}=\sum^j_{k=1} d_{k}
	\end{cases}
$$
Ricaviamo i $d_{k}$:
$$
	\begin{cases}
	d_{2}=d_{1}-2 \\
	d_{3}=d_{2}-2=d_{1}-4 \\
	\dots \\
	d_{k}=d_{1}-2(k-1)
	\end{cases}
$$
Sostituendo in $T_{j}$:
$$
	T_{j}=\sum^j_{k=1} [d_{1}-(k-1)2]=d_{1}j-2\sum^{j-1}_{k=0} k
$$
Sappiamo fare questa somma grazie a gauss:
$$
	T_{j}=jT_{1}-\frac{2(j-1)j}{2}=jT_{1}-j(j-1)
$$
Applichiamo le condizioni al contorno
$$
	0=T_{c}=cT_{1}-c(c-1)\implies T_{1}=c-1
$$
Alla fine otteniamo:
$$
	T_{j}=j(c-j)
$$
Il tempo di uscita scala in modo quadratico, come l'andamento lineare della varianza, anche questo è un risultato generale per processi diffusivi.
Per $j=\frac{c}{2}$ abbiamo:
$$
	T_{\frac{c}{2}}= \frac{c^2}{4}=\left( \frac{c}{2} \right)^2
$$


**Lezione Associata:** [[6.Catene di Markov discrete]]