---
corso: GAL 2
data: 2026-10-12
tags:
  - lezione
argomenti: []
lezione-precedente: "[[Superfici nello spazio]]"
source:
---


> [!info] Contesto
> Corso: undefined
> Argomenti previsti: 

## Riassunto veloce



## Appunti

Iniziamo una piccola parentesi sugli elementi di base della branca della topologia necessari a comprendere la geometria più astratta che andremo a discutere più avanti.
### Definizioni base e proprietà generali

>[!Abstract] Def: Topologia di un insieme
>Sia $X$ un insieme. Una **topologia** su $X$ è una collezione $\tau$ si sottoinsiemi $A_{i}\subseteq X$; $\tau=\{ A_{i} \}_{i\in I}$ tale che:
>1. $\emptyset\in \tau, \, X\in \tau$
>2. Qualunque unione di elementi di $\tau$ dev'essere un elemento di $\tau$
>3. Qualunque intersezione di elementi di $\tau$ dev'essere un elemento di $\tau$

I sottoinsiemi $A_{i}$ prendono il nome di aperti di $X$.
Un esempio classico di topologia di $\mathbb{R}$ è la collezione:
$\tau=\{ \text{unione di intervalli aperti nel senso classico }(a,b)  \}$, detta topologia standard di $\mathbb{R}$.
Se per convenzione ammettiamo l'insieme vuoto in $\tau$ le altre proprietà si vedono a occhio.

Una coppia data da un insieme e da una topologia su quell'insieme prende il nome di spazio topologico.
$$
	(X,\tau)\equiv \text{ "spazio topologico"}
$$
Soltanto da queste differenze risulta difficile farsi un'idea concreta di quale sia l'utilità della topologia. Intuitivamente quello che possiamo iniziare a dire è che la topologia serve per organizzare i punti di $X$ in "zone" e "bacini di influenza" (gli aperti).
Questa organizzazione è necessaria per poter parlare di temi critici come la continuità, la convergenze e la compatezza

Per chiarire ulteriormente le idee occupiamoci dello studio di alcune topologie importanti, alcune delle quali abbiamo già incontrato nel corso dei nostri studi.

MODELLO 1:
$$
	\begin{aligned}
	X&=\mathbb{R}^n \\
	\text{aperti}=\text{palle } B(x_{0},r)&=\{ x\in \mathbb{R}^n:|x-x_{0}|<r \}
	\end{aligned}
$$
Questa è la topologia che incontriamo in tutti i corsi di analisi e che ci permette di definire il concetto di limite e conseguentemente di continuità ecc...
Studiando le proprietà di questo spazio topologico si possono andare ad astrarre le $3$ proprietà tipiche degli aperti e che usiamo per andare a definire una topologia $\tau$.

MODELLO 2:
$$
	X=S \subseteq \mathbb{R}^3 \text{ regolare }
$$
Una superficie regolare immersa in $\mathbb{R}^3$ è dotata di una topologia naturale "indotta da $\mathbb{R}$".
$$
	A\in S \text{ aperto} \underset{\text{def.}}{\iff}A=S\cap \tilde{A},\,\text{ con } \tilde{A} \text{ aperto di }\mathbb{R}^n
$$

In generale possiamo dire che preso un qualunque spazio topologico $(X,\tau)$ è possibile definire una topogia indotta in modo analogo per ogni insieme $Y\subseteq X$.

Introduciamo ora ulteriori definizioni utili a caratterizzare una topologia.

- **DEF:** Sia $(X,\tau)$ uno spazio topologico. Una sottocollezione di aperti $\sigma\subseteq \tau$ si dice *base* per $\tau$ se ogni altro aperto di $\tau$ è ottenibile come *UNIONE* di $A_{i}\in \sigma$

Riprendendo il primo esempio; se la topologia standard di $\mathbb{R}$ sono gli intorni aperti e le loro unioni, allora una base della topologia standard sarà semplicemente $\sigma=\{ \text{int. aperti} \}$.

