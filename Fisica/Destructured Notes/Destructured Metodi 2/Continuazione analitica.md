
Per prima cosa introduciamo un paio di lemmi e teoremi
________________________________________________________________________
- **Lemma** 
**Hp:** 
$z_{0}\in \mathbb{C}$ punto regolare per $f(z)$
$z_{0}$ punto di accumulazione di zeri per $f(z)$
**Th:**
$f(z)=0 \; \forall \; z \in I_{\delta}(z_{0})$

- **Dimostrazione** (per assurdo)
$f(z)$ regolare allora posso scriverne lo sviluppo di Taylor: $f(z)=\sum_{k=0}^\infty a_{k}(z-z_{0})^k$, la tesi risulta vera se $a_{k}=0\;\forall\;k$.
Per assurdo suppondo $\exists \; n$ t.c $a_{n}\neq_{0} \; a_{k}=0 \; \forall k<n$.
Dunque $f(z)=\sum_{k=n}^\infty a_{k}(z-z_{0})^k=(z-z_{0})^n g(z)$, con $g(z)$ analitica e diversa da 0 in $z=0$.
Andrebbe dunque ad esistere un intorno $I_{\varepsilon}(z_{0})$ t.c. $\forall \; z \in \dot{I_{\varepsilon}}(z_{0})$ abbiamo $(z-z_{0})^n g(z)\neq 0$.
Cioè $z_{0}$ non è un punto di accumulazione di zeri. $\blacksquare$ 

________________________________________________________________________
- **Teorema**
**Hp:**
$f(z)$ regolare in $D \subset \mathbb{C}$, $D$ connesso
$z_{0}$ punto di accumulazione di zeri di $f(z)$
**Th:**
$f(z)=0 \; \forall z \in D$

- **Dimostrazione**
$D$ connesso $\to$ connesso per archi
Per il lemma precedente $\exists$ un intorno $\dot{I}_{\delta}(z_{0})$ in cui $f$ è identicamente nulla. 
Posso gradualmente spostarmi sfruttando intorni centrati in punti $\in \dot{I}_{\delta}(z_{0})$ che saranno a loro volta punti di accumulazione (per definizione).
Procedo così in maniera analoga fino a coprire tutto $D$. $\blacksquare$ 

![[Metodi2_1_6.png|al-c|700]]


________________________________________________________________________
- **Corollario**:
Siano $f_{1}(z) \text{ e } f_{2}(z)$ regolari in $D \subset C$, con $D$ connesso.
Se l'insieme $I=\{ z \in D \, / \, f_{1}(z)=f_{2}(z) \}$ ha un punto di accumulazione in $D$,
allora $f_{1}(z)=f_{2}(z) \, \forall z \in D$.

Il corollario si dimostra come il teorema precedente, scegliendo $f(z)=f_{2}(z)-f_{1}(z)$.

Posso anche fornire una formulazione alternativa del corollario, prendendo $f_{1}(z)$ regolare in $D_{1}$ e $f_{2}(z)$ regolare in $D_{2}$ e scegliendo l'insieme $I=\{ z \in D_{1} \cap D_{2} \, / \, f_{1}(z)=f_{2}(z) \}$. Se $I$ ha un punto di accumulazione in $D_{1} \cap D_{2}$ $\Rightarrow$ $f_{1}(z)=f_{2}(z) \, \forall z \in D_{1} \cap D_{2}$.
___
L'utilità di questo corollario sta nel fatto che mi da un modo univoco di estendere il dominio di $f_{1}(z)$ al di fuori del proprio, tramite una funzione diversa $f_{2}(z)$ che è definita anche altrove. Chiamiamo questa nuova funzione $f_{2}$ la continuazione analitica di $f_{1}$.
Questo ci garantisce che presa una certa rappresentazione locale di $f$ (con Laurant o Taylor ad esempio), analitica in un dominio ristretto rispetto a quello di $f$, il modo in cui possiamo ricostruire la funzione di partenza sia univoco.

- **DEF:**
considero $f_{1}(z)$ definita in $E \subset\mathbb{C}$ (anche il piano esteso è ok) e $f_{2}(z)$ analitica in $D \subset \mathbb{C}$.
$f_{2}(z)$ è la **continuazione analitica** di $f_{1}$ a tutto $D$ se:
1. $f_{1}(z)=f_{2}(z) \, \forall z \in E \cap D$
2. $E \cap D$ ha almeno un punto di accumulazione in $D$. Cioè i due domini si sovrappongono "con continuità" da qualche parte (ad esempio se una funzione è definita in $\mathbb{N}$ e l'altra in $\mathbb{R}$, l'intersezione tra i due non ha punti di accumulazione in $\mathbb{R}$).

L'esempio banale è quello dello sviluppo di taylor di $f_{2}=\frac{1}{1-z}$ attorno a $z=0$.
$$
	f_{1}=\sum^\infty_{k=0}z^k
$$
che converge in $|z|<1$.
$f_{2}(z)=\frac{1}{1-z}$ è la continuazione analitica di $f_{1}$ in $\mathbb{C}-\{ z=1 \}$.

Tra le altre cose, la continuazione analitica è anche il motivo per cui posso sempre estendere una funzione da $\mathbb{R}$ in $\mathbb{C}$.
![[Pasted image 20260925115959.png|404]]

