---
corso: GAL 2
data: 2026-09-24
tags:
  - lezione
argomenti:
  - Geometria differenziale
lezione-precedente:
source:
---


> [!info] Contesto
> Corso: GAL 2
> Argomenti previsti: Teoria delle curve nello spazio, definizioni e caratterizzazione: lunghezza di una curva, parametrizzazione per lunghezza d'arco, curvatura e torsione. Base di Frenet, equazione di Frenet, Teorema di Frenet

## Riassunto veloce



## Appunti

### Teoria delle curve (in $\mathbb{R}^n$)

Come cambia l'idea di curva dalla fisica alla geometria?
Con curve in fisica intendiamo descrivere un moto ben preciso, al contrario in geometria ci interessa solo la traiettoria (sostegno della curva), indipendentemente dalla legge oraria. Ci interessano "solo le figure".
Diamo ora un paio di definizioni.

>[!Abstract] **Def**: Curva parametrizata
>
>Chiamo curva parametrizzata una mappa:
>
>$$
>		\alpha: I=(a,b)\subseteq \mathbb{R} \to\mathbb{R}^k \quad (t \to \alpha(t))
>$$
>che sia:
>1. $\alpha \in C^\infty$
>2. $\dot{\alpha}(t)\neq 0 \, \forall t$, così da escludere traiettorie con punti singolari (cuspidi, punti angolosi ecc...)
>3. dev'esserci una corrispondenza biunivoca $t\leftrightarrow \alpha(t)$, per evitare che la curva passi due volte sullo stesso punto formando degli anelli
>
>Ulteriormente vorremmo escludere anche casi patologici in cui ho un punto che si avvicina infinitamente a un punto già percorso dalla mia curva:
>
>![[Pasted image 20260924085226.png]]
>
>Pertanto devo andare a rafforzare la seconda condizione, imponendo che la curva sia un omeomorfismo, cioè ci sia corrispondenza biunivoca: $(a,b)\leftrightarrow \mathrm{Im}(\alpha)$

Chiamiamo invece curva parametrizzabile l'insieme di punti:
$$
	C:=\mathrm{Im}(\alpha)=\{\alpha(t)\}\subseteq \mathbb{R}^k
$$
Grazie al terzo punto della definizione di curva parametrizzata posso trovare la mappa inversa:
$$
	P \in C\to t
$$
cioè le coordinate su $C$.

A questo punto viene naturale chiedersi se sia possibile ricostruire $\alpha$ a partire da $C$. La risposta è che no, non è possibile ed è legato alla definizione di cambio di variabili o riparametrizzazione. Una curva parametrizzabile contiene dunque meno informazioni di una curva parametrizzata.

>[!Abstract] **Def**: cambio di variabili
>Un cambio di variabili è una funzione:
>$$
>\tilde{I}=(\tilde{a},\tilde{b})\underset{t=t(\tau)}{\to}(a,b)=I
>$$
>Tramite un cambio di variabili posso ottenere moti differenti mantenendo la stessa traiettoria (cioè la stessa curva parametrizzabile). Emerge così più chiaramente la differenza tra fisica e geometria.
>Tuttavia non va bene una qualunque mappa $\tau\to t(\tau)$, ma devo avere che la nuova mappa che ottengo, $\beta(\tau)$, sia a sua volta una curva parametrizzata.
>Per far sì che ciò avvenga devo avere che la mappa $\tau\to t(\tau)$ sia:
>1. $C^\infty$
>2. invertibile con inversa $C^\infty$
>Cioè $t(\tau)$ dev'essere un diffeomorfismo

Andando a tracciare un analogia con GAL 1, andare a scegliere una parametrizzazione per una curva "equivale" a scegliere una base per uno spazio vettoriale.

Diciamo che un cambio di variabili è positivo se $t'(\tau)>0 \, \forall \tau$.
Che equivale a dire che $\alpha(t), \, \beta(\tau)=(\alpha \circ t)(\tau)$ percorrono $C$ nella stessa direzione. In caso contrario il cambio di variabili si dice negativo.