- **DEF**: Si dice che $\sigma \subseteq \tau$ è una prebase se ogni altro aperto è ottenibile come *UNIONI e/o INTERSEZIONI* di $A_{i}\in \sigma$.

Nell'esempio di prima una prebase sarebbe l'insieme delle semirette aperte $\sigma=\{ (-\infty,a);\,(b,+\infty) \}$.

- **DEF**: Sia $(X,\tau)$ uno spazio topologico. $C \subseteq X$ si dice chiuso se il suo completamento è aperto.

- **DEF**: $(X,\tau)$ si dice sconnesso se $\exists A_{1},A_{2}$ disgiunti e aperti non vuoti tali che $X=A_{1}\cup A_{2}$

- **DEF**: $(X,\tau)$, $x\in X$. Un intorno di $x$ è un qualunque aperto contenente $x$: $U_{x}$.

A questo punto facciamo ulteriori esempi che riguardino queste nuove definizioni.

Per ogni insieme $X$ è possibile definire la seguente topologia $\tau_{0}=\{ \emptyset,X \}$ che prende il nome di *topologia banale/grossolana*. $(X,\tau_{0})$ è uno spazio topologico connesso.

$\forall X$ possiamo anche definire la *topologia fine/discreta* $\tau_{\infty}\{ \text{ogni sottoinsieme di x} \}$. 
Osserviamo $X=\cup \{ x\in X \}$, duque questa scelta è molto sconnessa.

### Continuità

Occupiamoci ora di una definizione molto importante, quella di continuità:

>[!abstract] Def: funzione continua 
>$$
>	f:(X_{1},\tau_{1})\to(X_{2},\tau_{2})
>$$
>Si dice CONTINUA se $\forall A\in \tau_{2}$, $f^{-1}(A)={ x\in X_{1}:f(x)=A } \in \tau_{1}$

Analogamente una funzione si può considerare continua se la controimmagine di un chiuso è sempre un chiuso.

**OSS:** per dimostrare la continuità basta lavorare con la base di $\tau_{2}$.

A fronte di questa definizione risulta chiaro come sia sempre possibile trasformare funzioni discontinue utilizzando una topologia in funzioni continue in un'altra topologia. Ad esempio, funzioni che hanno come topologia di arrivo la topologia fine sarà sempre continua.

Al di là della continuità, esiste una condizione ancora più forte:

>[!abstract] Def: Omeomorfismo
>$f:(X_{1},\tau_{1})\to(X_{2},\tau_{2})$ si dice omeomorfismo se è continua, invertibile con inversa continua.
>Se esiste un omeomorfismo tra 2 spazi topologici, questi 2 spazi sono topologicamente indistinguibili.

Per esplorare ulteriormente l'utilità della topologia, andiamo ad analizzare meglio alcuni concetti.
### Precisazioni sui sottoinsiemi chiusi

Per capire meglio il significato di chiuso andiamo a definire alcuni nuovi concetti
**Def**: $Y\subseteq X, x \in X$. $x$ aderente a $Y$ se ogni intorno $U_{x}$ di $x$ ha intersezione non vuota con $Y$: 
$U_{x}\cap Y\neq \emptyset$.

Ad esempio, ogni $y\in Y$ è aderente a $Y$ perchè $U_{y}\cap Y$ è un sottoinsieme di $Y$.
Analogamente un punto sul bordo di $Y$ è sempre aderente a $Y$.

**Proposizione:** un sottoinsieme di $X$ è chiuso $\iff$ contiene tutti i suoi punti aderenti (intuizione: include il proprio bordo).

Solitamente si adotta l'altra definizione e si usa questa proposizione come test di chiusura.

### A cosa serve la topologia?

