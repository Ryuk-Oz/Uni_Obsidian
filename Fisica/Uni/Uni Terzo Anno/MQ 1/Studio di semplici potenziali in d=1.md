---
corso: Meccanica Quantistica 1
data: 2026-10-13
tags:
  - lezione
argomenti: []
lezione-precedente:
source:
---


> [!info] Contesto
> Corso: undefined
> Argomenti previsti: 

## Riassunto veloce



## Appunti

In questa sezione ci occupiamo dello studio di semplici problemi con potenziali stazionari unodimensionali per "farci le ossa" e acquisire dimestichezza con i calcoli
### Nozioni generali sui problemi unidimensionali

Per prima cosa partiamo dall'equazione di Shrödinger stazionaria nel caso unidimensionale.
$$
	-\frac{\hbar^2}{2m} \frac{d^2}{dt^2}\psi+V(x)\psi=E\psi
$$
Si tratta di un'equazione alle derivate ordinarie che sappiamo risolvere, conviene però fare alcune osservazioni preliminari.

1. Per $E$ fissato e potenziale $V(x)$ generico, la soluzione generata è una combinazione lineare di 2 (poichè l'eq. è di grado 2) soluzioni particolari. 
   $$
   	\psi_{E}=Au_{E}(x)+Bv_{E}(x)
   $$
2. Date due soluzioni per $E$ fissato possiamo andare a definire il Wronksiano: 
$$
   	W_{E}(x)=u'_{E}(x)v_{E}(x)-u_{E}(x)v'_{E}(x)
   $$
   Se $u_{E} \text{ e } v_{E}$ sono soluzioni, allora il wronksiano è costante:
   $$
	\begin{aligned}
	W'_{E}&=u''v+u'v'-uv''-u'v'=u''v+uv''=\\
	&=-\frac{2m}{\hbar^2}(E-V(x))(u_{E}v_{E}-u_{E}v_{E})=0
	\end{aligned}
   $$
3. $W_{E}=0\iff u_{E}\propto v_{E}$, cioè $u_{E}$ e $v_{E}$ sono linearmente dipendenti
4. Per soluzioni normalizzate su $\mathbb{R}$ gli autovalori di $\hat{H}$ sono NON DEGENERI, cioè, dato $E_{n}$ autovalore, i corrispondenti $u_{n} \text{ e } v_{n}$ sono t.c. $u_{n}\propto v_{n}$.
   Infatti $u_{n}$ e $v_{n}$ devono annullarsi all'infinito (per la normalizzazione), dunque all'infinito $W_{n}=0$, ma, poichè $W_{n}(x)=\text{cost}$ ovunque, allora il Wronksiano sarà ovunque nullo e $u_{n}$ e $v_{n}$ saranno proporzionali tra loro.

Facciamo adesso un'osservazione di natura classica. Riscriviamo l'equazione in questa forma:
$$
	\frac{\psi''}{\psi}=\frac{2m}{\hbar^2}(V(x)-E)
$$
Le regioni classicamente permesse sono quelli in cui l'energia $E>V(x)$, allora $\frac{\psi''}{\psi}<0$ e la funzione d'onda sarà oscillante. Nelle regioni classicamente proibite avrò $\frac{\psi''}{\psi}>0$ e la mia funzione d'onda avrà andamento esponenziale.

![[Pasted image 20261013205135.png]]

Vedremo come in meccanica quantistica dovremo andare a studiare anche le regioni classicamente proibite.

5. Preso un potenziale simmetrico $V(x)=V(-x)$, le soluzioni normalizzabili hanno parità definita: 
$$
   	\psi_{n}(x)=\pm \psi_{n}(-x)
   $$
   Infatti se sostituisco $\psi(-x)$ nell'equazione di Shrödinger (stazionaria) ottengo: 
   $$
	-\frac{\hbar^2}{2m} \frac{d^2}{dx^2}\psi(-x)+V(x)\psi(-x)=E\psi(-x)
   $$
   Poichè $V(-x)=V(x)$ anche $\psi(-x)$ è soluzione dell'equazione di Shrödinger.
   Ulteriormente, dalla conservazione del Wronksiano so che le soluzioni normalizzabili sono tra loro linearmente dipendenti: 
   $$
	\begin{cases}
	\psi_{n}(x)=C\psi_{n}(-x) \\
	\psi_{n}(-x)=C\psi_{n}(x)
	\end{cases}\implies C^2=1 \text{ e } C=\pm 1
   $$

### Studio di potenziali costanti a tratti

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

### La buca di potenziale infinita

Occupiamoci ora di un modello ancor più semplificato, quello di una buca di potenziale di profondità infinita.

![[Pasted image 20261017111825.png]]

Nelle zone $I$ e $III$ abbiamo che $\beta\to \infty$ perchè il potenziale è infinito nei salti, pertanto ho probabilità nulla di trovare la particella in una regione classicamente proibita. 
$$
	\psi_{I}(x)=\psi_{III}=0
$$
Occupiamoci dunque dello studio della sola regione permessa.
$$
	\frac{d^2\psi}{dx^2}+k^2\psi(x)=0
$$
cerchiamo soluzioni reali, quindi scriviamo la soluzione generale in termini di seni e coseni anzichè di esponenziali.
$$
	\psi(x)=A\sin kx+B\cos kx \quad \text{con } k=\sqrt{ \frac{2mE}{\hbar^2} }
$$
Imponiamo la continuità di $\psi(x)$, poichè il gradino di potenziale è infinito, non facciamo alcunchè sulla derivata.
$$
	\begin{cases}
	\psi(0)=0=B \\
	\psi(a)=0=A\sin(ka) \implies ka=n\pi \text{ e } k_{n}=\frac{n\pi}{a}; \, n\in \mathbb{N}, \, n\neq_{0}
	\end{cases}
$$
Cioè, abbiamo fissato i 2 estremi, trovando come soluzione un'onda stazionaria.
$$
	\psi_{n}(x)=A\sin\left( \frac{n\pi}{a}x \right)
$$
Cerchiamo la costante $A$ normalizzando. (NOTA BENE: Dopo aver imposto la continuità devo sempre trovare una costante libera che poi andrò a ricavare imponendo la normalizzazione).
$$
	\begin{aligned}
	1&=\int_{0}^adx\,|A|^2\sin^2\left( \frac{n\pi}{a}x \right) \\
	&=|A|^2 \frac{a}{2} \implies A=\sqrt{ \frac{2}{a} }
	\end{aligned}
$$
Dunque la funzione d'onda finale è:
$$
	\psi_{n}(x)=\sqrt{ \frac{2}{a} }\sin\left( \frac{n\pi}{a}x \right)
$$
I livelli energetici permessi sono invece:
$$
	E_{n}=\frac{k_{n}^2\hbar^2}{2m}= \frac{(n\pi \hbar)^2}{2ma^2}
$$
Cioè le particelle legate ammettono uno spettro discreto.

Osservazioni varie sulle soluzioni ottenute:
- Le $E_{n}$ sono non degeneri, come ci aspoettiamo dagli autovalori di $\hat{H}$
- Le $\psi_{n}$ hanno parità definita rispetto al centro della buca, come atteso
- Le $\psi_{n}$ hanno $n+1$ nodi tra le barrire della buca. 
- La soluzione per $n=0$ non è accettabile altrimenti avrei $E_{0}=0$ e la particella sarebbe ferma, cioè la particella avrebbe posizione e impulsi ben definiti, il che viola il principio di indeterminazione.
- Nel limite classico ho: $E_{n+1}-E_{n}=\frac{\pi^2\hbar^2}{2ma^2}[(n+1)^2-n^2]=\frac{\pi^2\hbar^2}{2ma^2}(2n+1)$ 
  $\implies \frac{E_{n+1}-E_{n}}{E_{n}}=o\left( \frac{1}{n} \right)$. Per oggetti microscopici ho $n\gg{1}$, dunque non vedo la differenza tra gli spettri energetici e lo spettro mi sembra continuo.

Come varia l'interpretazione probabilistica nel limite classico? Osserviamo graficamente la situazione quantistica e classica a confronto:

![[Pasted image 20261017115651.png]]

cioè $\rho_{\text{classica}}=\frac{1}{a}$. Ora prendiamo la densità di probabilità quantistica e mandiamola a infinito, poi calcoliamo il valore medio.

![[Pasted image 20261017115829.png]]

Abbiamo riottenuto il risultato classico.

A questo punto, sappiamo che la soluzione generale all'EdS per potenziali per buche di potenziale infinite è:
$$
	\psi(x,t)=\sum_{n=1}^\infty C_{n}\psi_{n}(x)e^{ -\frac{i}{\hbar}E_{n}t }
$$
Possiamo dimostrare che questa soluzione trovi effettivamente tutte le soluzioni del caso che abbiamo studiato? Dall'analisi discreta di Fourier sappiamo che seni e coseni formano una base di $L^2(0,a)$ pertanto siamo sicuri che in questo modo sia possibile trovare tutte le soluzioni.
Non solo, $L^2(0,a)$ ammette anche un prodotto scalare, tramite cui possiamo verificare l'ortogonalità della base:
$$
	\begin{aligned}
	(\psi_{m},\psi_{n})&\equiv \int^a_{0} dx \,\psi^*_{m}(x)\psi_{n}(x)=\frac{2}{a}\int^a_{0}dx \sin\left( \frac{m\pi}{a}x \right)\sin\left( \frac{n\pi}{a}x \right)=\\
	&=\frac{2}{a}\int^a_{0}dx \, \frac{1}{2} \left[ \cos\left( \frac{(m-x)\pi}{a}x\right) -\cos\left( \frac{(n-x)\pi}{a}x \right) \right] =\delta_{mn}
	\end{aligned}
$$
Ulterioremente, con il teorema di Dirichlet, è possibile dimostrare che le due funzioni sono anche ortonormali.

## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

