

$$
	\nabla_{\varphi_{*}(\partial_{i})}\varphi_{*}(\partial_{j}) \quad \text{ è un campo vettoriale definito localmente su } V \subseteq M
$$
Tale campo dipende dalla derizione $\varphi_{*}(\partial_{i})$ lungo la quale derivo.
Essendo un campo vettoriale, è una combinazione lineare di $\varphi_{*}(\partial_{k})$.
I coefficienti sono $\Gamma^k_{ij}$, simboli di Christoffel, che sono funzioni sulla carta $V\subseteq M$.
$$
	\nabla_{\varphi_{*}(\partial_{i})} \varphi_{*}(\partial_{j})=\sum_{k} \Gamma_{ij}^k \varphi_{*}(\partial_{k})
$$
Conoscendo i simboli di Christoffel conosciamo tutto $\nabla$. Supponiamo di voler calcolare:
$$
	\nabla_{X}Y=\text{?}
$$
Sappiamo che:
$$
	X=\sum x_{i}(x)\varphi_{*}(\partial_{i})\qquad Y=\sum y_{j}(x)\varphi_{*}(\partial_{j})\qquad 
$$
Possiamo calcolare $\nabla_{X}Y$ usando Leibnitz:
$$
	\begin{aligned}
	\nabla_{X}Y= \sum_{i,j} \nabla_{x_{i}\varphi_{*}(\partial_{i})}y_{j}\varphi_{*}(\partial_{j})=\underbrace{\sum_{i,j} x_{i}(x)[dy_{j}(\varphi_{*}(\partial_i))\cdot \varphi_{*}(\partial_{j})}_{\text{derivata tradizionale}}+y_{j}\nabla_{\varphi_{*}(\partial_{i})}\varphi_{*}(\partial_{j})]
	\end{aligned}
$$
Ci siamo ricondotti alla derivata tradizionale con un termine correttivo aggiuntivo, dato da $\nabla_{\varphi_{*}(\partial_{i})}=\Gamma^k_{ij}$, cioè dai simboli di Christoffel, verificando l'ipotesi che la conoscenza dei simboli di Christoffel (e dei campi) sia sufficiente a calcolare la connessione tra i 2 campi.

$\nabla$ ha come scopo (primario?) quello di poter definire l'accelerezione di una curva su $M$.
$$
	\alpha:(a,b)\to M
$$
La velocità (in $t=0$) è facile:
$$
	\dot{\alpha}(0)=d_{\alpha}|_{_{0}}(1)\quad \text{"}=\frac{d}{dt} \alpha(t)\text{"}
$$
con $1$ intendo il vettore unitario in $T_{0}\mathbb{R}$, la mappa $d\alpha$ è:
$$
	d\alpha: T_{0}\mathbb{R}\to T_{\alpha(0)}M
$$
Per definitr la derivata di $\dot{\alpha}$ serve una connessione $\nabla$, e l'accelerazione è:
$$
	\nabla_{\dot{\alpha}} \dot{\alpha}
$$
(che è un campo rettilineo lungo $\alpha$).

Ora scrivere $F=ma$ acquista senso. $F$ è un campo vettoriale tTANGENTE a $M$, definendo $a$ tramite una connessione, anche $a$ diventa un campo su $M$.

In generale su $M$ esistono infinite connessioni (e con esse infinite nozioni di accelereazione), tuttavia di solito modelli fisici includono una metrica su $M$:
$$
	g\text{ sezione di } T^*M \otimes T^*M \text{ simmetrica e definita positiva in ogni punto}
$$
**Prop:** $g$ induce una $\nabla$ naturale, con 2 proprietà aggiuntive, e solitamente usiamo questa (connessione di Levi-Civita).

Ulteriormente, le connessioni servono a definire le geodetiche e la curvatura di $M$.

#### Geodetiche

>[!abstract] Definizione di Geodetica
>Una geodetica su $M$ (rispetto a una certa connessione $\nabla$) è una curva parametrizzata $\alpha$:
>$$
>	\nabla_{\dot{\alpha}}\dot{\alpha}=0
>$$
>Si tratta dunque dei moti inerziali su $M$

Si tratta di un'equazione differenziale di secondo grado.
Localmente troviamo:
$$
	\dot{\alpha}=\alpha_{i}\varphi_{*}(\partial_{i})
$$
$$
	\nabla_{\dot{\alpha}}\dot{\alpha}=a_{i}a_{j}\nabla_{\varphi_{*}(\partial_{i})}\varphi_{*}(\partial_{j})+da_{j}(\varphi_{*}(\partial_{i}))\, a_{j}\varphi_{*}(\partial_{j})
$$
$$
	\implies \nabla_{\dot{\alpha}}\dot{\alpha}\equiv 0
