---
corso: GAL 2
data: 2026-10-01
tags:
  - lezione
argomenti:
  - Geometria differenziale
lezione-precedente: "[[Curve nello spazio]]"
source:
---


> [!info] Contesto
> Corso: GAL 2
> Argomenti previsti: Superfici immerse in $\mathbb{R}^3$ in tutte le salse

## Riassunto veloce



## Appunti

### Superfici nello spazio

Ripercorriamo quanto fatto per le curve ma con le superfici.

>[!Abstract] Def: Superficie parametrizzata
>Chiamiamo superficie parametrizzata un funzione: 
>$$
>	\varphi: \underset{(u,v)}{U} \subseteq \mathbb{R}^2\to \mathbb{R}^3 \quad \varphi(u,v)=(x(u,v),y(u,v),z(u,v))
>$$
>tale che:
>1. $\varphi\in C^\infty$
>2. $d\varphi$ deve avere rango $2$ in ogni punto (per evitare punte come quelle delle castagne o spigoli retti come quelli di un cubo)
>3. $\varphi:U\to \mathrm{Im}(\varphi)$ è un omeomorfismo, per evitare superfici che si autointersecano o 6 "più spessi", come quelli in figura:
>![[Pasted image 20261001223605.png]]

Interpretiamo meglio cosa implica la condizione $(2)$ da un punto di vista geometrico studiando meglio la natura del differenziale $d\varphi$. Presa $\varphi$:
$$
	\varphi:\underset{(\bar{u},\bar{v})\in U}{U}\to \mathbb{R}^3
$$
L'operazione:
$$
\begin{aligned}
d\varphi|_{\bar{u},\bar{v}}(a)&=\text{ derivata direzionale di }\varphi \text{ in direzione di a}\\
&=\frac{d}{dt}(\varphi \circ \alpha)(t)|_{t=0} \quad \text{con } \alpha=a+tv:I\subseteq \mathbb{R}\to U\subseteq \mathbb{R}^2
\end{aligned}
$$
è un'operazione lineare rispetto alla direzione $a$, pertanto posso rappresentarla tramite una matrice.
Questa linearità diventa evidente con un semplice esempio:
Consideriamo:
$$
	f:U\to \mathbb{R}
$$
la derivata direzionale di $f$ sarà:
$$
	df(a)=\frac{ \partial f }{ \partial x } \cdot a^1 +\frac{ \partial f }{ \partial y }\cdot a^2=\nabla f\cdot a 
$$
Il prodotto scalare è bilineare, dunque l'operatore $df(a)$ sarà lineare.

Tornando al discorso della rappresentazione in forma matriciale, scelte come basi le basi canoniche $d\varphi$ sarà isomorfo ($\simeq$) a una matrice $3\times 2$ e questa matrice saà proprio il Jacobiano di $\varphi$.
$$
J(\varphi)=	\begin{pmatrix}
	\frac{ \partial \varphi^1 }{ \partial u }  & \frac{ \partial \varphi^1 }{ \partial v } \\
	\frac{ \partial \varphi^2 }{ \partial u } & \frac{ \partial \varphi^2 }{ \partial v } \\
	\frac{ \partial \varphi^3 }{ \partial u } & \frac{ \partial \varphi^3 }{ \partial v }  
	\end{pmatrix}
$$
ogni colonna di questa matrice non è altro che $d\varphi(e_{1}=\partial u)$ (o $\partial v$), cioè la derivata direzionale di $\varphi$ lungo la direzione di $u$ e $v$.

La definizione ci dice che $\varphi$ deve avere rango 2 cioè la matrice che lo rappresenta deve avere rango 2. 
Questo si verifica qualora 2 colonne siano linearmente indipendenti o $d\varphi$ contenga una **sottomatrice $2\times {2}$ invertibile**. All'atto pratico questo si traduce nella condizione che le derivate direzionali di $\varphi$ lungo le direzioni di $u$ e $v$ non siano uguali, cioè che la superficie non vada a collassare su di una stessa curva, generando spigoli o punte. (E che la superficie resti quindi localmente paragonabile a $\mathbb{R}^2$).

![[Pasted image 20261001225620.png]]

>[!Abstract] Def: Superficie parametrizzabile
>in totale analogia con le curve, una superficie parametrizzabile è l'immagine $S=\varphi(U)$ di una superficie parametrizzata

