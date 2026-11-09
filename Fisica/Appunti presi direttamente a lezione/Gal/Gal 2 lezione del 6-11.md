
Riepilogo degli ultimi episodi:

In una galassia lontana lontana: 
$$
	\underbrace{\mathcal{X}(M)}_{\text{spazio vettoriale, algebra di Lie}} \overset{\text{flusso (mappa exp)}}{\longrightarrow} \underbrace{\text{Diff}(M)}_{\text{varietà, gruppo di Lie}}
$$
$\mathcal{X}(M)=$ insieme dei campi vettoriali
Diff$(M)=$ insieme di tutte le simmetrie possibili a seconda della struttura su $M$.

Cose nuove:

Oggi ci occupiamo dello studio delle 1-forme, per poi spostarci sullo studio dei tensori.
Per farlo, seguiamo le traccie di quanto fatto sul fibrato tangente per i campi vettoriali, ma lo facciamo su di un nuovo spazio, $T^*M$, fibrato cotangente.
>[!abstract] Fibrato Cotangente
>
>$$
>	T^*M = \text{insieme dei vettori cotangenti} = \underset{p\in M}{\cup} T_{p}^*M
>$$

Ha una topologia naturale, e di conseguenza un atlante $C^\infty$ ed è una varietà. (Sulle dispense questa topologia viene costruita passo passo).
Per il momento la forniamo direttamente.
Parto dall'altlante di M:
$$
	\{ U_{i}\subseteq \mathbb{R}^{n},\; V_{i} \subseteq M,\; \varphi_{i}: U_{i}\to V_{i}\}
$$
Ricordo l'atlante di $TM$:
$$
	U_{i}\times \mathbb{R}^{n}, \; TV_{i}=\{ \text{vettori nei punti di } V_{i} \} ,\; \Phi_{i}:(x,\underbrace{v\in \mathbb{R}^n}_{D_{v}})\to(\varphi_{i}(x), d\varphi_{i}|_{x}(D_{v}))
$$
Ora possiamo intuire la struttura dell'atlante di $T^*M$:
$$
	U_{i}\times(\mathbb{R}^n)^*,\; T^*V_{i}=\{ \text{vettori in } T^*_{p}M,\, p \in V_{i} \}, \; \Psi_{i}:(x,\alpha)\to(\varphi_{i}(x), \dots\in T^*_{\varphi_{i}(x)}M)
$$
Dobbiamo capire quale sia l'operazione nei $\dots$ Possiamo farlo semplicemente dualizzando:
$$
	d\varphi_{i}: T_{x}U_{i}\to T_{\varphi_{i}(x)}M
$$
$$
	d\varphi_{i}^*: T^*_{\varphi_{i}(x)}M\to T^*_{x}U_{i}
$$
Ma voglio che i miei elementi siano in $T^*_{\varphi_{i}(x)}M$, allora torno semplicemente indietro con la mappa inversa:
$$
	\dots = (d\varphi_{i})^{-1}|_{x}(\alpha)
$$
Da qua si capisce subito che la dimensione di $T^*M$ è $2n$.

A questo punto emerge in maniera naturale la seguente definizione:
>[!abstract] 1-forme differenziali
>Una 1-forma su $M$ è una sezione di $T^*M$:
>
>$$
>	\alpha: M\to T^*M, \qquad C^\infty 
>$$
>tale che $p\to \alpha(p)\in T_{p}^*M$

Esempio: preso $M=\mathbb{R}^n$, con la base standard una 1-forma è:
$$
	\alpha(x)=a_{1}(x)dx^1+\dots +a_{n}(x)dx^n
$$
con:
$$
	\begin{aligned}
	dx^1: T_{x}\mathbb{R}^n &\to \mathbb{R} \\
	e_{1}&\to 1\\
	e_{2} &\to{0}\\
	\text{ecc}&\dots
	\end{aligned}
$$
Attenzione! $\mathbb{R}^n$ è dotato di una base canonica quindi posso identificarlo con il proprio duale e sostanzialmente cambia poco tra spazi tangenti e cotangenti, ma in generale non è così.

A cosa mi servono le 1-forme differenziali?
Lo scopo principale delle 1-forme è quello di permetterci di integrare funzioni lungo curve.
Riprendiamo un problema che abbiamo già affrontato:
Presa una curva $\gamma:(a,b)\to M$, non posso calcolare l'integrale di una funzione 
$f:M\to \mathbb{R}$ lungo $\gamma$ nel seguente modo:
$$
	\int_{\gamma} f = \cancel{\int^a_{b} f(\gamma)\, dt} \in \mathbb{R} \quad \text{perchè dipende dalla parametrizzazione}
$$

