---
corso: Teoria dei campi classica
data: 2026-09-01
tags:
  - lezione
argomenti:
  - Campi_classici
lezione-precedente: "[[Quantità conservate in teorie di campo]]"
source:
---


> [!info] Contesto
> Corso: Teoria dei campi classici
> Argomenti previsti: Teoria dei gruppi, basi di algebre di lie, teorie di gauge U(1) (elettrodinamica)

## Riassunto veloce

Per prima cosa sono state introdotte le nozioni di gruppo, algebra di lie e generatori. Succeccivamente abbiamo studiato come, imponendo la conservazione di una lagrangiana scalare complessa sotto trasformazioni locali appartenenti ad un gruppo particolare U(1) emergano i concetti di campo di gauge e derivata covariante, come da questi esca la lagrangiana che descrive la dinamica del fotone e dell'elettromagnetismo di Maxwell. Viene anche fatto un accenno dell'interpretazione geometrica. Non abbiamo ancora esteso i concetti allo studio di trasformazioni appartenenti a gruppi non abeliani.

## Appunti

### Basi di Teoria dei gruppi e algebre di Lie

Per poter parlare adeguatamente di simmetrie e teorie di gauge bisogna prima introdurre alcuni concetti provenienti dalla teoria dei gruppi, insieme a qualcosina di algebre di Lie.

>[!abstract] Definizione di Gruppo
>Un **gruppo** è un insieme $G$ a cui è associata una mappa da $G \times G$ in $G$ (denotata come $g_{1}*g_{2}$) con le seguenti proprietà:
> 
> - Associatività: per ogni $g_{1},\,g_{2} \in G$, 
> $$
> g_{1}*(g_{2}*g_{3})=(g_{1}*g_{2})*g_{3}
> $$
> - Esiste un elemento identità $e \in G$ tale che per ogni $g \in G$, 
> $$
>	g*e=e*g=g
> $$
> - Esiste un elemento inverso $h \in G$ tale che per ogni $g \in G$:
> $$
>	g*h=h*g=e
> $$
> Ulteriormente se il gruppo è anche commutativo, si dice abeliano

L'elemento identità e l'elemnto inverso sono unici.
La mappa da $G \times G \rightarrow G$ è detta operazione prodotto del gruppo.
Alcuni esempi di gruppi sono:
- Il gruppo triviale, dotato di un unico elemento $e$ e la cui operazione è definita come $e e=e$
- Numeri interi con l'addizione, numeri reali con l'addizione, $\mathbb{R}^n$ con la somma vettoriale
- Il gruppo delle matrici invertibili. Preso un qualunque intero $n$, l'insieme delle matrici quadrate invertibili di rango $n$ formano un gruppo rispetto alla moltiplicazione tra matrici. Il gruppo è non abeliano per $n\geq 2$. Questo gruppo prende il nome di **gruppo lineare generale** (sui reali) ed è denotato con $GL(n;\mathbb{R})$ e lo rivedremo meglio in seguito.
Un sottoinsieme $H$ di $G$ che risulti a sua volta chiuso rispetto al prodotto di $G$ e sia dotato di inversa ed identità viene detto un sottogruppo di $G$.

#### Gruppi di Matrici di Lie

Partiamo da $GL(n;\mathbb{R})$ e definiamo $GL(n;\mathbb{C})$ come il gruppo delle matrici invertibili ad entrate complesse. Ovviamente il gruppo lineare sui numeri reali è contenuto in quello definito sui numeri complessi.

Consideriamo una sequenza di matrici complesse $A_{n}$. Diciamo che $A_{n}$ **converge** ad A se ogni entrata di $A_{n}$ converge alla corrispondente entrata di $A$. (Per n che tende a infinito).

>[!abstract] Definizione di Gruppo di Matrici di Lie
>Un **Gruppo di Matrici di Lie** è un qualsiasi sottogruppo $H$ di $GL(n,\mathbb{C})$ che soddisfi la seguente proprietà: se $A_{n}$ è una sequenza di matrici qualunque di $H$ e $A_{n}$ converge a una qualche matrice $A$, allora ho soltanto 2 possibilità, o $A\in H$ o $A$ non è invertibile (dunque non fa parte di $GL$).

