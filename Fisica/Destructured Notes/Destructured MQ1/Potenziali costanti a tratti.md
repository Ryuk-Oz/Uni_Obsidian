
Occupiamoci per prima cosa dei problemi di semplicità maggiore (sono quelli di cui ci occupiamo durante le esercitazioni con Badger), i problemi in cui il potenziale è costante a tratti.

![[Pasted image 20261017105137.png]]

Tramite potenziali di questo tipo è possibile andare a costruire numerosi esempi interessanti per modellare in maniera semplice alcune situazioni fisiche, ad esempio si possono creare semplici modelli di barriere e buche di potenziale.

Potenziali di questo tipo presentano però una grande problematica data dall'approssimazione che facciamo. Il problema è che il potenziale è discontinuo (e questo ha necessariamente delle ripercussioni su $\psi$), quando nella realtà la situazione che incontreremmo sarebbe quella di una variazione continua di $V$, seppur molto rapida

Quali sono le condizioni di continuità che si vanno a creare su $\psi(x)$ per $V$ discontinuo?
La prima condizione che andiamo a imporre è di natura puramente fisica ed è che $\psi(x)$ sia continua nei punti di "salto" del potenziale.
Possiamo però trovare anche una condizione sulle derivate, per farlo andiamo ad integrare l'edS su un intervallo piccolo attorno a un "salto".
$$
	\int^{x_{0}+\delta}_{x_{0}-\delta} dx \, \frac{d^2}{dx^2}\psi(x)=\frac{2m}{\hbar^2}\int^{x_{0}+\delta}_{x_{0}-\delta} dx\, [V(x)-E]\psi(x)
$$
Se la discontinuità è finita, l'integrale a destra esiste per ogni valore di $\delta$ e si annulla per $\delta$ che tende a 0. Pertanto a sinistra otteniamo:
$$
	\frac{d\psi}{dx}|_{x_{0}^+}-\frac{d\psi}{dx}|_{x_{0}^-}=0
$$
Cioè la derivata è continua nei punti di discontinuità del potenziale.
Se l'altezza del gradino di potenziale è infinita, questo non è più possibile

Occupiamoci ora di fare alcune considerazioni su quelli che sono gli stati legati all'interno di una buca di potenziale.

![[Pasted image 20261017110236.png]]

Nelle zone $I$ e $III$ abbiamo:
$$
	\begin{aligned}
	\frac{d^2\psi}{dx^2}-&\beta^2=0\\
	\text{con }\beta=&\sqrt{ \frac{2m}{\hbar^2}(V_{0})-E }>0
	\end{aligned}
$$
Nella zona $II$ trovo invece:
$$
    \begin{aligned}
	\frac{d^2\psi}{dx^2}+&k^2 \psi =0\\
	\text{con } k=&\sqrt{ \frac{2mE}{\hbar^2} }=\frac{p}{\hbar}
	\end{aligned}
$$
Nella zona $III$ trovo come soluzione $\psi(x)=Ae^{\beta x}+Be^{-\beta x}$ , ed escludo la soluzione $Ae^{\beta x}$ perchè esplode e non è normalizzabile. Analogamente nella zona $I$ devo andare ad escludere a soluzione $\propto e^{-\beta x}$.
Nella zona $II$ ottengo invece l'equazione dell'oscillatore armonico e ho soluzioni oscillanti.
$$
	\begin{cases}
	\psi_{I}=Ae^{\beta x} \\
	\psi_{II}=Be^{ikx}+Ce^{ -ikx } \\
	\psi_{III}=De^{ -\beta x }
	\end{cases}
$$
A questo punto basta risolvere il sistema imponendo le condizioni di continuità.

![[Pasted image 20261017111318.png|535]]
.
**OSS:** abbiamo ottenuto una probabilità non nulla di trovare la particella nelle regioni in cui $V>E$, che sarebbero classicamente proibite.
Non abbiamo mai notato questo fenomeno perchè il coefficiente dell'esponenziale fa crollare la probabilità a 0 così veolcemente da non essere un fenomeno osservabile a livello macroscopico.
Questo fenomeno prende il nome di effetto tunnel e può essere usato per formulare i primi toy model in grado di spiegare i decadimenti radioattivi.

![[Pasted image 20261017111700.png]]