1. Serve a garantire l'esistenza di punti di massimo o minimo di una funzione  $f:X\to \mathbb{R}$.
   Come? Cerco una topologia tale che $X$ sia *compatto*,  inoltre vogliamo che questa topologia renda $f$ continua. Se riusciamo a fare ciò $\implies$ è garantita l'esistenza di punti di massimo o minimo di $f$. (La dimostrazione è lasciata a noi nei fogli di esercizi).
   **Achtung!** Vedremo che trovare questa topologia è delicato, la compattezza (pochi aperti) e la continuità (molti aperti) "cozzano".
2. Sfruttiamo la topologia per produrre superfici astratte, cioè superfici non immerse in $\mathbb{R}^3$.

   Scelgo come insieme l'intervallo $X=[0,1) \subset \mathbb{R}$. 
   
   ![[Pasted image 20261013163318.png]]
   
   Scelgo una nuova topologia partendo da una base, ad esempio: 
$$
	\begin{cases}
	(a,b) \in \tau_{std} \\
	[0,\varepsilon) \cup (1-\varepsilon,1)
	\end{cases}
$$
   Anche $[0,\varepsilon)\text{ e }(1-\varepsilon,1)$ appartengono separatamente alla $\tau_{std}=\text{ indotta da }\mathbb{R}$, sono dunque standard per la topologia indotta su $X$ da quella standard (non sono però necessariamente aperti di $\mathbb{R}$, infatti $[0,\varepsilon)$ non lo è). 
   Scegliendo come base l'unione tra i 2 abbiamo impoverito la topologia standard (cioè abbiamo costruito una nuova topologia in cui i 2 insiemi precedentemente aperti, $[0,\varepsilon)$ e $(1-\varepsilon,1)$, smettono di essere aperti; gli unici aperti sono dati dall'unione tra i 2). 
   Con questa nuova topologia $\tau$, lo spazio $(X,\tau)$ è omeomorfo a un cerchio, tramite l'omeomorfismo $f(x\in X)=e^{ 2\pi ix }$. 
   Siamo riusciti a dare una definizione del cerchio indipendentemente da $\mathbb{R}^2$ (necessario invece in analisi in analisi).
   In maniera simile possiamo andare a definire il Toro in maniera indipendente da $\mathbb{R}^3$.
   ![[Pasted image 20261013163354.png]]

   
   Giocando in questo modo posso andare a definire altre superfici immerse in $\mathbb{R}^3$ indipendentemente da $\mathbb{R}^3$, come il Nastro di Moebius.
   Non solo! Posso anche andare a costruire superfici astratte, prive di una rappresentazione in $\mathbb{R}^3$, l'esempio classico è la bottiglia di Klein (mancanza di disegno data da una mancanza di comprensione reale da parte mia).
   Più avanti questo ci permetterà di parlare di varietà astratte.

3. La topologia ci permette di spiegare la sfera di Riemann: $\mathbb{R}^2 \cup \{ p \}$ dove $p$ è il punto all'infinito. Con la topologia si può dimostrare che $\mathbb{R}^2 \cup \{ p \}\simeq S^2$. Per farlo dobbiamo prima introdurre i concetti si successioni e convergenza.

### Successioni e convergenza

**Def:** Sia $(X,\tau)$ uno spazio topologicoe $x\in X$. Una successione $\{ x_{n} \}\subseteq X$ converge a $x$ $(x_{n}\to x)$ se e solo se $\forall U_{x}\, \exists N:\forall n>N\,, x_{n}\in U_{x}.$ In tal caso $x$ si dice limite di $\{ x_{n} \}$.