>[!Abstract] Def: cambio di coordinate
>Continuando con le analogie con le curve andiamo a definire una riparametrizzzione (o cambio di coordinate) come una mappa: 
>$$
>	\underset{(\xi,\eta)}{\tilde{U}}\subseteq \mathbb{R}^2 \to \underset{(u,v)}{U}\subseteq \mathbb{R}^2
>$$
>$u=u(\xi,\eta)$, $v=v(\xi,\eta)$.
>Questa mappa dev'essere un diffeomorfismo, cioè $C^\infty$ con inversa $C^\infty$

Sotto queste condizioni:
$$
	\tilde{\varphi}(\xi,\eta):=(\varphi\circ(u,v))(\xi,\eta):\tilde{U}\to \mathbb{R}^3
$$
avrà la stessa immagine di $\varphi(u,v)$. Cioè sarà cambiata solo la rappresentazione in coordinate.

**Esempi di superfici:**
___
$\forall f:\mathbb{R}^2\to\mathbb{R}$, $f\in C^\infty$ posso costruire una superficie di questo tipo:
$$
	\varphi(u,v):=(u,v,f(u,v))
$$
la cui immagine sarà semplicemente il grafico di $f$ in $\mathbb{R}^2$.
Verifichiamo la condizione $(2)$, cioè $d\varphi$ di rango $2$.
$$
	d\varphi \simeq \begin{pmatrix}
	1 & 0 \\
	0 & 1 \\
	\frac{ \partial f }{ \partial u } & \frac{ \partial f }{ \partial v }  
	\end{pmatrix}