Esempi:
- Il gruppo lineare generale (sia sui complessi che sui reali). Perchè $GL(n;\mathbb{C})$ è un sottogruppo di se stesso e una sequenza di matrici a entrate tutte reali sarà sempre una matrice a entrate reali e farà dunque parte di $GL(n;\mathbb{R})$.
- Il **gruppo lineare speciale** $SL(n;\mathbb{R})$ e $SL(n;\mathbb{C})$, cioè le matrici invertibili con determinante pari a uno. Infatti una sequenza di matrici con determinante uno convergera sempre a una matrice con determinante uno. 
- il **gruppo ortogonale e ortogonale speciale** $O(n)$ e $SO(n)$, cioè le matrici reali invertibili e ortogonali. (SO sono le matrici ortogonali di determinante 1 mentre O ammette matrici di determinante -1). Una definizione alternativa di ortogonalità rispetto a quella a noi nota è quella di conservazione del prodotto interno (o prodotto scalare) quando applicate a 2 vettori, abbiamo visto perchè in relatività.
- il **gruppo unitario e unitario speciale** $U(n)$ e $SU(n)$. Una matrice **unitaria** è una matrice $n \times n$ a entrate complesse che conserva il prodotto scalare. Questo si traduce nella condizione che $A^{\dagger} A = I$ , dove $A^{\dagger}$ indica la matrice trasposta coniugata (cioè la matrice aggiunta hermitiana). Sequenze di matrici unitarie convergono a matrici unitarie, inoltre matrici unitarie sono invertibili per definizione, dunque formano un gruppo di matrici di Lie. Il gruppo delle matrici unitarie con determinante uno è il gruppo unitario speciale. In generale matrici unitarie hanno determinante pari a $e^{ i\theta }$ per un $\theta$ qualsiasi.

>[!abstract] Definizione di Gruppo di Lie
>Un **gruppo di Lie** è una varietà differenziabile G che è anche un gruppo, ed è inoltre tale che il prodotto del gruppo 
>$$
>	G \times G \to G
>$$
>e la mappa inversa $g \to g^{-1}$ siano entrambe differenziabili

si può dimostrare che ogni gruppi di matrici di Lie è anche un gruppo di Lie

#### Esponenziale di matrici

L'esponenziale di una matrice gioca un ruolo cruciale nella teoria dei gruppi di Lie in quanto entra nella definizione dell'algebra di Lie di un gruppi di Lie ed è il meccanismo che  permette lo scambio di informazioni da un'algebra di Lie a un gruppo di Lie.
Sia $X$ una matrice $n \times n$ reale o complessa, vogliamo definire l'esponenziale di $X$ o $e^X$ per sviluppo in serie, come si fa per i numeri reali e complessi.
$$
	e^X = \sum^\infty_{m=0} \frac{X^m}{m!}