Torniamo alla sfera di Riemann. Consideriamo come spazio topologico l'insieme $\mathbb{R}^2 \cup \{ p \}$ con la topologia avente come base le palle aperte $B(0,r)$ ed il compelementare delle palle $B(0,r)\cup \{ p \}$ (che sono gli aperti contenenti p, ovvero gli aperti di $p$).
Cosa vuol dire che $x_{n}\to p$ con questa scelta di topologia? Significa che per ogni intorno di $p$ esiste un $N$ tale che $\forall n>N:$  $x_{n}\in U_{p}$, cioè $|x_{n}|>r$ oppure $x_{n}=p$. Intuitivamente questo implica che $p$ stia "all'infinito", tuttavia cambiando topologia non è detto che $p$ resti un "punto all'infinito".
Per capire come mai studiamo il caso più semplice di $\mathbb{R}$.
$X=\mathbb{R}\cup \{ p \}$ con la topologia data dalla base $$\begin{cases}(a,b) \\ (-\varepsilon,0)\cup \{ p \}\cup(0,\varepsilon) \end{cases}$$In questo spazio topologico quando mi avvicino a $0$ mi avvicino allo stesso modo anche a $p$, sto "sovrapponendo" il punto extra allo $0$.Dunque cambiando la scelta di topologia posso scegliere di "legare" $p$ a qualunque punto.

Ultimo esempio (strano).
La successione $x_{n}=\frac{1}{n}$ ha 2 limiti distinti, cioè *non vale l'unicità del limite*. Inutile dire che vorremmo ciò non succeda, andiamo pertanto ad introdurre una nuova definizione

**Def:** uno spazio topologico si dice di Hausdorff se $\forall x_{1}\neq x_{2}\,\exists U_{x_{1}},U_{x_{2}}:U_{x_{1}}\cap U_{x_{2}}\neq \emptyset$
Per ogni spazio topologico di Hausdorff il limite di una successione è unico. per questo motivo, le condizioni necessarie ad essre uno spazio di Hausdorff formano una "quarta" condizione, detta **secondo assioma di separabilità**.

Occupiamoci ora dell'esistenza di limiti. Questo non si può garantire ma è possibile "facilitarlo", sfruttando le proprietà di spazi Hausdorff e di alcuni nuovi assiomi.
Introduciamo dunque un nuovo assioma, che ci porterà a garantire l'esistenza di successioni:

**Primo assioma di numerabilità T1**:
Sia $(X,\tau)$ uno spazio topologico, $\forall x \in X \,\exists$ una collezione numerabile di intorni di $U_{x}$ tale che ogni altro intorno contenga uno di essi.

Questo non è sempre vero (indi per cui è un assioma), ma i controesempi sono complicati.

A cosa ci serve? 
1. Possiamo usarli per costruire una collezione di intorni $U_{x}^n$ tale che:
   $U_{x}^{n+1}\subseteq U_{x}^n \subseteq U_{x}^{n-1}\dots$ ovvero una collezione di intorni "concentrici", organizzati in modo comodo.
   Per farlo partiamo dalla collezione e costruiamolo per intersezioni successive:
$$
	\begin{aligned}
	U^1_{x}&=I \text{ elemento della collezione}\\
	U_{x}^2&=I\cap II\\
	U_{x}^3&=I\cap II\cap III\\
	&\text{ecc...}
	\end{aligned}
$$
2. Usando la collezione così "ordinata" $U_{x}^n$ posso garantire l'esistenza di una successione $x_{n}\to x$. 
$$
   	\begin{aligned}
	x_{1}&\in U^1_{x}\\
	x_{2}&\in U^2_{x}\\
	x_{3}&\in U^3_{x} \, \dots\\
	x_{n}&\to x \quad \text{ perchè } \forall U_{x}\, \exists N: \, x_{n}\in U_{x},\,n>N
	\end{aligned}
   $$

Il primo assioma di numerabilità garantisce l'esistenza di $U^n_{x}$, necessaria all'esistenza di una successione.

**Secondo assioma di numerabilità:**
$(X,\tau)$ ammette una base numerabile. 
Questa condizione implica il primo assioma, dunque è una condizione più forte.

In geometria differenziale lavoriamo sempre nelle condizioni dell'assioma di Hausdorff e del secondo assioma di numerabilità.

**Esempio 1:** $X\in \mathbb{R}^n$ con la topologia $\tau_{std}$, con base $\{ B(x,r) \}$.

