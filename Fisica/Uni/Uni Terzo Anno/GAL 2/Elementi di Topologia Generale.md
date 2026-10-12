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

Occupiamoci ora di una definizione molto importante, quella di continuità:
>[!abstract] Def: funzione continua 
>$$
>	f:(X_{1},\tau_{1})\to(X_{2},\tau_{2})
>$$
>Si dice CONTINUA se $\forall A\in \tau_{2}$, $f^{-1}(A)={ x\in X_{1}:f(x)=A } \in \tau_{1}$

Ovvero $f$ manda aperti in aperti (o chiusi in chiusi).

**OSS:** per dimostrare la continuità basta lavorare con la base di $\tau_{2}$.

**Esempio:** Una funzione da $X_{1}=\mathbb{R}$ in $X_{2}=\mathbb{R}$ con dei salti, come:

![[Pasted image 20261013003141.png]]

è continua con la giusta topologia.
NON SI CAPISCE; CHIEDI A FEDE

Al di là della continuità, esiste una condizione ancora più forte:
>[!abstract] Def: Omeomorfismo
>$f:(X_{1},\tau_{1})\to(X_{2},\tau_{2})$ si dice omeomorfismo se è continua, invertibile con inversa continua.
>Se esiste un omeomorfismo tra 2 spazi topologici, questi 2 spazi sono topologicamente indistinguibili.



## Domande per revisione
- [ ] ESERCIZIO: dimostrare che $f:(\mathbb{R}^n, \tau_{std})\to(\mathbb{R}^n, \tau_{std})$ è continua nel senso topologico se e solo se è continua nel senso degli $\varepsilon$ e dei $\delta$ in ogni punto.

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

