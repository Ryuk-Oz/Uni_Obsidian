
Perchè ci interessano i tensori/prodotti tensoriali? Codificano quasi ogni oggetto utile.
"Convertono operazioni bilineari in operazioni lineari"
**Es:**
il determinante in $\mathbb{R}^2$:
$$
	\det(x,y)=x_{1}y_{2}-x_{2}y_{1}
$$
è un'op. bilineare:
$$
	\mathbb{R} \times \mathbb{R}\overset{\det}{\to} \mathbb{R}
$$
Sappiamo come passare dal prodotto cartesiano al prodotto tensoriale.
$$
	\begin{aligned}
	x\otimes y\in \mathbb{R}\otimes \mathbb{R} &== (x^1 e_{1}+x^2e_{2})\otimes (y^1e_{1}+y^2e_{2})=\\
	&=x^1y^1e_{1}\otimes e_{1}+x^1y^2e_{1}\otimes e_{2}+x^2y^1e_{2}\otimes e_{1}+x^2y^2e_{2}\otimes e_{2}
	\end{aligned}
$$
A questo punto, definisco un'operazione $d$ tale che sulla base:
$$
	\begin{aligned}
	d(e_{1}\otimes e_{1})&=0\\
	d(e_{1}\otimes e_{2})&=1\\
	d(e_{2}\otimes e_{1})&=-1\\
	d(e_{2}\otimes e_{2})&=0
	\end{aligned}
$$
A questo punto, sfruttando la linearità:
$$
	d(x\otimes y) = x^1y^2-x^2y^1=\det(x,y)
$$
Ho definito un analogo lineare del determinante, ma lo spazio di partenza è diverso!

Casi particolari:
$$
	S^r(V)\subseteq \underbrace{V\otimes \dots \otimes V}_{r\text{-volte}}=\{ \text{forme }r \text{-lineari simmetriche } V^*\times\dots \times V^* \}
$$
$$
	\Lambda^r(V) \subseteq V\otimes \dots \otimes V=\{ \text{forme }r\text{-lineari alternanti } V^*\times\dots \times V^* \}
$$
Più spesso lavoriamo con:
$$
	\Lambda^r(V^*)\subseteq V^*\otimes \dots \otimes V^*=\{ r\text{-lineari alternanti } V\times\dots \times V \}
$$
**Esempio**:
$$
	\alpha\in \Lambda^3(V^*)
$$
$\alpha(v_{1},v_{2},v_{3})\in \mathbb{R}=-\alpha(v_{2},v_{1},v_{3})=\alpha(v_{2},v_{3},v_{1})$ etc... (è lineare rispetto ad ogni variabile).
In particolare: $\alpha(v,v,w)=-\alpha(v,v,w)=0$.
Questo fatto serve a dimostrare che $\Lambda^r(V^*)=\{ 0 \}$ per $r>\text{dim}(V)$.

Perchè le forme alternanti sono onnipresenti?
1. Algebricamente: hanno un'operazione interna:
$$
	\begin{aligned}
	\Lambda^r(V^*)\times \Lambda^s(V^*)&\to\Lambda^{r+s}(V^*)\\
	(\alpha,\beta)&\to \alpha \wedge \beta(v_{1}\dots v_{r+s})\\
	&:=\frac{1}{r!} \frac{1}{s!} \sum_{\sigma}(-1)^{|\sigma|}\alpha(v_{\sigma(1)},\dots,v_{\sigma(r)})\beta(v_{\sigma(r+1)},\dots,v_{\sigma(r+s)})
	\end{aligned}
$$
dove $\sum_{\sigma}$ è la somma sulle permutazioni. Si tratta di una definizione simile a quella del determinante.
**Esempio**: $\Lambda^1(\mathbb{R}^{n*})\times \Lambda^1\to \Lambda^2$
$$
	e^*_{i}\wedge e_{j}^*=\frac{1}{1!}\cdot \frac{1}{1!}(e_{i}^*\otimes e^*_{j}-e^*_{j}\otimes e^*_{i})=e_{i}^*\otimes e^*_{j}-e^*_{j}\otimes e^*_{i}
