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
> Argomenti previsti: 

## Riassunto veloce



## Appunti

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
&=\frac{d}{dt}(\varphi \circ \alpha)(t)|_{t=0}
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

**Esempi:**
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



## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

