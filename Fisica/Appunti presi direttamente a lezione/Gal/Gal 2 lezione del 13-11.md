
Come derivo un Tensore? Iniziamo da un campo vettoriale.

Cosa vogliamo imitare? Vorremmo imitare il tipo di derivazione che incontriamo per le funzioni: $f:M\to \mathbb{R}$
$$
	df_{p}(X)=\frac{d}{dt} (f \circ \alpha)(t)
$$
Cosa ha di speciale una derivazione di questo tipo?
- è $\mathbb{R}$-lineare rispetto a $X$.
- L'oggetto finale:
$$
	p\to df_{p}(X)\quad \text{ è una nuova funzione}
$$
- $d(f\cdot g)_{p}(X)=f_{p}\cdot dg_{p}(X)+df_{p}(X)\cdot g_{p}$, regola di Leibnitz
- $df(gX)=g \,df(X)$ con $g$ fattore moltiplicativo, indipendentemente dal fatto che $g$ sia costante o meno.
cioè $g$ si comporta come scalare se lo metto con $X$ e si comporta secondo la regola di Leibnitz quando lo metto nel differenziale.

Prendiamo ora $Z$ campo vettoriale generico. Per derivarlo, in astratto, ci serve:
$$
\begin{aligned}
	\nabla: \text{campi vettoriali} \overset{\mathbb{R}\text{-lineare}}{\longrightarrow}& \text{sezione di } T^*M\otimes TM \\
	Z \longrightarrow& \nabla Z\in T^{1,1}\\
	&\nabla_{X}Z \; \text{è un campo vettoriale}
\end{aligned}
$$
Vogliamo che un'operazione di questo tipo soddisfi la regola di Leibnitz:
$$
	\nabla_{X} fZ = df(X)\cdot Z+f\cdot \nabla_{X}Z
$$
OSS: se non scrivo la $X$, questa condizione diventa:
$$
	\nabla(fZ)=df\otimes Z+f\cdot \nabla Z
$$
con $df$ 1-forma.

Preso $T\in T^{1,1}=$ sezione di $T^*M\otimes TM$, studiamo cosa succede in alcuni casi:
- $T(X_{1}+X_{2})=T(X_{1})+T(X_{2})$
- $T(\lambda X)=\lambda T(X)$
- $T(fX)=fT(X)$

Dunque per definizione $\nabla_{X} Z$ ha le proprietà richieste sispetto a $X$ (cioè $\nabla_{fX}Z=f\cdot \nabla_{X}Z$ ecc...), perchè sono proprietà che ha qualunque tensore.
Una CONNESSIONE su $TM$ è una mappa del tipo appena discusso.

Come posso ottenere un'operazione di questo tipo?
I casi più naturali sono:
- $S \subseteq \mathbb{R}^3$, lo vedremo tra poco
- $(M,g)$, varietà differenziabile + prodotto scalare $\to$ connessione di Levi-Civita
In realtà è possibile dimostrare che su qualunque varietà esiste un'infinità di connessioni, questo è profondamente legato alle Teorie di Gauge.

A questo punto è lecito chiedersi, $\mathcal{L}$ è una connessione? Cioè, $\mathcal{L}_{X}Z$ ha le proprietà richieste?
No, perchè $\mathcal{L}_{fX}Z\neq f\cdot \mathcal{L}_{X}Z$, perchè contiene derivate di $fX$, che sono:
$$
	df\cdot X+f\nabla X
$$
Non va bene perchè contiene esplicitamente sia $X$ che le derivate di $X$.

Perchè vogliamo così tanto derivare campi vettoriali? Studiamolo mediante un esempio.
Immaginiamo di voler studiare moti vincolati: $\alpha(t)\subseteq M$.
Sappiamo che le velocità sono $\frac{d}{dt} \alpha(t)\in T_{p}M$.
Immaginiamo ora di voler studiare $F=ma$. $a=\dot{\alpha}$ è la derivata di un campo vettoriale!

POV locale (aka come fare i conti)

ho $M$ varietà differenziabile, cioè uno spazio topologico "modellato" su $\mathbb{R}^n$.
$$
	M=\cup V_{i}\; \text{aperti}