$$
e ho ottenuto una 2-forma alternante.
Generalizzando troviamo: $\Lambda^1 \times\dots \times \Lambda^1\to \Lambda^n$; $e^*_{i}\wedge\dots \wedge e^*_{n}=\det$.

Per il prodotto wedge vale la seguente proprietà:
- $\alpha \wedge \beta=(-1)^{r\cdot s}\beta \wedge \alpha$
Qual è l'utilità del prodotto wedge all'atto pratico?
In primis il calcolo del determinante, che misura il volume di un parallelepipedo $n$-dimensionale.
Il determinante $r$-dimensionale è dunque:
$$
	\Lambda^r (\mathbb{R}^{n*})|_{\text{r-ssp}} (v_{1},\dots v_{r}) \in \mathbb{R}
$$
Cioè una $r$-forma alternante sceglie una unità di misura per volumi su ogni r-ssp.
**Es:** 1-forma su $\mathbb{R}^n$
$\alpha=\alpha_{1}dx^1+\dots+\alpha_{n}dx^n$ mi da un'unità di misura per lunghezza su ogni retta in $\mathbb{R}^n$. Ossia $\alpha(v)=$ lunghezza di $v$ secondo $\alpha$.
Una 2-forma su $\mathbb{R}^n$: $\alpha=\sum \alpha_{ij}dx^i\wedge dx^j_{0}$.
Scelgo un piano $\pi=\mathcal{L}v_{1},v_{2}$ (questo è il mio r-ssp).
$\alpha(v_{1},v_{2})=$ area del parallelogrammo generato da $v_{1},v_{2}$.
$\alpha_{2}(v_{1},v_{2})=2\alpha(v_{1},v_{2})$.
Allora su $M$, le forme differenziali possono essere imtegrate lungo sottovarietà.

### Calcolo tensoriale su varietà

Abbiamo già definito 2 fibrati vettoriali su una generica varietà differenziabile $M$, $TM$ e $T^*M$. Giocando con il prodotto tensoriale possiamo definire un'infinità di nuovi fibrati, ad esempio:
Fibrato vettoriale dei tensori $(r,s)$:
$$
	\underset{p\in M}{\cup} \underbrace{T_{p}M \otimes \dots \otimes T_{p}M}_{\text{r volte}}\otimes \underbrace{T_{p}^*M\otimes \dots \otimes T_{p}^*M }_{\text{s volte}}=T^{r,s}M
$$
$T^{r,s}M$ è una varietà, allora ha senso introdurre la seguente definizione:
>[!Abstract] Tensori su $M$
>Un tensore di tipo $(r,s)$ su $M$ è una mappa $C^\infty$: 
>$M\to T^{r,s}M$ tale che $p\to T_{p}\in T^{r,s}M$

**Esempi**:
Il prodotto scalare/metrica su $M$ è un tensore di tipo $(0,2)$ simmetrico e definito positivo in ogni punto.
Una $r$-forma differenziale su M è un tensore di tipo $(0,r)$ alternante in ogni punto, ossia $p\to \alpha_{p}$ $r$-forma alternante su $T_{p}M$.

Ogni $T_{p}^{r,s}M$ è uno spazio vettoriale (perchè è un prodotto tensoriale), allora possiamo sommare tensori dello stesso tipo un punto alla volta:
presa $f$ funzione $C^\infty$, $T$ tensore, allora:
$$
(fT)_{p}=f(p)T_{p}	
$$
Abbiamo visto la possibilità di fare pushforward di un campo vettoriale $X$ (tensore $(1,0)$) su $\varphi\in \text{Diff}(M)$ e di fare il pullback di una 1-forma $\alpha$ sulla stessa $\varphi$.
Tra pushfoward e pullback c'è una discrepanza rispetto alle composizioni.
$$
	(\varphi \circ \psi)X=\varphi(\psi(X))
$$
preserva l'ordine
$$
	(\varphi \circ \psi)^*\alpha = \alpha(d(\varphi\circ\psi))=\alpha(d\varphi\circ d\psi)=\psi^*\alpha(d\varphi)=\psi^*\varphi^*\alpha
$$
Sul pullback $\varphi$ e $\psi$ sono invertiti.