![[Pasted image 20260924092431.png]]

Ora è lecito andarsi a chiedere cosa rimanga alla curva ora che ho abbandonato la visione fisica e ho definito una curva in maniera indipendente dalle coordinate.
Ciò che rimane sono le proprietà intrinseche di $C$:
- la lunghezza di $C$
- la possibilità di integrare una funzione lungo $C$
- la possibilità di definire una curvatura per $C$
Tuttavia le coordinate restano, anche in geometria, un comodo metodo computazionale.

A questo punto, come posso verificare che queste proprietà di $C$ siano davvero indipendenti dalle coordinate scelte? Esistono 2 possibili strade:
1. definisco ognuna di queste proprietà usando una parametrizzazione e poi mostro che queste so no invarianti per cambi di parametrizzazione (approccio di Analisi 3)
2. (Solo per le curve, per le superfici non sarà così) posso andare a trovare una parametrizzazione canonica "standard" e usarla per definire le varie proprietà. Essendo questa unica, non ci sono scelte arbitrarie ed il risultato dipende solo da C.

#### Lunghezza di $C$.

- **Strategia 1**:
___
Prendo $C$ curva parametrizzabile e scelgo una parametrizzazione $\alpha (t): C=\mathrm{Im}(\alpha)$.
$$
	\alpha:(a,b)\to\mathbb{R}^n
$$
Definisco la lunghezza di $C$ come:
$$
	L(\alpha):=\int^b_{a}|\dot{\alpha}(t)|dt
$$
A questo punto considero una riparametrizzazione: $t=t(\tau), \quad\tau \in(\tilde{a},\tilde{b})$.
Dunque:
$$
	\beta=(\alpha \circ t)(\tau) \quad \text{e} \quad L(\beta):=\int^\tilde{b}_{\tilde{a}}|\dot{b}(\tau)|d\tau
$$
Verifico che $L(\alpha)=L(\beta)$ sfruttando la formula di cambio di variabili per gli integrali.
$$
	\int^b_{a}|\dot{\alpha}(t)|dt =\int^{t^{-1}(b)}_{t^{-1}(a)}|\dot{\alpha}(t)|t'd\tau = \int^\tilde{b}_{\tilde{a}}|\dot{\beta}(\tau)|d\tau
$$
Dunque la lunghezza di $C$ è indipendente dalla parametrizzazione

- **Strategia 2**:
___
Vado a definire la parametrizzazione "speciale":
>[!Abstract] **Def**: Parametrizzazione per lunghezza d'arco
> 
>$C$ si dice parametrizzata per lunghezza d'arco $\alpha(s)$ se:
>
>$$
>	\exists \,p\,\in\,C \, :\, \forall p'=\alpha(s) \text{ ho } \int^S_{0}|\dot{\alpha}(s)|ds=S
>$$

In relatività questo equivale a parametrizzare il moto usando l'elemento metrico $ds$.
Per verificare che una parametrizzazione $\alpha(s)$ sia la parametrizzazione per lunghezza d'arco mi basta verificare che $|\dot{\alpha}(s)|\equiv 1$.
Ogni curva ammette una parametrizzazione per lunghezza d'arco e $$L(C)=\text{valore max-valore mic della coordinata s}$$
**Oss:** in realtà la scelta della parametrizzazione per lunghezza d'arco non è perfettamente univoca in quanto posso sempre variare la scelta del punto di partenza o dell'orientamento.

**Oss:** l'esistenza di $S$ parametrizzazione per lunghezza d'arco, ci dice qualcosa di abbastanza ovvio ma comunque molto profondo.
Ogni curva io prenda, è sempre isometrica ad un segmento in $\mathbb{R}$. Esiste cioè una corrispondenza biunivoca tra i punti di una retta e di una curva, che **conserva le distanze**.

![[Pasted image 20260928135110.png]]

Questa isometria non è altro che la parametrizzazione per lunghezza d'arco.

