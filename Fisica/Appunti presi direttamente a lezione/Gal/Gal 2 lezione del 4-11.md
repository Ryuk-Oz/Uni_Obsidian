
digressione sui diffeomorfismi.
I diffeomorfismi sono mappe $\varphi: M_{1}\to M_{2}$ $C^\infty$, invertibili con inversa $C^\infty$.
In particolare ci interessano diffeomorfismi in se stessi:
$$
	\varphi:M\to M
$$
Cosa fa un diffeomorfismo di questo tipo? "Rimescola i punti in $M$".
Un esempio sono le rotazioni di una sfera.
Le rotazioni sulla sfera sono diffeomorfismi "speciali", si tratta infatti di un'isometria (movimento rigido), un diffeomorfismo che preserva le distanze fra i punti.
$$
	d(p_{1},p_{2})=d(\varphi(p_{1}), \varphi(p_{2}))
$$
Un esempio più generale è una mappa che prende una "chiazza" su di una sfera e "stira" i punti al suo interno lasciando invariati i punti esterni alla chiazza.
"stira" = i punti al centro della chiazza si muovo verso l'esterno più velocemente dei punti esterni alla chiazza.
Dunque i diffeomorfismi possono lasciare ferme alcune zone.
Un altro esempio di diffeomorfismo diverso dai movimenti rigidi è quello di un cilindro la cui metà superiore ruota in una direzione e la metà inferiore ruota nella direzione opposta (intorno all'asse del cilindro).

Questi esempi ci servono per capire che Diff($M$) è $\infty$-dimensionale.
Non solo, i diffeomorfismi formano anche un gruppo rispetto alla composizione:
- $\varphi \circ \psi$ è un diffeomorfismo, $(\varphi \circ \psi)^{-1}= \psi^{-1} \circ \varphi^{-1}$
- Esiste un elemento neutro (la mappa identità) e un elemento inverso (per definizione)
Ulteriormente, i diffeomorfismi hanno una struttura di varietà differenziale infinito dimensionale.

L'insieme di queste 2 condizioni (varietà diff. + struttura di gruppo) è quello che ci darà la definizione di gruppo di Lie (anche se noi lavoreremo principalmente con gruppi finito dimensionali).

Ogni volta che andiamo a definire dei nuovi oggetti, è comodo andare a vedere come si comporta rispetto a dei diffeomorfismi.

Come si comporta un campo vettoriale sotto l'azione di un diffeomorfismo?
Considero un campo vettoriale $X\in \mathcal{X}(M)$ e $\varphi \in \text{Diff}(M)$.
Posso costruire un nuovo campo vettoriale $\varphi(X)$ come segue:
$$
	\varphi(X)_{p}=d\varphi(X|_{\varphi^{-1}(x)})
$$
$$
	d\varphi|_{\varphi^{-1}(p)}: X\in T_{\varphi^{-1}(p)}M\to \varphi(X)_{p}\equiv d\varphi(X)_{\varphi^{-1}(p)} \in T_{p}M
$$
Ossia $\varphi(X)=d\varphi(X)\circ \varphi^{-1}$.
Quest'operazione prende il nome di Push-Forward di $X$.
Perchè mi serve usare la mappa inversa?
$\varphi(X)$ campo vettoriale, allora deve'essere una sezione di $TM$, cioè:
$$
	p\to \varphi(X)|_{p} \in T_{p}M
$$
...MA...
$$
	d\varphi (X): p\to \text{vettore in } T_{\varphi(p)}M
$$
dunque devo correggere questa mappa con l'inversa.

Questa nozione si ricollega ai flussi per dare una prima nozione di derivata di campi vettoriali.

Riprendiamo la definizione di flusso di $X \in \mathcal{X}(M)$. Preso $p \in M$ , luna linea di flusso di $X$ è una curva $\varphi_{t}(p)$ tale che:
- $\varphi_{0}(p)=p$
- $\frac{d}{dt} \varphi_{t}(p)= X|_{\varphi_{t}(p)}$, che è n'ODE su $M$

$X$ è completo se ogni linea di flusso di $X$ è definita per ogni $t$.
Se $M$ è compatto, ogni campo vettoriale è completo.
In tal caso, il flusso di $X$ = insieme delle linee di flusso,
mappa che ad ogni $(t,p)$ associa $\varphi_{t}(p)$.
Questa è una mappa:
$$
	\mathbb{R} \times M \to \varphi_{t}(p)\in M
$$
Vediamo un fatto "ovvio":
Le linee di flusso sono bidirezionali, posso tornare da $\varphi_{t}(p)$ a $p$ usando la linea di flusso inversa $\varphi_{-t}(p)$.
Cioè, ogni $\varphi_{t}:M\to M, \quad p\to \varphi_{t}(p)$ è un diffeomorfismo.
Dunque un flusso mi da un diffeomorfismo per ogni $t$.
$$
	\mathbb{R}\to \text{Diff}(M), \qquad t\to \varphi_{t}
$$
Cosa succede se faccio la somma di due tempi?
$$
	t+s\to \varphi_{t+s}=\varphi_{s} \circ \varphi_{t}
$$
Questo mette in risalto il fatto che $\mathbb{R}$ è un gruppo per la somma, $\text{Diff}(M)$ è un gruppo per la composizione, allora un flusso è un omomorfismo tra gruppi.

Commenti:
1. $\mathcal{X}(M)\to \text{sottogruppi 1 dimensionali di Diff}(M)$,
   prendo $X\in\mathcal{X}(M)$ e lo mando in $\{ \varphi_{t}:t\in \mathbb{R} \}$, flusso di $X$.
   Ad ogni elemento di $\mathcal{X}$, insieme infinito-dimensionale associo un sottogruppo unidimensionale di Diff($M$), allora anche l'insieme dei diff. è infinito-dimensionato.
2. Di conseguenza, posso pensare a $\mathcal{X}(M)$ come diffeomorfismi infinitesimali:
$$
   	X\to \text{curva di diffeomorfismi nella direzione specificata da }X
   $$
   Ossia: 
$$
	\mathcal{X}(M)=T_{Id}\text{Diff}(M)
   $$
   = variazioni infinitesimali del punto $Id \in \text{Diff}(M)$ = diffeomorfismi infinitesimali


### Come derivare un campo vettoriale

Problema di fondo, vediamo come si deriva una funzione:
$$
	\frac{d}{dt} f(t)|_{t=0} = \lim_{ t \to 0 }  \frac{f(t)-f(0)}{t}
$$
Funziona perchè ha senso confrontare $f(t)$ e $f(0)$. Cioè serve una struttura di spazio vettoriale. Ulteriormente per poter fare un limite bisogna avere una topologia.
Ad esempio:
$$
	t\to v(t)\in V\simeq \mathbb{R}^n
$$
è uno spazio vettoriale e ha una topologia indotta da $\mathbb{R}^n$, quindi non è problematico fare $\frac{d}{dt} v(t)|_{t=0}$. 
Vogliamo derivare un campo vettoriale:
$$
	X: p\to X(p) \in T_{p}M
$$
Scegliamo una direzione data da una curva $\alpha$.
$$
	\frac{d}{dt}(X \circ\alpha)=\lim_{ t \to 0 } \frac{X|_{\alpha(t)}-X|_{\alpha(0)}}{t} 
$$
Questo non funziona perchè $X|_{\alpha(t)}$ e $X|_{\alpha(0)}$ appartengono a spazi diversi. Come posso confrontare vettori che si spostano tra spazi vettoriali diversi?
Prima di derivare devo o trovare un modo di riportare tutti i vettori sullo stesso spazio oppure trovare un modo per identificare vettori di spazi diversi.
Il primo modo è la derivata di Lie $\mathcal{L}_{z}X$. Il secondo modo è quello delle connessioni $\nabla_{z}X$.

Oggi ci occupiamo della derivata di Lie.
Dati 2 campi vettoriali $X$ e $Z$, la derivata di $X$ nella direzione $Z$ si fa nel modo seguente:
$$
	\underbrace{\mathcal{L}_{Z}(X)|_{p}}_{\text{campo vettoriale}}: -\frac{d}{dt}\{\underbrace{\varphi_{t}(X)_{p}}_{\text{flusso di } Z\to \text{push forward}}  \}|_{t=0}\in T_{p}M
$$
Cioè sposto i vettori di $X$ lungo $Z$ fino a $p$ tramite un push forward, a questo punto posso confrontare i campi e fare la derivata:
$$
	\mathcal{L}_{Z}X|_{p} = -\frac{d}{dt} \varphi_{t}(X)_{p}=-\lim_{ t \to 0 } \frac{\varphi_{t}(X)|_{p}-X|_{p}}{t}
$$
In sostanza $\mathcal{L}_{Z}(X)$ mi da le variazioni di $X$ sotto il flusso di $Z$.

Proposizione:
tutto inutile, nel senso che $\mathcal{L}_{Z}(X)=[Z,X]$.
Però $\mathcal{L}_{Z}$ servirà per derivare Tensori.




