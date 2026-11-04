
Oggi ci occupiamo della definizione intrinseca di spazio tangente e differenziale su varietà differenziabili.

Ricordiamo che la definizione estrinseca di $T_{p}S$ per superfici in $\mathbb{R}^3$ è quella di immagine del differenziale della parametrizzazione della superficie, e avevamo detto che ogni vettore appartenenete a $T_{p}S$ era associato biunivocamente alla velocità di una qualche curva in $S$.

L'idea della definizioni intrinseca di oggi è quella che un $v\in T_{p}M$ serve a derivare una funzione
$f:M\to \mathbb{R}$, con $M$ varietà differenziabile.

Partiamo da un **osservazione**: se $f=g$ vicino a un punto $p$, ossia $\exists U_{p}: \, f|_{U_{p}}=g|_{U_{p}}$, allora ci aspettiamo che le derivate coincidano. Cioè nella derivata non ci interessa il dettaglio di $f$ ma solo quello che $f$ fa vicino a $p$.

Questa idea ci porta alla prima definizione:

**Def:** 2 funzioni sono equivalenti ($f\sim_{p}g$) se $\exists U_{p}: f|_{U_{p}}=g|_{U_{p}}$.
Definiamo una classe di funzioni equivalenti ad $f$ in $p$:
$$
	[f]_{p} =\{ g:\, g\sim f \}
$$
che chiamiamo "germe" di $f$ in $p$.

In virtù del fatto che funzioni appartenenti al germe di $f$ hanno derivate coincidenti, a noi interessa soltanto lo studio di $[f]_{p}$ quando ci occupiamo di $T_{p}M$.

Dunque ci interessa andare a studiare l'insieme dei germi, così definito:
$$
	C_{p}^\infty=\{ \text{germi in } p \}= \{ [f]_{p} \}
$$
Questo insieme ha proprietà algebriche interessanti:
- $[f_{1}]_{p}+[f_{2}]_{p}:=[f_{1}+f_{2}]_{p}$
  è una buona definizione, nel senso che se $g_{1} \sim f_{1}\implies[g_{1}]+[f_{1}]=[f_{1}]+[f_{2}]$
- $\lambda[f]_{p}:=[\lambda f]_{p}$
- $[f_{1}]_{p} \cdot [f_{2}]_{p}:= [f_{1}f_{2}]_{p}$.
Queste ultime 2 proprietà sono ben definite nel senso precedente.

Dunque $C_{p}^\infty$ è un'algebra (spazio vettoriale dotato di operazioni extra che sodisfano tutte le proprietà necessarie).

In conclusione, vogliamo derivare $[f]_{p}$.

Come si deriva un germe?

**Def:** Una Derivazione (nel senso di "derivata sui germi") è un operazione $D:C_{p}^\infty\to \mathbb{R}$. Vogliamo che tale operazione sia lineare rispetto alla somma e alla moltiplicazione per scalare ($+, \lambda\cdot$).
Ulteriormente, vogliamo che esista una regola tipo Leibniz all'applicazione della derivata:
$$
	D([f]\cdot[g])\underset{\text{Leibniz}}{=}f(p)\cdot D([g]_{p})+g(p)\cdot D([f]_{p})
$$
**Oss:** L'insieme degli omomorfismi: $Hom(C^\infty_{p},\mathbb{R})$, sia $C^\infty_{p}$ ha dimensione $\infty$. Dunque l'insieme degli omomorfismi ha dimensione infinita. Posso dire lo stesso per lo spazio delle derivazioni?

L'ipotesi di leibniz è sufficientemente forte da ridurne le dimensioni. Di quanto ci viene detto dal teorema delle derivazioni.

**Teorema delle derivazioni:** Presa una varietà $M$ con $\text{dim}M=n, \, p\in M$.
1. L'insieme delle derivazioni è uno spazio vettoriale di $\text{dim}=n$

Esiste un ulteriore punto al teorema, prima di enunciarlo, acquisiamone un'idea intuitiva tramite un esempio.
Considero $M,\,p\in M$. Sia $f:M\to \mathbb{R}$. Prendiamo una curva $\alpha$ su $M$, passante in $p$; $\alpha(0)=p$.
Possiamo definire una derivazione "vecchio stile" per composizione con $\alpha$:
$$
	D_{\alpha}([f]_{p}):=\frac{d}{dt}(f \circ\alpha)(t)|_{t=0}