L'importanza di questo fatto diventa immediatamente più evidente quando proviamo a fare qualcosa di analogo in dimensioni superiori alla prima, dove ci accorgiamo non essere possibile. Lo renderemo poi esplicito tramite il Teorema Egregium di Gauss, dove identificheremo in una proprietà chiamata curvatura l'origine del problema.

![[Pasted image 20260928135310.png]]

Continuiamo ora con la definizione di proprietà intrinseche delle curve.

#### Integrazione di una funzione lungo una curva

Considero $f:C\to\mathbb{R}$, come posso integrare questa funzione lungo $C$?

- **Strategia 1**
___
definisco l'integrale nel seguente modo:
$$
	\int_{C} f :=\int^b_{a}(f \circ \gamma)(t)|\dot{\gamma}|dt
$$
e successivamente vado a dimostrare l'invarianza sotto cambi di parametrizzazione. Questo è il modo in cui vado a definire il lavoro.

- **Strategia 2**
___
Uso la parametrizzazione "privilegiata", quella della lunghezza d'arco $\alpha(s)$.
$$
	\int_{C}f:=\int(f \circ \alpha(s))|\dot{\alpha}|ds=\int f \circ \alpha(s) ds
$$

A questo punto è lecito andarsi a chiedere cosa succederebbe se usassimo come integrale il seguente:
$$
	\int^a_{b}(f \circ\gamma)(t)dt
$$
senza il modulo della velocità.
Possiamo facilmente dimostrare come questo non sia invariante per cambi di parametrizzazione, e non sia dunque una buona definizione per l'integrale **sulla curva**. Possiamo usarlo tutt'al più come integrale sulla parametrizzazione $\gamma(t)$.

#### Curvatura

Abbiamo precedentemente accennato che il problema delle cartine perfette per una superficie è legato al concetto di curvatura. Non avendo lo stesso preoblema sulle curve, ne possiamo dedurre che il significato geometrico di curvatura per una curva sia significativamente diverso.
A grandi linee la curvatura di una curva mi va ad indicare *quanto la curva si contorce nel suo spazio ambiente.*

Partiamo dallo studio di un caso semplificato. D'ora in poi adotteremo solo più l'approccio della lunghezza d'arco.

Partiamo con lo studio di $C \subseteq \mathbb{R}^2$, cioè una curva che giace su di un piano.

![[Pasted image 20260928141009.png|388]]

Intuitivamente l'idea di contorsione sarà legata alla variazione della retta tangente, andiamo ora a formalizzarlo.

>[!Abstract] **Def:** Spazio Tangente (in $\mathbb{R}^2$)
>Considero una curva $C$ ed un punto $p \in C$.
>Scelgo una parametrizzazione $\alpha(t)$, allora $p:=\alpha(t_{0})$. Il vettore velocità $\dot{\alpha}(t_{0})\in \mathbb{R}^2$.
>Definiamo Spazio Tangente di $C$ in $p$ il sottospazio unidimensionale di $\mathbb{R}^2$ così definito: 
>$$
>	T_{p}C:=Span\{ \dot{\alpha}(t_{0}) \}=\{ \lambda \dot{\alpha}(t_{0}):\lambda\in\mathbb{R} \}
>$$
>![[Pasted image 20260928141802.png]]

In realtà possiamo osservare una discrepanza tra la definizione e la figura. Quello che abbiamo definito è un sottospazio ed in quanto tale deve passare per l'origine. Quello che abbioamo disegnato invece passa per $p$ ed è dunque stato traslato.

Lo $Span$ della parametrizzazione resta invariato sotto cambi di coordinate e potrei dimostrarlo, altrimenti posso andare a definire lo spazio tangente utilizzando direttamente la parametrizzazione per lunghezza d'arco ed ottengo lo stesso risultato.