Soddisfa Hausdorff? Sì, presi 2 punti mi basta costruire un intorno di ognuno con raggio minore della metà della distanza tra i 2 punti. Questo ci porta all'esistenza del limite.

Soddisfa il primo assioma? Sì, basta usare come intorni $U_{x}^n=B\left( x, \frac{1}{n} \right)$. Infatti in $\mathbb{R}$ possiamo convergere a $x$ tramite $x_{n}=x+\frac{1}{n}$.

Soddisfa il secondo assioma? La base $\{ B(x,r) \}$ non è numerabile (perchè dipende da parametri reali, non numerabili), posso trovarne un'altra?
Posso scegliere ad esempio $\left\{  B\left( x, \frac{1}{n} \right): \,x\in \mathbb{Q^n}  \right\}$. Infatti l'insieme dei numeri razionali è denso ma è numerabile!

Era ovvio che questo esempio andasse bene perchè in geometria differenziale ci capita di lavorare con $\mathbb{R}^n$ con la topologia standard.

**Esempio 2:** $(\mathbb{R};\tau_{0})$, con $\tau_{0}=\{ \emptyset,X \}$.

Soddisfa Hausdorff? No perchè gli unici intorni sono $U_{x_{1}}=U_{x_{2}}=\dots=X$.
Dunque deve cadere l'unicità del limite. 
Consideriamo $x_{n}\in(\mathbb{R},\tau_{0})$ possiamo costruire una successione che converga ad un punto solo? No, perchè qualunque successione può convergere in qualunque punto.

Soddisfa il primo assioma? Sì, mi basta prendere $U_{x}^n\equiv X$, infatti è contenuto in ogni altro intorno perchè tutti gli altri intorni sono semplicemente $X$. Idem per il secondo assioma, come base mi basta prendere $X$.

Conclusioni: Una topologia con pochi aperti soddisfa molto facilmente $I$ e $II$ ma fatica a soddisfare Hausdorff e viceversa. A casa prova a studiare cosa succede con $\tau_{\infty}$.

Perchè è così importante costruire successioni?

___
1. Ci permette di studiare molti problemi usando il linguaggio delle successioni!
Ad esempio sappiamo che essere sempre vero:
$$
	\begin{aligned}
	f:(X_{1},\tau)&\to(X_{2},\tau_{2}) \quad \text{continua}\\
	\text{allora } x_{n}\to x &\implies f(x_{n})\to f(x)
	\end{aligned}