Possiamo correggere questa discrepanza di $X$ usando un pushforward di $\varphi^{-1}$:
$$
	(\varphi \circ\psi)^{-1}X=(\psi^{-1}\circ \varphi^{-1})X=\psi^{-1}(\varphi^{-1}X)
$$
inverte l'ordine, come succede col pullback.

Usando questa idea, decidiamo di definite il pullback su $\alpha$ come al solito e il pullback su $X$ come pushforward di $\varphi^{-1}$.
A questo punto diventa possibile definire il pullback di $\alpha \otimes X$ come:
$$
	\varphi^*\alpha \otimes \varphi^*X=\varphi^*\alpha \otimes \varphi^{-1}(X)
$$
In questo modo posso definire il pullback di $\varphi$ su tensori di ogni tipo.
Per definizione troviamo quindi:
$$
	(\varphi\circ\psi)^*T=\psi^*(\varphi^*T)
$$
l'ordine è uniformemente scambiato $\forall T$.
Diciamo che $\varphi^*$ è una simmetria che preserva un gerto tensore $g$ se $\varphi^*g=g$.

La definizione consistente di Pullback ci permette di introdurre la derivata di Lie anche per i tensori.
Sia $X$ un campo vettoriale e $\varphi_{t}$ il flusso di diffeomorfismi associato. Preso $T$ tensore, la derivata di Lie di $T$ è definita nel seguente modo:
$$
	\mathcal{L}_{X}T= \frac{d}{dt}\varphi_{t}^{*}T|_{t=0}
$$
cioè:
$$
	\mathcal{L}_{X}T_{p}=\lim_{ t \to 0 } \frac{\varphi^*_{t}T|_{{p}}-\varphi^*_{0}T|_{p}}{t}
$$
derivate dentro a $T_{p}^{r,s}M$.

Come nei casi già noti, $\mathcal{L}_{X}T=0$ significa che $T$ è preservato dal flusso di $X$, ossia che $\varphi_{t}$ sono simmetrie di $T$, cioè $\varphi_{t}^*T\equiv T$.
Ossia $X$ è una simmetria infinitesimale di $T$.

**Esempio:** in meccanica classica i campi Hamiltoniani $X_{f}$ sono simmetrie infinitesime della forma simplettica $\omega$. 
$$\mathcal{L}_{X_{f}}\omega\equiv 0$$

Si dimostra che:
$$
	\mathcal{L}_{X}(T_{1}\otimes T_{2})=\mathcal{L}_{X}T_{1}\otimes T_{2}+T_{1}\otimes \mathcal{L}_{X}T_{2}
$$
Applichiamo quanto detto ad un caso semplice:
$$
	\mathcal{L}_{X}f=\frac{d}{dt}(\varphi_{t}^*f)=\frac{d}{dt}(f\circ\varphi_{t})=df\left( \frac{d}{dt} \varphi_{t} \right)=df(X)
$$
o ancora:
$$
	\mathcal{L}_{X}(\alpha(Y))=(\mathcal{L}_{X}\alpha)(Y)+\alpha(\mathcal{L}_{X}Y)
$$

DOMANDA:
abbiamo davvero definito la "derivata direzionale di un tensore"?
RISPOSTA:
$\mathcal{L}_{X}T$ contiene un "problema" quindi la risposta è NO!

Abbiamo visto che:
$$
	\mathcal{L}_{X}(Y)=-\frac{d}{dt}\varphi_{t}(x)\dots=[X,Y]
$$
Dunque contiene sì derivate di $Y$, ma contiene anche derivate di $X$.

Al contrario la derivata direzionale di una funzione, per come la conosciamo,
$df(X)$, contiene le $X$ ma non le derivate di $X$, $x_{i} \frac{df}{dx^i}$.

Dunque per definire le derivate direzionali di un tensore è necessaria un'idea diversa, quella delle "connessioni".

DEF: una connessione su $TM$ è. un operazione 
$$
\nabla:\{ \text{sezioni di } TM \}\to \{ \text{sezioni di }T^{1,1}M \}
$$
in modo tale che:
$$
	\nabla (f\cdot X)=df\otimes X+f\nabla X
$$
(tipo Leibniz).