A questo punto studiamo come misurare la variazione della retta tangente. L'idea, come nei corsi di analisi resta quella di andare ad operare una derivazione, ma come faccio la derivata di una retta?
Partiamo dall'osservazione che ogni retta $l(t)$ non è altro che uno spazio undimensionale, possiamo dunque andare ad identificarlo con un versore $V(t)$ con $|V|=1$.
Andiamo ora a lavorare con la lunghezza d'arco. Alla curva $C$ associamo la parametrizzazione $\alpha(s)$. A questo punto, possiamo andare ad identificare la retta tangente in ogni punto tramite il vettore tangente così definito:
$$
	\vec{t}(s):=\dot{\alpha}(s)
$$
Facciamo ora alcune osservazioni:
- **Oss. 1:** 
$$
	|\dot{\alpha}|^2\equiv1 \Rightarrow \dot{\alpha}\cdot \dot{\alpha}=1
$$
per ogni valore di $s$. Andandolo a derivare otteniamo dunque:
$$
	\frac{d}{ds}(\dot{\alpha}\cdot \dot{\alpha})=0=\dot{\alpha}\cdot \ddot{\alpha}+\ddot{\alpha}\cdot \dot{\alpha}=2\dot{\alpha}\cdot \ddot{\alpha}
$$
Con la parametrizzazione per lunghezza d'arco accelerazione e velocità sono tra loro normali, questo da un punto di vista fisico non ci stupisce granchè.

- **Oss. 2:** Posso andare a definire i versori normali a una curva, $\vec{n}(s)$, in maniera univoca e indipendente dall'accelerazione, tramite delle rotazioni antiorarie.

![[Pasted image 20260928143515.png]]

Unendo le due osservazioni possiamo andare a scrivere:

$$
	\ddot{\alpha} = k(s)\vec{n}(s)
$$
con:
$$
	k(s)=\vec{t}'\cdot \vec{n}(s) = \ddot{\alpha}(s)\cdot \vec{n}(s)
$$

$k(s)$ è una funzione $C^\infty$ di segno variabile che va a misurare le variazioni della retta tangente alla curva. Chiamiamo questa funzione **curvatura** di $C$.

Si dimostra facilmente che laddove $k(s)\equiv 0$ troviamo che $C$ è un segmento.

Facciamo ora un'osservazione di natura grafica, da un disegno è possibile capire intuitivamente il verso di $\ddot{\alpha}$ e con esso il segno di $k$. Da qui capiamo che il segno di $k$ mi da un'indicazione sulla concavità della curva.

![[Pasted image 20260928144217.png]]

Andiamo ora a studiare una curva in $\mathbb{R}^3$.
Aggiungendo una dimensione siamo andati ad aggiungere un ulteriore dimensione in cui la curva potrebbe andare a piegarsi. Provando ad andare ad adattare lo stesso approccio usato fin'ora ci accorgiamo che la definizione di un vettore normale smette di essere semplice come in $\mathbb{R}^2$. In questo caso abbiamo infiniti vettori normali, che giacciono su di un piano.

![[Pasted image 20260928144546.png]]

Dobbiamo scegliere quale versore normale utilizzare.
Dai calcoli di prima otteniamo ancora $\dot{\alpha} \perp \ddot{\alpha}$. Andiamo dunque a definire una normale *canonica* nel seguente modo:
$$
	\vec{n}(s):=\frac{\ddot{\alpha}(s)}{|\ddot{\alpha}(s)|}
$$
Questa scelta è ovviamente più limitante rispetto a quella che abbiamo fatto in precedenza perchè ci restringe a curve tali che $|\ddot{\alpha}|\neq {0} \, \forall  \, s$. Dunque non posso definire la normale canonica a dei segmenti nello spazio.

A questo punto otteniamo che il vettore accelerazione è:
$$
	\ddot{\alpha}(s)=|\ddot{\alpha}|\vec{n}
$$
e possiamo dedurre che la curvatura sia: $k(s):=|\ddot{\alpha}(s)|$.
Come prima $k(s)$ misura la variazione della retta tangente, ma questa volta può assumere soltanto valori positivi.

#### Torsione