$$
- **Dim:**
  So che $f$ è continua e $x_{n}\to x$. Devo dimostrare $f(x_{n})\to f(x)$.
  $f$ continua $\implies x\in f^{-1}(U_{f(x)})$, intorno aperto di $x$. 
  Allora (usando l'Hp $x_{n}\to x$) posso dire che $\exists N: \forall n>N,\, x_{n}\in f^{-1}(U_{f(x)}) \implies f(x_{n})\in U_{f(x)}$.
  $\blacksquare$

Questo risultato lo abbiamo ottenuto senza usare alcun assioma aggiuntivo.

Il viceversa vale solo se $(X_{1},\tau_{1})$ soddisfa il $I$ assioma di separabilità. ($*$)
Con viceversa intendiamo:
$$
	\begin{aligned}
	&\text{se } \forall x_{x}\to x \text{ si ha che } f(x_{n})\to f(x)\\
	&\text{allora } f \text{ è continua}
	\end{aligned}
$$
___
2. Posso trovare un'ulteriore modo per verificare che un insieme sia chiuso.
   Se $X$ soddisfa il $I$ assioma abbiamo che:
   preso $Y\subseteq X$, $x$ è aderente a $Y \iff \exists\, y_{n}\in Y: y_{n}\to x$ (da dimostrare).
   quindi, $C\subseteq X$ chiuso $\iff$ contiene tutti i limiti delle successioni, $x_{n}\in C$. 

Sfruttando questo ulteriore risultato è possibile dimostrare ($*$), prova a casa!

- **Dim di ($*$)**:
  Sia $f:X_{1}\to X_{2}$.
  Considero $C_{2}\subseteq X_{2}$, voglio dimostrare che $f^{-1}(C_{2})=\{ x\in X_{1}:f(x)\in C_{2} \}$ sia un chiuso $C_{1}$.
  Usiamo il fatto $C_{2}\subseteq X_{2}$ chiuso $\iff$ contiene tutti i limiti delle successioni, $f(x_{n})\in C_{2}$.
  $f(x_{n})\to f(x)$ per ipotesi. Dunque $C_{2}$ deve contenere necessariamente $f(x)$, limite delle successioni $f(x_{n})$ appartenenti a $C_{2}$.
  Sappiamo anche che $f^{-1}(f(x))=Id(x)=x\implies x\in f^{-1}(C_{2})$.
  Ma, per ipotesi ho che $\forall x_{n}: \, x_{n}\to x$. Allora $f^{-1}(C_{2})$ contiene tutti i limiti delle successioni $f^{-1}(f(x_{n}))\equiv x_{n}\to x$, e per il risultato appena dimostrato devo avere che $f^{-1}(C_{2})$ dev'essere un chiuso. Dunque, $f$ è continua. $\blacksquare$  

___
Possiamo finalmente occuparci di "facilitare" l'esistenza del limite.

**OSS generale:** non si può sperare che in $(X,\tau)$ + assiomi vari si garantisca l'esistenza di limiti per ogni successione.
L'esempio classico in $\mathbb{R}$ è $x_{n}=(-1)^n$.
Possiamo però studiare le sottosuccessioni: $x_{2n}\to{1}, \quad x_{2n+1}\to-1$ .

**Def:** Dato $(X,\tau)$ e $x_{n}$, l'insieme dei punti limite di $x_{n}$ è l'insieme dei limiti delle sue sottosuccessioni.

Nell'esempio precedente tale insieme sarebbe $\{ -1,1 \}$.

**Def:** $(X,\tau)$ si dice **compatto** se da ogni successione $x_{n}$ è possibile estrarre una sottosuccessione convergente.

**Def:**: $Y\subseteq X$ si dice compatto se è compatto rispetto alla topologia indotta, cioè se ogni successione in $Y$ contiene una sottosuccessione convergente ad un esempio in $Y$.

**Esempio:** $\mathbb{R}$ non è compatto perchè $x_{n}=n$ non contiene sottosuccessioni convergenti.
Ulteriormente $Y\subseteq \mathbb{R}$ è compatto $\iff$ è chiuso e limitato. (Come in analisi).
La sfera è compatta perchè chiusa in quanto controimmagine di un unico punto (che è un insieme chiuso) di una funzione continua. Inoltre la sfera è ovviamente limitata. (Questo stesso ragionamento si può estendere localmente su tutte le superfici)

Per concludere possiamo dire che:
- Spazi topologici compatti esistono in abbondanza
- garantiscono l'esistenza di limiti (di sottosuccessioni)
- importanti per il seguente teorema: se $(X,\tau)$ è compatto e $f:X\to \mathbb{R}$ è continua, allora $f$ ha punti di massimo e di minimo. (Teorema di Weierstrass)

Volendo è possibile anche dimostrare che:
- ogni sottoinsieme chiuso di uno spazio compatto è compatto
- Se $(X,\tau)$ è Hausdorff e soddisfa il primo assioma allora ogni compatto è chiuso.


## Domande per revisione
- [ ] ESERCIZIO: dimostrare che $f:(\mathbb{R}^n, \tau_{std})\to(\mathbb{R}^n, \tau_{std})$ è continua nel senso topologico se e solo se è continua nel senso degli $\varepsilon$ e dei $\delta$ in ogni punto.

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

