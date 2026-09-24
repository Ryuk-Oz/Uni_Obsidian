---
corso: GAL 2
data: 2026-09-24
tags:
  - lezione
argomenti: []
lezione-precedente:
source:
---


> [!info] Contesto
> Corso: GAL 2
> Argomenti previsti: Curve e superfici nello spazio

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

## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