Come accennavamo prima, una curva in $\mathbb{R}^3$ si "contorce" in più direzioni, possiamo dunque andare a definire "una seconda curvatura", che misura come la curva si avvita su stessa.
Per fare ciò andiamo a misurare la variazione della direzione normale al piano formato da $\vec{t} \text{ e } \vec{n}$. 
![[Pasted image 20260928150839.png]]
Lo facciamo tramite il versore normale al piano, che possiamo scrivere come:
$$
	\vec{b}(s) = \vec{t}(s) \times \vec{n}(s)
$$
e lo chiamiamo vettore binormale; $\vec{b} \, , \,  \vec{t} \text{ e }\vec{n}$ formano una base ortonormale di $\mathbb{R}^3$.
Facciamo un paio di osservazioni:
$$
	\begin{aligned}
	\vec{b}\cdot \vec{t}=0=\vec{b}\cdot \vec{n} \quad \text{e} \quad |\vec{b}|^2=1
	\end{aligned}
$$
Andando a derivare troviamo che:
$$
	\dot{b}\cdot \vec{t}+\vec{b}\cdot \dot{t}\equiv 0
$$
ma:
$$
	\vec{b}\cdot \dot{t}=\vec{b}\cdot k(s)\vec{n}(s)=0
$$
dunque:
$$
	\dot{b}\cdot \vec{t}=0 \quad \text{e} \quad \dot{b} \perp \vec{t}
$$
Derivando $|\vec{b}|^2$ otteniamo, come nel caso precedente, $\dot{b} \perp \vec{b}$.
Dunque:
$$
	\dot{b} \perp \vec{b} \quad \text{e} \quad \dot{b}\perp \vec{t} \quad \Rightarrow \quad \dot{b} \parallel \vec{n}
$$
Posso quindi riscrivere, nella base $\{ \vec{b},\vec{t},\vec{n} \}$:
$$
	\dot{b}=\tau(s)\vec{n}(s)
$$
la funzione $\tau(s)$ prende il nome di **torsione** e misura l'oscillazione del piano definito dallo $span(\vec{t},\vec{n})$.

La base che abbiamo usato fino ad adesso, $\{ \vec{b},\vec{t},\vec{n} \}$ ortonormale su ogni punto della curva, prende il nome di **base di Frenet**.

A questo punto emergono alcune domande che ha senso porsi e a cui ha senso andare a rispondere.

- **Q1)** Ha senso continuare a derivare cose per ottenere ulteriori "curvature"?
- **Q2)** Da quanti parametri dipende $C \subseteq \mathbb{R}$? Quanti sono i gradi di libertà di una curva?
- **Q3**) Da quanti parametri dipende la posizione di un punto su una curva (nota)?

##### Risposta a (Q1)

Fin'ora ci siamo occupati dello studio di $\dot{t} \text{ e } \dot{b}$. Proviamo a calcolare $\dot{n}$.
$$
	\vec{n}=\vec{b}\times \vec{t}
$$
$$
	\implies \dot{n}=\dot{b}\times \vec{t}+b\times \dot{t}=\tau(s)\vec{n}\times \vec{t} +k(s)\vec{b}\times \vec{n}=-\tau \vec{b}-k\vec{t}
$$
cioè $\dot{n}$ ricicle le stesse funzioni di prima, derivando l'ultimo versore non ottengo nuove informazioni. Ogni altro vettore può essere scritto come combinazione lineare degli elementi della base di Frenet, dunque non mi darà nuove informazioni.

##### Risposta a (Q2)

La risposta al secondo quesito ci viene data dal Teorema di Frenet, un teorema che si occupa del seguente sistema di equazioni differenziali, le cui incognite sono i vettori della base di Frenet.
$$
	\begin{cases}
	\dot{t}=k\vec{n} \\
	\dot{n}=-k\vec{t}-\tau \vec{b} \\
	\dot{b}=\tau \vec{b}
	\end{cases}