infatti, $E\equiv\mathbb{R}$ ha infiniti punti di accumulazione in $\mathbb{C}$.
All'atto pratico compio questa continuazione analitica sfruttando gli sviluppi di Taylor.
Consideriamo ad esempio la funzione coseno, in $\mathbb{R}$ posso andare a definire il coseno tramite la circonferenza goniometrica, ma questo non è più possibile nel piano complesso, dunque:
$$
	\cos x=\sum^\infty_{k=0} \frac{(-1)^k}{2k!}x^{2k} \to \cos z\equiv \sum^\infty_{k=0} \frac{(-1)^k}{2k!}z^{2k}
$$

Verifichiamo ulteriormente l'unicità della continuazione di $f_{1}(z)$, definita su $E$.
Supponiamo di avere 2 diversi modi di continuarla:
$f_{2}(z)$ in $D$ e $f_{3}(z)$ in $D$, entrambe continuazioni analitiche di $f_{1}(z)$.
Con queste ipotesi otteniamo:
$$
	\begin{aligned}
	f_{1}&=f_{2} \, \forall z \in E \cap D \\
	f_{1}&= f_{3} \, \forall z \in E \cap D \\
	\Rightarrow f_{2}&=f_{3} \, \forall z \in E \cap D
	\end{aligned}
$$
dunque la continuazione analitica di $f_{1}$ è univoca.

Posso trovare un modo di costruire la continuazione analitica per una funzione olonoma qualunque? Iniziamo da un modo pedagogico, che trova però poche applicazioni reali, a causa della lunghezza dei conti.

#### Continuazione analitica alla Weierstrass

L'idea dietro alla continuazione alla Weierstrass è quella degli sviluppi successivi.
Considero $f(z)$ analitica in $D$ $\Rightarrow$ posso svilupparla con Taylor.
$$
	f_{0}(z) = \sum^\infty_{k=0}a_{k}(z-z_{0})^k \, \text{ con } z_{0} \in D
$$
questo sviluppa vale in un intorno di $z_{0}$, $I_{\delta_{0}}(z_{0})$.
Ora prendo $z_{1}$ e ci sviluppo $f_{0}(z)$ attorno.
$$
	f_{1}(z)=\sum^\infty_{a=0} b_{a} (z-z_{1})^a \to I_{\delta_{1}}(z_{1})
$$
e non è detto che $I_{\delta_{1}} \subseteq I_{\delta 0}$
Ripeto con cerchi successivi fino ad arrivare a $z_{n} \in D$.

![[Pasted image 20260925123307.png]]

e:
$$
	f(z)= \begin{cases}
	f_{0}(z) \quad z \in I_{\delta_{0}}(z_{0}) \\ \\
	f_{1}(z)\quad z \in I_{\delta_{1}}(z_{1})
	\end{cases}
	\quad \text{definita in} \quad I_{\delta_{0}}(z_{0})\cup I_{\delta_{1}}(z_{1})
$$

alla fine di tutto ottengo che $f(z)=f_{i}(z)$ per $z \in I_{\delta_{1}}(z_{1})$. Procedendo in questo modo è sempre possibile andare ad aggirare eventuali poli della nostra funzione.

Facciamo un esempio di questo approccio.
Considero $f_{0}(z)=\sum^\infty_{k=0} z^k$ in $I_{1}(0)$.
Scelgo $z_{1}=1$ e sviluppo attorno a $z_{1}$.
$$
	f_{1}=\frac{2}{3} \sum^\infty_{k=0}\left( \frac{2}{3} \right)^k\left( z+\frac{1}{2} \right)^k \, \text{ definita su } I_{\frac{3}{2}}(-\frac{1}{2})
$$
![[Pasted image 20260925124319.png]]

In questo caso conosco direttamente la somma ($f(z)=\frac{1}{1-z}$), che potrei usare per trovare il più grande dominio che posso coprire con l'approccio di Weierstrass, ma non sempre è detto che sia così.

Consideriamo adesso il caso di una funzione definita su di un dominio non connesso.
Per arrivare a $z_{n}$ partendo da $z_{0}$, per sviluppi successivi, posso aggirare la zona "bucata" del dominio e ho più di un cammino possibile.

![[Pasted image 20260928225247.png|527]]

Come posso confrontare i risultati ottenuti passando per 2 percorsi diversi?
L'unicità discussa precedentemente vale solo quando le 2 possibili continuazioni condividono parte del dominio, ma in questo caso ciò chiaramente non succede.
Se non avessi singolarità e andassi a prendere 2 cammini separati, potrei sempre estendere il dominio utilizzato per un cammino sul dominio utilizzato per il secondo cammino (per ottenere $D_{1} \cap D_{2} \neq \emptyset$), usando il teorema di Cauchy. Questo ovviamente non è possibile in presenza di singolarità.

Più avanti nel corso vedremo come nel caso di singolarità isolate riusciremo ad andare a ristabilire l'unicità della continuazione analitica. Per singolarità non isolate, questa sarà invece destinata a cadere.

**Lezione Associata:** [[1.Mappe conformi e Continuazione Analitica]]