$$
è evidente la presenza di una sottomatrice $2\times 2$ invertibile (l'identità).
Ovviamente non è necessario che $f(u,v)$ occupi la posizione delle $z$, potrebbe occupare le $x \text{ o le }y$ e non cambierebbe nulla, avrei solo una superficie ruotata.

**OSS:** ogni superficie parametrizzatra è localmente di questo tipo.

**Dim:** 
Sia $\varphi(u,v)=(x(u,v),y(u,v),z(u,v))$.
utilizzo la condizione $(3)$ (quella sull'omeomorfismo).
Dunque scelto $p\in S\underset{\varphi}{\leftrightarrow}(\bar{u},\bar{v})\in U$ , cioè ogni punto della superficie è omeomorfo a un punto del piano. Ulteriormente, sappiamo che $d\varphi|_{\bar{u},\bar{v}}$ contiene una matrice $2\times 2$.
Allora, per il teorema della funzione implicita, la funzione $(u,v)\to(x,y)$ è invertibile (ho scelto $x,y$ ma poteva essere anche $x,z$ o $y,z$). Dunque possiamo riscrivere $u=u(x,y)$ e $v=v(x,y)$.
$$
	\implies \tilde{\varphi}(x,y):=(\varphi\circ (u,v))(x,y)\underset{\text{per costr.}}{=}(x,y,\tilde{z}(x,y))
$$
che è il grafico della funzione $\tilde{z}$. $\blacksquare$

Un altro esempio utile è quello di superfici descritte da vincoli. 
$$
	f:\mathbb{R}^3\to \mathbb{R} \quad f^{-1}(0)\subseteq \mathbb{R}^3 \text{ è una superifice se } \forall\,p\in f^{-1}(0)\; \text{si ha: } \nabla f_{|p} \neq \begin{pmatrix}
	0 \\
	0 \\
	0
	\end{pmatrix}
$$
L'esempio classico è quello della sfera: $f(x,y,z)=x^2+y^2+z^2-1=0$.
L'idea dietro alla dimostrazione è di verificare che vicino a $p$ che soddisfi tali condizioni la controimmagine di $f$ sia sempre il grafico di una qualche funzione $g$, riconducendoci al caso di prima (per una dimostrazione più profonda vedere le dispense). 
Di fatto si tratta del teorema della funzione implicita esteso allo superfici.

### Analisi su superfici

Per poter fare analisi su superfici è necessario andare a definire cosa sia una funzione (differenziabile) definita su una superficie. ($f:S\to \mathbb{R} \; \in C^\infty$)
Prima ancora è necessario porsi il quesito riguardo a come mai non sappiamo definire funzioni differenziabili su delle superfici.
Il problema sta nella definizione stessa di derivata tramite rapporto incrementale.
Proviamo a definire i rapporti incrementali di una funzione su una superficie.

![[Pasted image 20261004234735.png]]


$$
	\frac{ \partial f }{ \partial v }=df_{|p}(v) = \frac{d}{dt} f(p+tv)_{|t=0}= \lim_{ t \to 0 } \frac{f(p+tv)-f(p)}{t} 
$$
il problema in questo caso è che $p+tv \not\in S$ e potrebbe anche darsi che $f$ non sia proprio definita fuori da $S$. Fin'ora abbiamo sempre lavorato con insiemi aperti quindi le funzioni con cui lavoravamo erano sempre definite intorno ai punti sui quali andavamo a derivare. Ora non è più così.

Tornando al primo quesito, per definire una funzione differenziabile su di una superficie abbiamo fondamentalmente 2 strategie tra loro equivalenti (la dimostrazione dell'equivalenza si trova sulle dispense).
1. Analisi estrinseca
2. Analisi intrinseca
Noi in particolare ci occupiamo dell'analisi intrinseca perchè ci permetterà un grado di astrazione maggiore più avanti.

Prima di procedere facciamo un ulteriore osservazione preliminare. Ci interessa in realtà andare a costruire 3 definizioni differenti: funzione dalla superficie a $\mathbb{R}$, curva da $\mathbb{R}$ alla superficie e infine la definizione di funzione definita tra 2 superfici.

- **DEF 1:** $f:S\to \mathbb{R} \in C^\infty \iff f\circ \varphi(u,v):U\subseteq \mathbb{R}^2 \overset{\varphi}{\to}S\overset{f}{\to}\mathbb{R}$ è $C^\infty$.
  $f \circ \varphi$ è una funzione definita su un aperto di $\mathbb{R}^2$ quindi so cosa vuol dire che sia $C^\infty$
  ...MA... devo verificare che sia $C^\infty$ indipendentemente dalla parametrizzazione scelta. Disegnamo le mappe per farci un'idea migliore di ciò che sta succedendo e proviamo a cambiare parametrizzazione.
  $f \circ \tilde{\varphi}=(f \circ \varphi \circ(u,v))(\xi,\eta)$. Questa è la composizione di due funzioni $C^\infty$: $f \circ \varphi$ e $(u,v)(\xi,\eta)$, pertanto è a sua volta $C^\infty$.

![[Pasted image 20261006222658.png|500]]

- **DEF 2:** $\alpha:I\subseteq \mathbb{R}\to S \in C^\infty \iff \varphi^{-1}\circ\alpha:I\to U$ è $C^\infty$.
  Per dimostrare l'invarianza sotto cambi di parametrizzazione procediamo con ragionamenti analoghi a prima

- **DEF 3**: $G:S_{1}\to S_{2} \in C^\infty \iff \psi^{-1} \circ G \circ \varphi: U_{1}\to U_{2}$ è $C^\infty$. Dove $\psi \text{ e } \varphi$ sono parametrizzazioni rispettivamente di $S_{1} \text{ e } S_{2}$.

Sfruttiamo quanto appena detto per studiare $\varphi^{-1}$.

![[Pasted image 20261006232155.png|399]]

Andiamo ad applicare la definizione.
$\varphi^{-1}$ è $C^\infty \iff \varphi^{-1} \circ \varphi$ è $C^\infty$. Ma una funzione composta con la sua inversa mi dà l'identità che è $C^\infty$. Dunque l'inversa di una parametrizzazione è sempre $C^\infty$. Cioè $\varphi$ è un diffeomorfismo.

Queste 3 definizioni abbiamo detto essere definizioni che seguono l'approccio intrinseco, ma cosa significa di preciso? Si tratta di definizioni **intrinseche** perchè sfrutto il più possibile gli oggetti definiti da $S$ e poco il fatto che $S$ vive in $\mathbb{R}^3$. (Impareremo, lavorando con varietà astratte, a non sfruttare proprio $\mathbb{R}^3$).

Questo approccio è più sofisticato rispetto a quello che usiamo quotidianamente, infatti è possibile dimostrare che tutte le funzioni (interessanti) abbiano un'estensione su $\mathbb{R}^3$ e dunque la notazione "classica" di differenziabilità sarebbe stata sufficiente.

A questo punto la domanda con cui è naturale proseguire il discorso è la seguente:

- Appurato cosa sia una funzione differenziabilr, come calcolo le derivate (direzionali)?

Questo equivale a dire: "come calcolo il differenziale"?
Sappiamo che queste devono agire lungo le direzioni tangenti, dunque, in analogia con quanto fatto per le curve, andiamo a definire il piano tangente a $S$, che sarà il supporto della nostra mappa differenziale.
Sfruttiamo temporaneamente l'approccio "estrinseco" per fare uso dell'analisi matematica standard.
Da analisi sappiamo che $d\varphi|_{\bar{u},\bar{v}}:\mathbb{R}^2\to \mathbb{R}^3$ è un'applicazione lineare, dunque le immagini $\mathrm{Im}(d\varphi)$ è un sottospazio del codominio di $\varphi$.

![[Pasted image 20261006233458.png]]

>[!Abstract] **Def:** piano tangente in un punto ($T_{p}S$)
>Il piano tangente a $S$ in $p$ è $\mathrm{Im}(d\varphi)$ per una qualche parametrizzazione $\varphi$ di $S$.
>$dim(\mathrm{Im}(d\varphi))=2$ perchè $d\varphi$ ha rango 2.
>La base di $T_{p}S$ è data da $\frac{ \partial \varphi }{ \partial u }|_{\bar{u},\bar{v}}; \, \frac{ \partial \varphi }{ \partial v }|_{\bar{u},\bar{v}}$

**OSS:** se cambio parametrizzazione cambio il dominio ma il codominio è lo stesso, dunque lo spazio tangente resta invariato e cambio solo la base.
$$
	d\tilde{\varphi}=d(\varphi \circ(u,v))=d \varphi|_{\bar{u},\bar{v}} \circ d(u,v)|_{\bar{\xi},\bar{\eta}}
$$
dove $d\varphi|_{\bar{u},\bar{v}}$ genera la mia immagine, cioè lo spazio tangente e $d(u,v)|_{\bar{\xi},\bar{\eta}}$ rimescola i vettori del dominio.

Come posso caratterizzare i vettori tangenti? Cioè, preso $v\in \mathbb{R}^3$ come faccio a sapere se quel vettore è tangente a $S$?

Per fare ciò esiste la seguente PROPOSIZIONE:
$$
	v\in T_{p}S \iff \exists\, \alpha:(a,b)\to S \quad \alpha(0)=p,\, \dot{\alpha}(0)=v
$$
Cioè $v$ è un vettore tangente a $S$ solo se e solo se è la velocità di una qualche curva parametrizzata su $S$.

- **DIMOSTRAZIONE**:
  $\text{"}\implies \text{"}$ $v\in T_{p}S$, dunque $\exists\, w \in \mathbb{R}^2$ tale che $v=d\varphi|_{\bar{u},\bar{v}}(w)$ (definizione di vettore $\in T_{p}S$)
  ora definisco: 
  $$
	\tilde{\alpha}(t):=(\bar{u},\bar{v})+tw \quad \text{curva in }\mathbb{R}^2
  $$
  trasporto questa curva dal piano $\mathbb{R}^2$ alla superficie:
  $$
	\alpha(t):=\varphi \circ\tilde{\alpha}(t) \to\dot{\alpha}(0)=\frac{d}{dt}(\varphi \circ \tilde{\alpha})|_{t=0} =d\varphi|_{\alpha(0)}(\dot{\tilde{\alpha}}(0))=d\varphi|_{p}(w)=v
  $$
  Dove abbiamo applicato la definizione di derivata direzionale di $\varphi$.
  ![[Pasted image 20261007000222.png]]

  $\text{"} \impliedby \text{"}$ $v=\dot{\alpha}(0) \quad \alpha:I\to S$, cerco il $w$ giusto e verificare che $v=d\varphi(w)$.
  Faccio l'operazione contraria, trasporto la curva dalla superficie al piano:
  $$
	\tilde{\alpha}:=\varphi^{-1} \circ \alpha(t)
  $$
  il vettore $w$ corrispondendte sarà $w=\dot{\tilde{\alpha}}(0)$.
  $$
	d\varphi(w)|_{t=0}=d\varphi|_{\tilde{\alpha}(0)}(\dot{\tilde{\alpha}}(0))=\frac{d}{dt}(\varphi \circ\tilde{\alpha})|_{t=0}=\dot{\alpha}(0)=v
  $$
  $\blacksquare$


## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