$$
è proprio un sistema di equazioni differenziali del II ordine.
Date delle condizioni iniziali, sappiamo esistere una sola soluzione a tale equazione.
Cioè $\forall p\in M$, $\forall v=\dot{\alpha}(0)\in T_{p}M$ $\exists!$ moto inerziale $\alpha(t)$ con quei dati iniziali.

Più in generale, dato un campo vettoriale $X$ lungo $\alpha \subseteq M$, diciamo che $X$ è "parallelo" se $\nabla_{\dot{\alpha}}X=0$.
(Quello che ci sta dicendo tale formula è che lungo la curva il campo non cambia e resta sempre parallelo a se stesso).
Per quello che abbiamo detto prima, dati iniziali ci danno un unico campo parallelo.
La nozione di campo parallelo ci spiega come funziona l'intera connessione.

Per definire derivate (nel senso di rapporti incrementali) dobbiamo raccordare spazi tangenti diversi.
Ad esempio, vogliamo definire 
$$
\nabla_V X=\nabla_{\dot{\alpha}(0)}X
$$
a questo punto uso una base parallela lungo $\alpha$, cioè:
$$
	\begin{cases}
	\nabla_{\dot{\alpha}}e_{1}=0 \\
	\nabla_{\dot{\alpha}}e_{2}=0
	\end{cases}
$$
e ottengo:
$$
\begin{aligned}
	\nabla_{\dot{\alpha}}X&=\nabla_{\dot{\alpha}}(x^1e_{1}+x^2e_{2})=\nabla_{\dot{\alpha}}x^1e_{1}+\nabla_{\dot{\alpha}}x^2e_{2}= \\
&=dx^1(\dot{\alpha})e_{1}+\cancel{x^1\nabla_{\dot{\alpha}}e_{1}}+dx^2(\dot{\alpha})e_{2}+\cancel{x^2\nabla_{\dot{\alpha}}e_{2}}
\end{aligned}
$$
In sostanza $\nabla$ ha prodotto una base lungo $\alpha$ che permette un'identificazione tra gli spazi tangenti (lungo $\alpha$) $\implies$ $\nabla_{\dot{\alpha}}X$ è uguale alle derivate delle coordinate di $X$.


### Geometria Riemanniana

Ci occupiamo di Varietà Riemanniane, cioè varietà astratte dotate di un profotto scalare. Tale prodotto scalare sarà dato da una metrica $g_{|p}$ su ogni $T_{p}M$.

**OSS:** la metrica di minkowski non è definita positiva! Noi non ci occupiamo di Varietà di questo tipo.

Cosa possiamo fare con varietà Riemanniane?
1. Possiamo calcolare la lunghezza di $\alpha$:
$$
	L(\alpha)=\int_{a}^b \lVert \dot{\alpha}(t) \rVert dt 
$$
Questo ci permette anche di definire la distanza fra 2 punti.
$$
	d(p,q):= \underset{\alpha}{\text{inf}}\,L(\alpha)
$$
Perchè inf e non min?
Perchè il concetto di inf è più flessibile, va per approssimazioni successive anzichè cercare subito il valore minimo.

Per questo motivo varietà riemanniane sono spazi metrici. Per questo motivo è possibile parlare di successioni di cauchy e conseguentemente anche di criteri di convergenza.

**Oss:** $M$ era già uno spazio topologico, ora è uno spazio metrico. Sappiamo che spazi metrici sono dotati di una topologia naturale. Per fortuma le due topologie coincidono.

**Altra oss:** la sfera ha 2 distanze, una indotta da $\mathbb{R}^3$ che sfonda la sfera e unisce i punti tramite segmenti e una indotta dal suo prodotto scalare.
In teoria entrambe mi danno successioni di Cauchy. Per la sfera risulta che una successione di cauchy lo è per una distanza $\iff$ lo è anche per l'altra. Cioè le due distanze inducono le stesse successioni di Cauchy

Facciamo un esempio ulteriore, quello di un cilindro meno una retta. Considero una $x_{n}$ che saltella tra i due lati della retta, avvicinandosi progressivamente alla retta.
In questo caso per la distanza indotta da $\mathbb{R}^3$ questi punti stanno convergendo e abbiamo una successione di Cauchy.
Con la distanza indotta dalla metrica devo invece fare sempre il giro attorno al cilindro e non ho una successione di Cauchy.

**Prop:** se una superficie in $S\subseteq \mathbb{R}^3$ è un insieme chiuso, allora le successioni di Cauchy per le 2 distanze coincidono.
(Sappiamo infatti che un sottoinsieme chiuso di un insieme completo (in questo caso di $\mathbb{R}^3$) è a sua volta completo).