$$
Da un punto di vista formale bisognerebbe studiare la convergenza di questa serie, ma temporaneamente buttiamo un po' di polvere sotto al tappeto ed elenchiamo alcune proprietà degli esponenziali di matrici.
Siano $X$ e $Y$ matrici $n \times n$ arbitrarie, allora:
1. $e^0 =I$
2. $e^X$ è invertibile (la matrice risultante, non l'operazione!) e $(e^X)^{-1}=e^{ -X }$
3. $e^{ (\alpha + \beta) X}=e^{ \alpha X }e^{ \beta X }$
4. Se $XY=YX$ allora $e^{ X+Y }=e^{ X }e^{ Y }=e^{ Y }e^{ X }$
5. Se $C$ è invertibile, allora $e^{ CXC^{-1} }=Ce^{ X }C^{-1}$
6. $||e^X|| \leq e^{||X||}$
7. $\det(e^X)=e^{Tr(X)}$ dove con $Tr$ si intende la traccia della matrice

Il modo più semplice per calcolare una matrice è sfruttare la proprietà (5) nel caso di matrici diagonalizzabili. Infatti se $X$ è una matrice diagonalizzabile $X=CDC^{-1}$ allora:
$$
	e^X = Ce^DC^{-1}
$$
e l'esponenziale di una matrice diagonale non è altro che la matrice diagonale che ha ad ogni entrate l'esponenziale dell'entrata corrispondente. In questo caso avrò lungo la diagonale le entrate $e^{\lambda_{1}}, e^{\lambda_{2}}, \dots$ dove $\lambda_{1}, \lambda_{2}, \dots$ sono gli autovalori di $X$.
L'operazione inversa è il logaritmo di matrice ma non è necessario al momento.

#### Algebre di Lie

Prima di introdurre finalmente le algebre di Lie, diamo ancora due definizioni essenziali.

Una funzione $A:\mathbb{R}\to GL(n;\mathbb{C})$ è chiamata **Gruppo a un parametro** se:
1. $A$ è continua
2. $A(0)=I$
3. $A(t+s)=A(t)A(s)$ per ogni $t,s \in \mathbb{R}$

Se $A$ è un gruppo a un parametro in $GL(n;\mathbb{C})$, allora esiste una matrice $X$ complessa $n \times n$ unica, tale che:
$$
	A(t)=e^{itX}
$$

$X$ prende il nome di **generatore**/base del gruppo. Si possono definire anche gruppi a più parametri che avranno ovviamente più generatori. (Quella riportata è la convenzione fisica, quella matematica è $A(t)=e^{tX}$).

>[!abstract] Definizione di Algebra di Lie
>Sia $G$ un gruppo di Lie. Allora un'**Algebra di Lie** di $G$, denotata con $\mathfrak{g}$, è l'insieme di tutte le matrici $X$ tali che $e^{itX} \in G$ per ogni numero reale $t$.

Come ultima cosa andiamo a definire il **commutatore**.
Date due matrici $n \times n$ $A$ e $B$, il commutatore di $A$ e $B$ è definito come:
$$
	[A,B]=AB-BA
$$
L'algebra di Lie di un qualunque gruppo di Lie è chiuso rispetto al commutatore.


### Simmetrie interne globali e locali

Le teorie di campo rilevanti in natura sembrano coinvolgere sempre campi che possono essere raggruppati in vettori che si trasformano in una maniera definita sotto l'azione di alcuni gruppi di simmetria. Queste simmetrie saranno poi le simmetrie della lagrangiana.
Un esempio tipico è quello dove le componenti del campo si traformano in accordo col gruppo unitario $U(N)$.  Gli elemnti $g$ di tale gruppo ricordiamo essere tutte le matrici $N \times N$ tali che $U^{-1}=U^{\dagger}$. L'azione di questo gruppo su un vettore complesso $\phi$ con $N-$componenti sarà:
$$
	\phi^a\to U(g)^{ab}\phi^b
$$
Dove abbiamo sommato sugli indici ripetuti.
Le matrici unitarie sono inoltre quelle che lasciano invariato il prodotto scalare definito nel seguente modo:
$$
\phi ^{\dagger} \psi \equiv (\phi^a)^*\psi^a
$$
Pertanto, un'azione invariante sotto l'azione del gruppo unitario potrebbe essere quella scritta partendo da una lagrangiana (scritta nello spazio-tempo di Minkowski) del tipo:
$$
	\mathcal{L}(\phi)=-\partial_{\mu}\phi ^{\dagger}\partial^\mu \phi-V(\phi ^{\dagger}\phi)
$$
Un altro esempio di gruppo di simmetria interno è quello delle matrici ortogonali $O(N)$ che lascia invariato il prodotto scalare definito nel seguente modo:
$$
	\phi^t \psi \equiv \phi^a \psi^a
$$
In questo caso una lagrangiana invariante è una lagrangiana del tipo:
$$
	\mathcal{L}(\phi)=-\frac{1}{2}\partial_{\mu}\phi^t\partial^\mu \phi-V(\phi^t\phi)
$$
per $O(1)$ il campo $\phi$ è un normalissimo campo scalare. Per il gruppo abeliano $O(2)$ che descrive le rotazioni rigide e le riflessioni del piano il campo da considerare è un vettore reale a 2 componenti. Le rotazioni e basta sono descritte dal gruppo $SO(2)$.
Possiamo osservare che $SO(2)=U(1)$ perchè $U(1)$ agisce allo stesso modo sui numeri complessi $\phi=\phi_{1}+i\phi_{2}$ quando lo scriviamo come un vettore con 2 componenti.
Per $U(1)$ gli elementi del gruppo $g$ sono solo fattori di fase che agiscono su $\phi$:
$$
	\phi\to U(g)\phi=e^{i \alpha(g)}\phi
$$
(che sono proprio le rotazioni).

I gruppi $U(N)$ e $O(N)$ di dimensione più grande sono tutti non abeliani.
Anche per i gruppi non abeliani possiamo descrivere l'azione che questi hanno sui campi, andando ad introdurre l'algebra di Lie del gruppo.

Consideriamo ad esempio il gruppo $U(N)$. Per ogni matrice Hermitiana  $H$, di dimensione $N \times N$, abbiamo che $U=e^{iH}$ è una matrice unitaria. Dunque lo spazio delle matrici Hermitiane forma l'algebra di Lie del gruppo $U(N)$.
Poichè è uno spazio vettoriale (di dimensione $N^2$), possiamo scegliere una base $T^a$ e scrivere:
$$
	H=\alpha^a(H)T^a
$$
dove i numeri reali $\alpha^a(H)$ sono le "coordinate" di $H$ nella base $T^a$.
Con questa notazione, l'azione dell'elemento del gruppo $g$ su $\phi$ diventa:
$$
	\phi \to e^{i\alpha^a(H)T^a}\phi
$$
Che è per molti aspetti simile a quello che abbiamo trovato per $U(1)$.
Una proprietà dei vettori della base è che soddisfano la relazione:
$$
	[T^a,T^b]=ic^{abc}T^c
$$
le $T^a$ sono definite generatori dell'algebra di li e le costanti $c^{abc}$ sono definite costanti di struttura.
I generatori possono sempre essere scelti "ortonormali" tra di loro:
$$
	Tr(T^a T^b) \equiv T^a_{\alpha \beta}T^b_{\beta \alpha}=\delta^{ab}
$$
L'algebra di Lie del gruppo $O(N)$ è lo spazio di tutte le matrici antisimmetriche puramente immaginarie.

Ulteriori gruppi di notevole importanza in fisica sono i sottogruppi $SU(N)$ e $SO(N)$, caratterizzati dall'avere determinante 1. I generatori di $SU(N)$ sono lo spazio delle matrici hermitiane con traccia nulla, mentre i generatori di $SO(N)$ sono gli stessi di $O(N)$.
==La differenza precisa tra $U(N)$ e $SU(N)$ ,al di là del determinante, non so quale sia ed è apparentemente parecchio complesso quindi forse lo riprenderò con calma in futuro.==

Tutte le simmetrie appena discusse possono essere rese locali, nel senso che gli elementi del gruppo che entrano in gioco nella trasformazione dipendono dalla posizione spazio temporale del punto $x$:
$$
	\phi(x)\to U(g(x))\phi(x)
$$
Una simmetria di questo tipo è chiamata **simmetria di Gauge locale**.
Il termine $\partial_{\mu}\phi ^{\dagger}\partial^\mu \phi$ non è più invariante sotto trasformazioni di questo tipo. Se vogliamo che la nostra teoria resti invariante sotto queste trasformazioni locali dobbiamo introdurre un nuovo campo, un *campo di gauge*, che compensi i termini delle derivate che agiscono sulla matrice di trasformazione $U(g(x))$.

### Teorie di Gauge Abeliane

Scriviamo una lagrangiana (con un campo scalare) invariante sotto trasformazioni globali del gruppo $U(1)$ (posso immaginare $\phi$ come un campo di materia, tipo un dielettrico):
$$
	\mathcal{L}_{0}(\phi)=-(\partial_{\mu}\phi)^*(\partial^\mu \phi)-V(\phi^*\phi)
$$
Se richiediamo l'invarianza sotto trasformazioni di gauge locali dobbiamo andare ad introdurre un *campo di gauge* $A_{\mu}(x)$ che si trasformi insieme a $\phi(x)$ nel seguente modo:
$$
	\begin{aligned}
	\phi(x)&\to e^{i \alpha(x)}\phi(x) \\
	A_{\mu}(x)&\to A_{\mu}(x)+\partial_{\mu}\alpha(x)
	\end{aligned}
$$
A questo punto, andando ad introdurre la derivata covariante:
$$
	D_{\mu}=\partial_{\mu}-iA_{\mu}
$$
otteniamo che:
$$
	D_{\mu}\phi \to e^{i\alpha(x)}D_{\mu}\phi(x)
$$
cioè la derivata covariante di $\phi$ si tyrasforma in maniera covariante sotto trasformazioni locali del gruppo $U(1)$.
Facciamo i calcoli espliciti:
$$
	D_{\mu}(e^{i \alpha(x)}\phi(x))=e^{i\alpha(x)}\partial_{\mu}\phi(x)-i(A_{\mu}+\partial_{\mu}\{ \alpha(x)\})e^{i\alpha(x)}\phi(x)+i\partial_{\mu}e^{i\alpha(x)}\phi(x)=e^{i\alpha(x)}D_{\mu}\phi(x)
$$
Pertanto la lagrangiana scritta con $D_{\mu}$ anzichè $\partial_{\mu}$ sarà invariante sotto trasformazioni di gauge locali appartenenti al gruppo $U(1)$:
$$
	\mathcal{L}=-(D_{\mu}\phi)^*(D^\mu \phi)-V(\phi^*\phi)
$$
All'interno di questa lagrangiana sul campo di gauge $A_{\mu}$ non agiscederivata del secondo ordine quindi non sto andando a descrivere alcuna dinamica propria del campo $A_{\mu}$.  A questo punto però è interessante andare a scrivere una lagrangiana che descriva la dinamica di questo campo. In assenza di sorgente gli unici termini che vogliamo compaiano sono i termini delle derivate prime al quadrato, inoltre andando ad imporre l'invarianza per trasformazioni di lorentz e per trasformazioni del campo di Gauge definite come sopra, il termine cinetico della lagrangiana va a definirsi univocamente come:
$$
	\mathcal{L}(A_{\mu})=-\frac{1}{4}F_{\mu \nu}F^{\mu \nu},\quad \text{con} \quad F_{\mu \nu}=\partial_{\mu}A_{\nu}-\partial_{\nu}A_{\mu}
$$
Argomentiamo meglio la questione dell'invarianza per trasformazioni di Gauge:
Si osserva facilmente che un termine cinetico del tipo $\partial_{\mu}A_{\nu}\partial^\mu A^\nu$ non sarebbe stato invariantesotto la trasformazione $A_{\mu}\to\partial_{\mu}\alpha$, motivo per cui dobbiamo andare ad introdurre l'antisimmetria tramite il tensore di campo. 
Inoltre non è neanche possibile aggiungere alla lagrangiana un termine potenziale legato alla massa, del tipo $m^2\phi^2$ , in quanto $m^2 A_{\mu}A^\mu$ è anch'esso incompatibile con la trasformazione di gauge. Dunque la particella associata al campo di gauge $A_{\mu}$ è massless.
Particella massless + interazione elettromagnetica ci fanno intuire che la particella in questione non sia altro che il fotone.

Nel caso di elettrodinamica libera, possiamo ignorare l'interazione con $\phi$ e ottenere (con E-L) l'equazione del moto:
$$
	\partial^2A_{\mu}-\partial_{\mu}\partial_{\nu}A_{\nu}=0 \, \Rightarrow \, \partial_{0}(\partial_{i}A_{i})=0 \quad \text{se} \quad A_{0}=0
$$
allora $\partial_{i}A_{i}=cost$ per ogni $t$. Fissando $\partial_{i}A_{i}=0$ a $t=0$ otteniamo che è uguale a 0 per ogni $t$.
Analogamente se $A_{0}=0$ possiamo scrivere:
$$
	\partial^2 A_{i}-\partial_{i}\partial_{0}(0)=0 \, \Rightarrow \, \partial^2A_{i}=0
$$
E alla fine restiamo con:
$$
	\partial^2 A_{i}=0, \quad \partial_{i}A_{i}=0
$$
La prima delle 2 è l'equazione di D'Alembert, la cui soluzione generale è:
$$
	A_{i}=e^{(k_{i}x_{i}-|\omega|t)}e_{i}
$$
La seconda condizione viene soddisfatta nel caso in cui: $k_{i}e_{i}=0$
Questa condizione ci dice che i fotoni si propagano (nel vuoto) solo se oscillano trasversalmente (infatti non esistono onde elettomagnetiche longitudinali).

### Interpretazione geometrica

L'invarianza di Gauge ha molto in comune con l'invarianza sotto cambi di coordinate in relatività generale (vedi dopo aver seguito intro a rel. gen.).
L'invarianza di gauge locale rende inutile $\partial_{\mu}\phi$ come misura della variazione di $\phi$.
Per avere una teoria con derivate che abbiano un significato fisico-matematico, abbiamo bisogno di una regola collegare efficacemente $\phi(x)$ e $\phi(x+dx)$: una connessione $A_{\mu}$ che definisca la traslazione $T$ di $\phi$:
$$
	\begin{aligned}
	x &\to x+dx &&= T_{dx}(x) \\
	\phi(x) &\to T_{dx}(\phi)(x) &&= (1+idx \cdot A(x)+O(dx)^2)\phi(x)\\
	&&&= e^{(idx\cdot A(x))} \phi(x)
	\end{aligned}
$$
Cioè quando $T$ agisce sul campo e non su $x$ va ad indurre anche una rotazione di fase.
Possiamo definire la derivata covariante andando a comparare il valore di $\phi(x+dx)$ a quello "teorico" dato dall'operatore $T_{dx}$
$$
	\begin{aligned}
	dx_{\mu}D_{\mu}\phi &\equiv \phi(x+dx)-T_{dx}\phi(x) \\
	&\simeq(\phi(x)+dx_{\mu}\partial_{\mu}\phi(x))-(\phi(x)+idx_{\mu}A_{\mu}(x)\phi(x))\\
	&=dx_{\mu}(\partial_{\mu}+iA_{\mu})\phi(x)
	\end{aligned}
$$
Concludiamo che $D_{\mu}=\partial_{\mu}-iA_{\mu}$
A questo punto possiamo ricavare le proprietà di trasformazione di $A_{\mu}$ utilizzando l'ipotesi che $T_{dx}\phi(x)$ dev'essere un campo che obbedisce alla trasformazione di gauge in $x+dx$.
Considero $A'$ connessione trasformata. Per definizione $\phi(x)\to e^{i\alpha(x)}\phi(x) \equiv \phi'$ in ogni punto $x$.
Otteniamo così il seguente schema di uguaglianze:
$$
	\begin{aligned}
	T_{dx}\phi'(x) &\equiv(1+idx\cdot A'(x))\phi'(x) &&=(1+idx\cdot A'(x))e^{i\alpha(x)}\phi(x)\\
	= e^{i\alpha(x+dx)}T_{dx}\phi(x) &= e^{i\alpha(x+dx)}(1+idx \cdot A(x))\phi(x) &&\simeq e^{i\alpha(x)}(1+idx(\partial \alpha(x)+A(x)))\phi(x)
	\end{aligned}
$$

Concludiamo dunque che $A'_{\mu}(x)=A_{\mu}(x)+\partial_{\mu}\alpha(x)$
Nell'ultima uguaglianza il processo è stato: $e^{i\alpha(x+dx)}\simeq e^{i(\alpha(x)+\partial \alpha(x)dx)}\simeq e^{i\alpha x}i\partial \alpha(x)dx$
Quando avrai delle basi di relatività vedi come $F_{\mu \nu}$ è la curvatura di uno spazio (fibrato) e vedi meglio i legami con la relatività generale.



## Domande aperte / cose da rivedere
- [ ] Cos'è il gruppo unitario?
- [ ] Cos'è l'algebra di lie di un gruppo?
- [ ] Come emerge il gauge imponendo la conservazione locale sotto trasformazioni del gruppo U(1)?

## Collegamenti
- Lezione precedente: [[Quantità conservate in teorie di campo]]
- Concetti collegati: [[Quantità conservate in teorie di campo]] 

