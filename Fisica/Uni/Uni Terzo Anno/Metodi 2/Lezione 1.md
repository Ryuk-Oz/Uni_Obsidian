---
corso: Metodi 2
data: 2026-09-21
tags:
  - lezione
argomenti: []
lezione-precedente:
source:
---


> [!info] Contesto
> Corso: Metodi 2
> Argomenti previsti: Funzioni Analitiche, Mappi Conformi, Continuità Analitica


## Riassunto veloce

Siamo andati a studiare funzioni analitiche nei punti in cui hanno deribvata non nulla. In questi punti abbiamo visto come le funzioni agiscano da mappe locali che operano una dilatazione e una rotazione del piano di partenza, andando a conservare gli angoli formati tra le curve nel piano di partenza e di arrivo. Abbiamo definito trasformazioni di questo tipo mappe conformi.

In seguito abbiampo studiato come nei punti in cui la derivata prima si annulla (o si annullano in generale le prime $n-1$ derivate) cada la condizione di conservazione dell'angolo e le mappe smettono di essere dunque conformi.

A questo punto ci siamo concentrati sullo studio di alcune funzioni analitiche come esponenziali e potenze e abbiamo trovato che spesso il paino di partenza viene mappato nel prodotto cartesiano di più piani, rendendo queste funzioni non invertibili globalemente. Abbiamo però mostrato come sfruttando l'analiticità si possa definire un inversa locale.

Infine abbiamp introdotto un teorema utile allo studio della continuazione analitica: una funzione analitica definita su un dominio connesso $D$ in cui sia presente un punto di accumulazione di 0 è ugualmente nulla su tutto il dominio $D$.

## Appunti

Partiamo dalle funzioni analitiche per andare a studiare le proprietà delle mappe conformi
### Mappe conformi

Considero $f(z)$ analitica in $D \subset \mathbb{C}$. Definisco $w \equiv f(z)$ e definisco così una corrispondenza tra un piano $z$ e un piano $w$.

![[Metdodi2_1_1.png|700]]

$f(z)$ è una mappa $z\to w$, poichè $f$ è analitica, cioè continua e derivabile, essa mappa anche curve in curve e regioni di spazio in altre regioni di spazio:
$$
	\begin{aligned}
	f&: \gamma(z) \to \gamma(w) \\
	f&: D \subset \mathbb{C}_{z} \to E \subset\mathbb{C}_{w} \\
	f&: \partial D \to \partial E
	\end{aligned}
$$

Ricordiamo ora la definizione di derivabilità in ambito complesso: $f$ è derivabile se:
$$
	\lim_{ z \to z_{0} } \frac{f(z_{0}+\delta z)-f(z_{0})}{\delta z} \equiv \lambda(z_{0}) 
$$
Consideriamo a questo punto un punto $z_{0} \quad \text{t.c.}\quad \frac{df}{dz}|_{z_{0}}=\lambda(z_{0})\neq 0$, allora:
$$
	z=z_{0}+\delta z \to w = w_{0}+\delta w = f(z_{0}+\delta z)=f(z_{0})+\frac{df}{dz}|_{z_{0}}\delta z +\frac{1}{2} \frac{d^2f}{dz^2}|_{z_{0}}(\delta z)^2+\dots
$$
cioè:
$$
	\delta w=\lambda(z_{0})\delta z
$$
Questo significa che localmente $f$ opera una **dilatazione** e una **rotazione**, infatti:
$$
	\begin{aligned}
	|\delta w|&=|\lambda(z_{0})||\delta z| \quad (\text{che riscala}) \\
	arg(\delta w)&=arg(\lambda(z_{0}))+arg(\delta z) \quad (\text{che ruota})
	\end{aligned}
$$
dunque, se io considero due diverse variazioni $\delta z_{1}$ e $\delta z_{2}$:
$$
	\begin{aligned}
	arg(\delta w_{1})&=arg(\lambda(z_{0}))+arg(\delta z_{1})\\
	arg(\delta w_{2})&=arg(\lambda(z_{0}))+arg(\delta z_{2})\\
	\end{aligned}
$$
e dunque:
$$
	arg(\delta w_{2})-arg(\delta w_{1})=arg(\delta z_{2})-arg(\delta z_{1})
$$
cioè nei punti in cui la derivata di $f$ è non nulla, questa forma una **mappa conforme** (cioè una mappa che conseva gli angoli).

![[Metodi2_1_2.png|700]]

- Facciamo un esempio:
$w=f(z)=z^2$ analitica in $\mathbb{C}$
$f'(z)=2z$ che è non nulla $\forall z \neq 0$, allora scelgo $z_{0}\neq{0}$ e ho:
$$
	\begin{aligned}
	dw&=2z_{0}dz\\
	|dw|&=2|z_{0}||dz|\\
	arg(dw)&=arg(z_{0})+arg(dz)
	\end{aligned}