$$
Le uniche informazioni note del sistema sono le funzioni curvatura e torsione.
Possiamo riscrivere il sistema in forma matriciale.
Poichè $\vec{t},\vec{n},\vec{b}$ formano una base $ON$, posso rappresentarla tramite una matrice $M(s)\in SO^3$
$$
	M(s):=\begin{pmatrix}
	\vec{t}&\vec{n} &\vec{b}
	\end{pmatrix}
$$
E il sistema diventa:
$$
	\dot{M}(s)=M(s)\cdot \begin{pmatrix}
	0 & -k(s) & 0  \\
	k(s) & 0 & \tau(s) \\
	0 & -\tau(s) & 0
	\end{pmatrix}
$$
Questa forma diventerà molto interessante quando parleremo di algebre di Lie.

>[!Example] Teorema di Frenet
>Siano date $k(s)$, $\tau(s):\,(a,b)\to \mathbb{R} \, \in C^\infty$
>tali che $0\in(a,b), \,k(s)>0$.
>Scegliamo $p\in \mathbb{R}^3$ e una base $ON$ positiva (in $p$) $(t,n,b)\equiv M(0)\in SO^3$
>$\implies \exists$ un'unica curva $C$ passante per $p$ e avente $k$ e $\tau$ come propria curvatura e torsione.
>Il parametro $s\in(a,b)$ è la sua lunghezza d'arco.
>
>**Corollario:** 2 curve con stessa curvatura e torsione coincidono a meno di movimenti rigidi (che siano rotazioni o traslazioni).

Dunque la risposta a **(Q2)** è che ci bastano 2 parametri per costruire una curva.

**OSS:** ad un fisico per costruire la legge oraria (cioè la curva) servono tre parametri (le tre componenti della forza). La ragione è che in questo caso (e nella maggior parte dei casi di interesse fisico) non ci interessa la curva parametrizzabile (che interessa invece un geometra) ma la curva parametrizzata. Il parametro aggiuntivo ci fornisce un informazione aggiuntiva, la parametrizzazione della curva.

##### **Risposta a (Q3)**

La risposta al quesito 3 è più semplice. Per descrivere la posizione di un punto su una curva nota ci basta un solo parametro reale, infatti sappiamo che tra una curva e una retta sussiste una corrispondenza biunivoca, resa esplicita dalla parametrizzazione per lunghezza d'arco. Quell'unico parametro sarà dunque $s$.
Questo ci permette di concludere che $Dim(C)=1$.

#### Bozza di dimostrazione del Teorema di Frenet

Analizziamo la dimostrazione al teorema per step.
1. usiamo $k, \tau$ per impostare l'equazione di Frenet e la risolviamo (o meglio, verifichiamo l'esistenza di un unica soluzione $M(s)$). A questo punto abbiamo trovato una candidata per la base di Frenet.
**OSS:** per poter risolvere l'equazione ho bisogno di una condizione iniziale $M(0)$ per risolvere l'equazione, ma questa è fornita dalle ipotesi del teorema.
2. sfruttiamo il fatto che $\vec{t}(s)$ è la prima colonna della matrice $M(s)$ appena ottenuta. Risolviamo $\dot{\alpha}=\vec{t}(s)$ per ottenere la parametrizzazione per lunghezza d'arco $\alpha(s)$. Abbiamo così ottenuto una curva che per costruzione ha curvatura e torsione $k,\tau$. Anche qua per risolvere l'equazione abbiamo sfruttato la condizione iniziale fornita dalle ipotesi: $\alpha(0)=p$.

>[!Attention] Achtung!
>Manca in quanto fatto una dimostrazione formale che $M(s)\in$ sempre a $SO^3$, come abbiamo ipotizzato nel passaggio in cui diciamo che $\vec{t}(s)$ è la prima colonna di $M(s)$. 
>Per verificare che questo succeda possiamo fare molti conti per vedere come variano le norme e gli angoli dei vettori della matrice (che schifo). Alternativamente possiamo sviluppare anuovi strumenti teorici. 
>Scegliamo la seconda opzione e torniamo sullo studio di questo problema dopo aver studiate la teoria dei gruppi e delle algebre di Lie.




## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