$$
è ben definita perchè non vede la differenza tra rappresentazioni diverse e soddisfa tutte le proprietà di una derivazione.
Chiamiamo derivazioni di questo tipo derivazioni geometriche perchè costruite con l'ausilio di oggetti geometrici, come le curve.

2. Ogni derivazione è geometrica, ossia $\forall D \quad \exists \alpha \; (\text{curva}): \, D=D_{\alpha}$

Dunque possiamo definire $T_{p}M=\text{insieme delle derivate direzionali nel punto }p \text{ (al valore di } f \text{)}$.

Non dimostreremo il teorema, tuttavia è utile approfondire alcuni ingredienti della dimostrazione:

- Preso $V$ spazio vettoriale, posso definire $V^*=Hom(V,\mathbb{R})$, insieme delle applicazioni lineari da $V\to \mathbb{R}$. Questa è la nozione di spazio (vettoriale) duale.
**Oss:** supponiamo $\text{dim}(V)=n$, $B=\{ v_{1},v_{2},\dots v_{n} \}$. Partendo da $B$ è possibile costruire una una "base duale" $v_{1}^*,\dots, v_{n}^*$ tale che $v_{i}^*(v_{j})=\delta_{ij}$.
Questa è una base di $V^*$, pertanto:
1. dim$V^*=n$ 
2. Usando $B$ ottengo un isomorfismo $V\to V^*$ che manda $v_{i}\to v_{i}^*$.
   Da questo sembra che $V$ e $V^*$ siano identificabili. Però è un'identificazione molto debole che dipende dalla scelta della base. $V$ e $V^*$ sono "gemelli eterozigoti", si assomigliano sotto alcuni punti di vista, sono profondamente diversi sotto altri.

Possiamo trovare un'identificazione alternativa che sia migliore di questa? Sì, possiamo trovarla sfruttando un prodotto scalare su $V$.
Prendiamo $V$ e scegliamo un prodotto scalare $\langle , \rangle$ su $V$:
$$
	v\to \langle v, \cdot \rangle \in V^*
$$
Iniettiva perchè non degenere. Ricordiamo da Gal 1 che ogni applicazione lineare tra spazi con la stessa dimensione è un isomorfismo, dunque possiamo identificare $V$ e $V^*$. Parliamo di "isomorfismo musicale".