$$
Su di una sfera, posso vedere $V_{1}$ e $V_{2}$ calotte superiori e inferiori. Non bastano perchè essendo aperti escludono l'operatore. Allora prendo $V_{3}$ e $V_{4}$ calotte destra e sinistra. Ma sto comunque escludendo 2 punti, "l'intersezione dei tagli". Dunque devo prendere anche $V_{5}$ e $V_{6}$, callotta frontale e posteriore.
**Oss:** Ogni calotta è modellata su un aperto di $\mathbb{R}^2$, perchè è il grafico di una funzione a 2 variabili: $z=\sqrt{ 1-x^2-y^2 }$.
$$
	\text{Grafico}:(x,y)\to(x,y,\sqrt{ 1-x^2-y^2 }) 
$$
Una mappa manda dischi in calotte ed è un omeomofrgismo.
Chiamo i dischi $U_{i}$, le calotte $V_{i}$ e gli omeomorfismi $\varphi_{i}$. L'atlante della sfera è l'insieme di questi elementi.
$$
	S^2 = \{ U_{i}, V_{i}, \varphi_{i} \}
$$
**Definizione:** una varietà è uno spazio topologico tale che esista un ricoprimento $\{ U_{i}\subseteq \mathbb{R}^n, V_{i}\subseteq M, \varphi_{i}:U_{i}\to V_{i} \}$. che chiamiamo atlante.

Dobbiamo ancora distinguere tra varietà topologica e differenziale.
Varietà topologica è uno spazio topologico che soddisfa il secondo assioma di numerabilità ed è Hausdorf, modellato su $\mathbb{R}^n$, cioè esiste un atlante.
Per varietà differenziabili richiedo anche che le carte siano tra loro compatibili, ossia:
$$
	d\varphi_{j}^{-1}\circ d\varphi_{i}:U_{i}\to V_{i}
$$
sia un diffeomorfismo.

Come si inserisce $\nabla$ in questo framework locale (dentro una carta)?
$$
	\forall \varphi_{i}\text{ genera una base per } T_{p}M, \; p\in V_{i}
$$
$$
	d\varphi_{x}(e_{1})\in T_{p}M \dots d\varphi_x(e_{n})
$$
Achtung: $d\varphi_{x}(e_{i})$ sono vettori parametrizzati in $TM$, parametrizzati da punti $x\in U_{i}\subseteq\mathbb{R}^n\implies$ non sono campi vettoriali su $M$. Per ottenere una base formata da campi vettoriali devo usare il push-forward $\varphi_{i}(e_{i})$.
$\varphi_{i}(e_{i})|_{\varphi_{i}(X)}=d\varphi_{i}|_{X}(e_{i})$. Ossia:
$$
	\varphi_{i}(X)=d\varphi(X)\circ \varphi^{-1} \qquad \varphi(X)=\varphi_{i}(X)\circ\varphi
$$
Ossia, l'operazione $d\varphi_{i}$ è utile per spostare avanti singoli vettori, ma non sposta i punti che li parametrizzano. L'operazione push-forward corregge, spostandoli entrambi.

Per calcolare $\nabla_{X}Z$ nei punti $p\in V_{i}$, dico che:
$$
	Z=\sum a_{k}(p) \varphi_{i}(e_{k})
$$
$$
	X=\sum b_{j}(p)\varphi_{i}(e_{j})
$$
Ora uso le proprietà di $\nabla_{X}Z$:
$$
	\begin{aligned}
	\nabla_{X}Z&=\nabla_{\sum b_{j}\varphi_{i}(e_{j})} \sum a_{k}\varphi_{i}(e_{k})=\sum_{k,j}b_{j}\nabla_{\varphi_{i}(e_{j})}a_{k}\varphi_{i}(e_{k})=\\
	&=\sum_{k,j} [b_{j}a_{k}\nabla_{\varphi_{i}(e_{j})}\varphi_{i}(e_{k})+b_{j}da_{k}(\varphi_{i}(e_{j}))\circ \varphi_{i}(e_{k})]
	\end{aligned}
$$
Dunque la scelta di $\nabla$ corrisponde alla scelta di $\nabla_{\varphi_{i}(e_{j})}\varphi_{i}(e_{k})=\Gamma^l_{jk}\varphi_{i}(e_{l})$.
$$
	\Gamma^l_{jk}=\text{simboli di Christoffel}
$$