$$
Se $\frac{df}{dz}|_{z_{0}}=0$ allora continuo lo sviluppo all'ordine successivo e:
$$
	w=w_{0}+\delta w=f(z_{0})+\frac{1}{2} \frac{d^2f}{dz^2}|_{z_{0}}(\delta z)^2
$$
In questo caso l'argomento non viene più conservato (la mappa smette di essere conforme):
$$
	arg(\delta w)=arg\left( \frac{d^2f}{dz^2}|_{z_{0}} \right)+2arg(\delta z)
$$
Prendendo nuovamente due diverse variazioni abbiamo:
$$
	arg(\delta w_{1})-arg(\delta w_{2})=2(arg(\delta z_{1})-arg(\delta z_{2}))
$$
L'esempio appena fatto in $z_{0}=0$ si traduce dunque in qualcosa di questo tipo:

![[Metodi2_1_3.png]]

In generale, laddove si annullimo i primi $n-1$ termini dello sviluppo, abbiamo:
$$
	w=w_{0}+\delta w=f(z_{0})+\frac{1}{n!} \frac{d^nf}{dz^n}|_{z_{0}}(\delta z)^n
$$

Studiamo adesso tutte le funzioni analitiche note:

- $w=f(z)=z$ analitica in tutto $\mathbb{C}$
$f'(z)=1 \; \forall \; z$ dunque la mappa è conforme in tutto il piano complesso ed opera come la trasformazione identica: $f: \mathbb{C}_{z} \to \mathbb{C}_{w}$.

- $w=f(z)=az$, come prima è analitica e conforme su tutto il piano complesso ma questa volta va ad operare una rotazione ed una dilatazione globale

- $w=f(z)=az+b$, in questo caso alla dilatazione alla rotazione aggiungiamo una traslazione
Queste 3 sono le uniche trasformazioni $\mathbb{C}\to\mathbb{C}$ globalmente invertibili, $z=\frac{1}{a}(w-b)$

- $f(z)=z^2$, analitica in $\mathbb{C}$, conforme in $\mathbb{C}-\{0\}$

![[Metodi2_1_4.png]]

Tutti i punti che appartengono al settore circolare coperto da $\phi$ nel piano di $z$ sono mappati al settore circolare corrispondente nel piano $w$, coperto da $2\phi$.
Dunque il semipiano superiore in $z$ viene mappato nell'intero piano in $w$.
$$
	\begin{aligned}
	f: H|_{\perp}&\to \mathbb{C}_{w} \\
	\mathbb{C}_{z}&\to \mathbb{C}_{w} \times \mathbb{C}_{w}
	\end{aligned}
$$
Andando a generalizzare a $f(z)=z^n$ ho:
$$
	\begin{aligned}
	f: S_{\frac{2\pi}{n}}&\to \mathbb{C}_{w}\\
	\mathbb{C}_{z}&\to\mathbb{C}_{w}^n
	\end{aligned}
$$
Ovviamente mappe di questo tipo smettono di essere globalmente invertibili

- funzione esponenziale: $w=f(z)=e^z=e^x+e^iy$
![[Metodi2_1_5.png |pos-r|565]]

$\forall$ striscia di ampiezza $2\pi$ in $\mathbb{C}_{z}$ viene mappata in $\mathbb{C}_{w}$:
$$
	\begin{aligned}
	f: L_{2\pi}^z&\to\mathbb{C}_{w}\\
	\mathbb{C}_{z}&\to\mathbb{C}_{w}^\infty
	\end{aligned}
$$
Anche questa non è globalmente invertibile.

Nonostante queste funzioni non siano globalmente invertibili, posso sfruttare l'analiticità per andare a definire un inversa locale.
Considero $w_{0}=e^{i\pi/4}$ e suppongo di sapere che questa viene da $z_{0}=i \frac{\pi}{4}$. Se mi sposto "poco" so di dover restare in un intorno di $z_{0}$ e posso andare a definire localmente l'inversa.

Se andassimo a considerare il piano complesso esteso per mezzo del punto all'infinito, otterremmo che per il piano compattificato, le uniche trasformazioni $\bar{\mathbb{C}}_{z}\to \bar{\mathbb{C}}_{w}$ che coprono $\bar{\mathbb{C}}_{w}$ tutto e una volta solo saranno le trasformazioni della forma:
$$
	f(z)=\frac{az+b}{cz+d}
$$
(lo vedremo meglio nelle esercitazioni con Maccaferri).

### Precisazioni sulle continuazioni analitiche (continua nella seconda lezione)

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




## Domande per revisione
- [ ] Come emerge il concetto di mappa conforme dalle funzioni analitiche?
- [ ] Quando una funzione analitica smette di descrivere mappe conformi?
- [ ] Qual è il problema di molte funzioni analitiche quando vado a cercarne l'inversa?

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