**Esempio:** $f:\mathbb{R}^3\to \mathbb{R}$
$$
	\nabla f=\begin{pmatrix}
	\frac{ \partial f }{ \partial x }  \\
	\frac{ \partial f }{ \partial y }  \\
	\frac{ \partial f }{ \partial z } 
	\end{pmatrix} \in \mathbb{R}^3 \underbrace{\longrightarrow}_{\text{definisco l'isomorfismo musicale}} df(v)= \langle \nabla f ,v\rangle = \frac{ \partial f }{ \partial v }  
$$
Ma ha lo stesso problema dell'altra rappresentazione, dipende da una scelta, in questo caso una scelta di prodotto scalare.

**Oss:** se $M:=M^{B,\tilde{B}}$ in $V$, allora $M^{B^*, \tilde{B}^*}= \,^tM^{-1}$

Perchè ci interessa $V^*$? Ci interessa perchè $T_{p}M=\{ \text{der} \}\leq Hom(C_{p}^\infty,\mathbb{R})=(C_{p}^\infty)^*$

Quello che faremo ora è giocare con gli spazi duali.

- Iniziamo dualizzando lo spazio duale:
**Oss:** $V^{* *}=\{ V^*\to \mathbb{R} \}$ spazio biduale. In teoria potrei procedere in maniera iterativa ma fortunatamente non ci serve. In molti casi $V^{**}$ è gemello omozigota di $V$, cioè c'è un'identificazione canonica.

**Esempio:** dim$V=n$. Considero una mappa da $V\to V^{* *}$.
che manda vettori $v$ in un elemento di $V^{* *}$, che devo costruire.
Un elemento di $V^{* *}$ è un'applicazione lineare:
$$
	\begin{aligned}
	V^*&\to \mathbb{R} \\
	\alpha\in V^* &\to \alpha(v) \in \mathbb{R}
	\end{aligned}
$$
Si dimostra facilmente che un'applicazione lineare così definita è tale da generare una mappa iniettiva tra $V$ e il proprio biduale $V^{* *}$, poichè i 2 spazi hanno la stessa dimensione, si ha che questa mappa è un isomorfismo e $V\simeq V^{* *}$.
Dunque posso vedere $V$ come lo spazio delle applicazioni da $V^*\to \mathbb{R}$.

**Esempio:** $V$ è uno spazio di Hilbert.
Per spazi di Hilbert abbiamo già scelto un prodotto scalrem dunque possiamo dire $V \simeq V^*$ e di conseguenza $V \simeq V^{* *}$.

- la seconda cosa che possiamo fare è dualizzare le applicazioni lineari

### Dualità e applicazioni lineari

consideriamo una qualunque applicazione lineare:
$$
	f:V\to W
$$
Possiamo dualizzare $f$?
Sì, e il duale va in direzione opposta (ed è sempre un'applicazione lineare):
$$
	f^*:W^*\to V^*
$$
Come costruisco questo duale? Si tratta di un'applicazione che opera nel seguente modo:
$$
	\alpha \in W^* \to f^*(\alpha):=\alpha \circ f
$$
Dove $\alpha$ è un elemento di $W^*$, cioè un'applicazione lineare da $W\to \mathbb{R}$.

L'abbiamo già vista in Gal 1, si tratta dell'applicazione trasposta.

Recap Gal 1:
$$
	\begin{aligned}
	f: &V\qquad \longrightarrow &&W \\
	&\langle , \rangle _{V} &&\langle , \rangle _{W}
	\end{aligned}
$$
Allora, l'applicazione trasposta è:
$$
	^tf: W \quad \longrightarrow  \quad V
$$
tale che $\langle f(v),w \rangle_{W}=\langle v,\,^tf(w) \rangle_{V}$. Nel caso di endomorfismi ($W=V$) questo si riconduce al caso di applicazioni diagonalizzabili

Scelto un prodotto scalare possiamo identificare $W=W^*$, $V=V^*$ e $f^*$ con $^tf$.

Ma, a differenza della trasposta, $f^*$ non necessità di un prodotto scalare, dunque è più vesatile. Il motivo è analogo a quello per cui il differenziale è meglio del gradiente.

Torniamo al nostro studio delle varietà differenziabili:
Considero $F: M_{1}\to M_{2}$. Questa genera una mappa tra i germi, la mappa duale (devo quindi invertire $M_{2}$ e $M_{1}$):
$$
	F^*: C^\infty_{F(p)}\overset{F^*}{\to} C_{p}^\infty, \quad F^*[f]:=[f \circ F]
$$
detta pull-back, che manda $[f]_{F(p)}\to[f \circ F]_{p}$. Si tratta di una mappa lineare tra spazi vettoriali.
La sua mappa duale, genericamente indicata con $F_{*}$ è:
$$
	F_{*}:(C_{p}^\infty)^*\to(C_{F(p)})^*
$$
Questa mappa è diversa da $F$ perchè sto lavorando sul duale dei germi e non di  tutto lo spazio duale $M_{i}^*$, dunque si tratta del "duale di una restrizione del duale di $F$".
Ricordando che le derivazioni sono applicazioni lineari sui germi, quindi $F_{*}$ opera anche sulle derivazioni.
A questo punto è lecito chiedersi:
$F_{*}$ manda derivazioni in derivazioni?
Sì, per mostrarlo consideriamo $D \in T_{p}M$. Chiediamoci se $F_{*}(D)\in (C_{F(p)}^\infty)^*$ sia una derivazione.
- $F_{*}(D)$ è lineare per dualizzazione
- Verifico leibniz. Considero due funzioni $g,f:M_{2}\to \mathbb{R}$
$$
	\begin{aligned}
	F_{*}(D)([f]\cdot [g])&=F_{*}(D)([fg])\underset{\text{dualità}}{=}D(F^* [fg])=D([(fg)\circ F]) \\
	&=D[(f \circ F) \cdot (g \circ F)] \underset{\text{leibniz}}{=} (f\circ F)D[g \circ F]+(g\circ F)D[f \circ F]\\
	&=f|_{F(p)} D(F^* ([g]))+g|_{F(p)} D(F^*[f])=f|_{F(p)} F_{*}D[g]+g|_{F(p)}F_{*}D[f]
	\end{aligned}
$$
La restrizione di $F_{*}$ agli spazi tangenti è la definizione di differenziale:
$$
	dF = F_{*}|_{T_{p}M}
$$
Cioè il differenziale di $F$ è una mappa tra gli spazi tangenti (come per le superfici):
$$
	dF: T_{p}S_{1}\to T_{F(p)}S_{2}
$$
Siamo riusciti però a creare una nozione di calcolo della derivata che è intrinseco.