La definizione di integrale richiede la scelta di una 1-forma $\alpha$ su $M$ che lo renda indipendente dalla parametrizzazione di $\gamma$.
$$
	\int_{\gamma} f\, \alpha = \int_{a}^b (f\circ\gamma)\alpha(\dot{\gamma})\; dt
$$
Esempio:
$f:M\to \mathbb{R}$, $df: T_{p}M\to T_{f(p)}\mathbb{R}=\mathbb{R}$.
$df \in T_{p}^*M$ è una 1-forma speciale (esatta), una 1-forma si dice esatta quando rappresenta un differenziale.

Perchè ci interessano 1-forme esatte? L'integrazione di 1-forme esatte ci da il TFCI:
$$
	\int_{\gamma} df = \int^b_{a} df(\dot{\gamma}) dt = \int^b_{a} \frac{d}{dt} (f \circ\gamma)(t) dt = (f\circ\gamma)(b)-(f\circ\gamma)(a)
$$
In analisi complessa:
$$
	\int_{\gamma} fdz = \int \text{1-forma } \alpha \quad \text{con } \alpha=fdz 
$$
tipicamente $fdz$ non è esatta, perchè $f$ può avere dei poli nel dominio di integrazione.
Però $fdz$ è una 1-forma chiusa se $f$ è olomorfa.
Una 1-forma è chiusa se il suo differenziale è nullo.

Prendo $\varphi\in \text{Diff}(M)$ e $\alpha$ 1-forma.
Posso definire una nuova 1-forma nel seguente modo:
$$
	\varphi^* \alpha \quad \text{1-forma "pullback"}
$$
$$
	\varphi^* \alpha|_{p} (v\in T_{p}M) := \alpha|_{\varphi(p)}(d\varphi|_{p}(v) \in T_{\varphi(p)}M)
$$
Con questa nozione posso calcolare la derivata di Lie di $\alpha$ rispetto a un campo $X$ nel seguente modo:
$$
	\mathcal{L}_{X} \alpha = \frac{d}{dt} \varphi^*_{t}\alpha|_{p;t=0} = \lim_{ t \to 0 } \frac{\varphi^*_{t}\alpha|_{p}-\varphi^*_{0}\alpha|_{p}}{t}
$$
Calcola come varia $\alpha$ rispetto ai diffeomorfismi $\varphi_{t}$, ossia rispetto ai campi $X$.
$$
	\mathcal{L}_{X}\alpha=0
$$
significa che $\alpha$ non varia rispetto a $\varphi_{t}$, ossia $\varphi_{t}$ preservano $\alpha$.
$$
	\varphi_{t}^*(\alpha)\equiv \alpha
$$
Ossia, i flussi $\varphi_{t}$ sono le simmetrie di $\alpha$.


### Algebra Tensoriale

$$
	V \otimes W \equiv \text{prodotto tensoriale tra } V \text{e } W
$$
$$
	V\otimes W:=\{ \text{forme bilineari su } V^*\times W^*\to \mathbb{R}, \quad (\alpha,\beta)\to\in \mathbb{R}\}
$$
Molto spesso:
$$
	V^* \otimes W^* = \{ \text{forme bilineari su } \underbrace{V^{**}\times W^{**}}_{V\times W}\to \mathbb{R}, \quad (v,w)\to\in \mathbb{R} \}
$$
Esempio:
Prodotto scalare $\langle , \rangle\in V^*\otimes V^*$ perchè forma bilineare su $V\times V\to \mathbb{R}$.
**Oss:**
Consideriamo la mappa (che associa ad ogni 2 vettori il loro prodotto tensoriale):
$$
	V\times W\underset{\text{bilineare}}{\to} V\otimes W
$$
$$
	(v,w)\to v\otimes w, \text{forma bilineare } V^*\times W^*\to \mathbb{R}
$$
$$
	v\otimes w\;(\alpha,\beta)=\alpha(v)\beta(w) \in \mathbb{R}
$$
In particolare, l'immagine di una mappa di questo tipo NON è un sottospazio vettoriale, però è un sottoinsieme che genera tutto $V\otimes W$.
In particolare: 
$$
	B=\{ e_{i} \}\quad e=\{ f_{j} \}\qquad e_{i}\otimes f_{j}\in V\otimes W
$$
Dunque, qualunque elemento di $V\otimes W$ si può scrivere come:
$$
	\sum a_{ij}\, e_{i}\otimes f_{j}
$$
Ulteriore esempio:
$$
	V^* \otimes W = \text{Hom}(V,W)
$$
In che senso? Tramite un identificazione $v^* \otimes w\;(v')=\underbrace{v^*(v')}_{\mathbb{R}}\cdot w$. Dunque è una mappa lineare che manda vettori di $V$ in vettori di $W$ (omomorfismo).

Riassunto: everything is a Tensor





