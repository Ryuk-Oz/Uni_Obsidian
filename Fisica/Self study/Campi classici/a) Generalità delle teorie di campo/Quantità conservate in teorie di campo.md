---
corso: Teoria dei campi classica
data: 2026-07-31
tags:
  - studio_individuale
  - lagrangiane
argomenti:
  - Campi_classici
lezione-precedente: "[[Formulazione di una teoria di campo (classica) col formalismo lagrangiano]]"
---


> [!info] Contesto
> Corso: Teoria dei campi classica
> Argomenti previsti:  Correnti conservate, leggi di trasformazione, conservazione di energia e momento


## Riassunto veloce

Partendo dall'esempio del campo scalare libero  abbiamo studiato le quantità conservate associate a una teoria di campo e come si relazionano alla lagrangiana di densità, tralasciando temporaneamente il teorema di Noether.
In particolare abbiamo trovato che per ogni tensore $J^{\mu}$ costruito a partire dai campi che costituiscono la lagrangiana (per semplicità omettiamo gli altri indici), tale che $\partial_{\mu}J^\mu = 0$ , è possibile trovare una quantità conservata, covariante secondo lorentz, $Q = \int d\mathbf{x}J^0$ , legata alle altre componenti di $J^\mu$ tramite un'equazione di continuità (implicitamente definita da $\partial_{\mu}J^\mu = 0$).
Per questo motivo le componenti $J^1,J^2,\text{e } J^3$ prendono il nome di correnti.
Infine abbiamo dimostrato che nel caso in cui una coordinata $x^\sigma$ sia ciclica, allora questa quantità conservata $Q$ corrisponde all'energia del sistema ($\sigma=0$) o a una componente del momento del sistema ($\sigma =1,2,\text{o }3$). Come accade nella meccanica del punto materiale.
Infine abbiamo rivisto quest'ultima parte utilizzando la densità Hamiltoniana e abbiamo introdotto il tensore energia-impulso

## Appunti

### Correnti conservate

Riprendiamo l'esempio introdotto nella lezione precedente:
$$
	\mathfrak{L}=-\frac{1}{2}(\partial_{\mu}\phi)(\partial^\mu \phi)-\frac{m^2}{2}\phi^2+\phi S(x)
$$
Consideriamo ora le quantità $\mathcal{E}^\mu(x)$ definite nel seguente modo:
$$
	\begin{aligned}
	&\mathcal{E}^0(x)=\frac{1}{2}[(\partial_{0}\phi)^2+(\partial_{j}\phi)(\partial^j\phi)+m^2\phi^2]+\phi S, \\
	&\mathcal{E}^j(x) = -(\partial_{0}\phi)(\partial^j\phi) \qquad j = 1,2,3
	\end{aligned}
$$
Queste quantità non sono altro che le quantità conservate associate ad una traslazione temporale e sono ricavate adattando il teorema di Noether a questo nuovo formalismo (vedi lezioni successive), nonostante ciò possiamo comunque andare a ricavare $\mathcal{E^0}$.
per prima cosa divido la lagrangiana nei suoi contributi temporali e spaziali	$$
		L = \frac{1}{2}(\partial_{0}\phi)^2-\frac{1}{2}(\partial_{j}\phi)(\partial^j\phi)-\frac{m^2}{2}\phi + \phi S
	$$
Per il termine $\mathcal{E^0}$ ritrovo la forma dell'energia generalizzata $H = \frac{ \partial L }{ \partial \dot{q} }\dot{q}-L$ adattata a questo nuovo formalismo:	$$
		\mathcal{E}^0 = \frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi)}\partial_{\mu}\phi - \mathfrak{L} 
	$$
per questo motivo $\mathcal{E^0}$ prende il nome di densità di energia. 
Per $\mathcal{E}^j$ dobbiamo invece aspettare una generalizzazione del teorema di Noether.
Come esercizio, calcoliamo la derivata di $\mathcal{E}^\mu$ rispetto al quarivettore $x^\mu$, e sfruttiamola per dimostrare la natura energetica di $\mathcal{E}^0$.
$$
	\partial_{\mu}\mathcal{E^\mu}= \partial_{0}\mathcal{E^0}+\partial_{j}\mathcal{E^j}
$$
supponendo che la sorgente esterna $S$ sia indipendente dal tempo otteniamo:
$$
	\begin{aligned}
	\partial_{0}\mathcal{E}^0 &= (\partial_{0}\phi)(\partial_{0}\partial_{0}\phi)+(\partial_{0}\partial_{j}\phi)(\partial_{j}\phi)+m^2(\partial_{0}\phi)\phi+(\partial_{0}\phi)S+\phi(\partial_{0}S)\\
		\partial_{j}\mathcal{E^j} &= -(\partial_{j}\partial_{0}\phi)(\partial_{j}\phi)-(\partial_{0}\phi)(\partial_{j}\partial_{j}\phi)
	\end{aligned}
$$
Unendo, tenendo conto della metrica, otteniamo:
$$
	\partial_{\mu}\mathcal{E^\mu} = (\partial_{0}\phi )[(-\partial_{\mu}\partial^\mu +m^2)\phi+S]+\phi(\partial_{0}S)
$$
Imponendo che la sorgente non vari nel tempo, cioè $\partial_{0}S=0$, e riprendendo le equazioni di E-L (ricavate nella sezione [[Formulazione di una teoria di campo (classica) col formalismo lagrangiano]]), otteniamo $\partial_{\mu}\mathcal{E^\mu}=0$).

Se a questo punto prendo l'energia definita come $E(t)=\int d\mathbf{x}\mathcal{E}^0(t,\mathbf{x})$, ne segue direttamente che questa quantità si conserva. Infatti, usando il teorema della divergenza e l'uguaglianza appena ottenuta troviamo:
$$
\frac{d}{dt}E(t) = \int_{V} d\mathbf{x}\partial_{0}\mathcal{E}^0 =-\int_{V} d\mathbf{x}\partial_{j}\mathcal{E}^j = -\oint_{\partial V}\mathbf{\mathcal{E}\cdot d\mathbf{A}}=0
$$
Dove l'ultimo integrale si annulla ipotizzando che $\mathbf{\mathcal{E}}$ diminuisca abbastanza velocemente all'aumentare del raggio e integrando su una sfera di $r\to \infty$.

Dunque scrivere $\partial_{\mu}\mathcal{E}^\mu=0$ non è altro che un'espressione attraverso la quale descriviamo una conservazione locale dell'energia. Riscrivendolo in una forma diversa, si ottiene infatti qualcosa che ci è molto familiare, un'equazione di continuità:
$$
	\frac{d}{dt}\int_{V}\mathcal{E}^0d\mathbf{x}=-\oint_{\partial V}\mathbf{\mathcal{E}}\cdot d\mathbf{A}
$$
Queste conclusioni a cui siamo arrivati in un caso semplificato, sono in realtà un esempio di un fenomeno generale. Ogni volta che, partendo dai campi base di una teoria di campo, possiamo costruire un insieme di campi $J^0(x), \,J^1(x), \,J^2(x),\,J^3(x)$ che obbediscono all'uguaglianza $\partial_{\mu}J^\mu=0$, allora la quantità $Q(t)=\int d\mathbf{x}J^0(x)$ è una quantità conservata e posso interpretare localmente $J^0$ come la densità di "$Q$" e $J^j$ come correnti (elettriche, di energia, ecc...)

### Leggi di trasformazione

La trattazione appena fatta vale in uno specifico sistema di riferimento. Cambiando sistema di riferimento le componenti del campo vettoriale $J^\mu$ (o del campo tensoriale $J^\mu=T^{\mu 1}$ ad esempio), devono trasformarsi secondo una certa legge di trasformazione che si ripercuote anche sulla quantità $Q$ (troveremo che $Q$ sarà un invariante di Lorentz).

Riprendendo il paragrafo precedente, considero: $Q=\int d\mathbf{x}J^0(0,\mathbf{x})$. A questo punto considero un cambio di parametrizzazione $x^\mu = x^\mu(a^1, a^2, a^3)$. 
(Abbiamo scelto 3 parametri perchè la coordinata $x^0$ di partenza era fissata a 0 quindi il sistema iniziale aveva 3 gradi di libertà.)
Dunque: 
$$
Q=\int d^3a \frac{ \partial (\mathbf{x}) }{ \partial (\mathbf{a}) }J^0(x^\mu(a^1,a^2,a^3))
$$
Andiamo a sviluppare la matrice Jacobiana.
$$
\begin{aligned}
	\frac{ \partial (\mathbf{x}) }{ \partial (\mathbf{a}) } &= \det\left[ \frac{ \partial x^i }{ \partial x^j }  \right] \\
	&=\mathbf{\epsilon_{ijk}}\frac{ \partial x^i }{ \partial a^1 }\frac{ \partial x^j }{ \partial a^2 } \frac{ \partial x^k }{ \partial a^3 } \\
	&=-\mathbf{\epsilon_{0\nu\alpha\beta}}\frac{ \partial x^\nu }{ \partial a^1 } \frac{ \partial x^\alpha }{ \partial a^2 } \frac{ \partial x^\beta }{ \partial a^3 } 
\end{aligned}
$$
A questo punto possiamo riscrivere l'integrale in forma covariante.
$$
\begin{aligned}
	Q &= \int dS_{\mu }J^\mu \\
	dS_{\mu} &= -\mathbf{\epsilon_{\mu\nu\alpha\beta}}\frac{ \partial x^\nu }{ \partial a^1 } \frac{ \partial x^\alpha }{ \partial a^2 } \frac{ \partial x^\beta }{ \partial a^3 } da^1da^2da^3
\end{aligned}
$$
(In realtà nella definizione di Q da cui siamo partiti abbiamo utilizzato solo il termine $J^0$, ma questo è un caso specifico).

Riscritto in questa forma, l'integrale non è altro che un integrale di superficie lungo su una superficie tridimensionale $\mathcal{S}$ definita in maniera parametrica delle equazioni $x^\mu=x^\mu(a^1,a^2,a^3)$.
Il differenziale $dS_{}\mu$ è un vettore ortogonale alla superficie in $a$ (iinfatti lo abbiamo definito proprio come in 3MC e difatto vive in $T\mathcal{S}$).
Essendo $dS_{\mu}$ un vettore, allora $dS_{\mu}J^\mu$ è un prodotto scalare ed è per tanto un invariante di lorentz, indipendente dalla scelta delle coordinate $a$.

Tuttavia resta una traccia della superficie su cui abbiamo integrato, nel valore della coordinata 0esima che abbiamo fissato all'inizio, in questo caso $x^0 = 0$. Per dimostrare che $Q$ sia davvero uno scalare (e che sia davvero invariante), dobbiamo mostrare che il risultato resti uguale per ogni scelta di $x^0$ (e cioè per ogni scelta di superficie).

La superficie originale era quella descritta dall'equazione $x^\mu c_{\mu}=0$ con $c_{\mu}=(1,0,0,0)$, vettore diretto lungo l'asse temporale. Un'altro osservatore "misurerà" la superficie $x^\mu b_{\mu}=0$ (posso trovare $b_{\mu}$ con le trasformazioni di Lorentz).
Vogliamo mostrare che:
$$
	\begin{aligned}
	Q_{c}=\int_{x\cdot c=0}dS_{\mu}J^\mu = \int_{x\cdot b=0}dS_{\mu}J^\mu=Q_{b}
	\end{aligned}
$$
Per mostrare ciò useremo il Teorema di Gauss (divergenza) e l'identità $\partial_{\mu}J^\mu=0$, in modo analogo a quanto fatto nelle correnti conservate.
Considero il volume 4-dimensionale racchiuso all'interno delle superfici $x\cdot c=0$, $x\cdot b=0$, e $\mathbf{x}^2=R^2$. 
![[dimostrazione_covarianza_carica.png]]
Questo volume consta di due regioni distinte $I$ e $II$. 
$$
	\begin{aligned}
	\int_{I}d^4x\partial_{\mu}J^\mu &= 0 \\
	\int_{II}d^4x\partial_{\mu}J^\mu & = 0 \\
	\Rightarrow 0 = \int_{II}d^4x\partial_{\mu}J^\mu &- \int_{I}d^4x\partial_{\mu}J^\mu
	\end{aligned}
$$
Per il teorema della divergenza, ho:
$$
	\int_{V}d^4x\partial_{\mu}F^\mu = \int_{\partial V}dS_{\mu}F^\mu
$$
(Il teorema della divergenza vale in 4 dimensioni come in 3 e si dimostra allo stesso modo, il perchè mi è ignoto).
Allora l'uguaglianza di prima diventa:
$$
	0 = \int_{\begin{aligned}
	x\cdot &b =0 \\
	x^2&<R^2
	\end{aligned}} dS_{\mu}J^\mu - \int_{\begin{aligned}
	x\cdot &c =0 \\
	x^2&<R^2
	\end{aligned}} dS_{\mu}J^\mu + \int_{\text{lati con } x^2=R^2} dS_{\mu}J^\mu
$$
Per R che tende ad infinito rapidamente, abboamo che il contributo lungo i lati $x^2 = R^2$ si annulla e $x^2<R^2$ diventa una tautologia e otteniamo infine:
$$
	\int_{x\cdot c=0}dS_{\mu}J^\mu = \int_{x\cdot b=0}dS_{\mu}J^\mu
$$
Abbiamo dimostrato efficacemente il caso scalare, tuttavia si può facilemnte generalizzare al caso in cui $J^{\alpha\dots \mu}$ sia un tensore di rango N e $dS_{\mu}J^{\alpha\dots \mu} = 0$, in questo caso la carica conservata $Q$ non sarà più uno scalare, bensì un tensore di rango N-1.

### Conservazione del momento e dell'energia

Nello studio dell'esempio specifico abbiamo visto che la sorgente $S(x^\mu)$ sia indipendente dal tempo nel caso in cui una certa quantità $E$ costruita dai campi si conservi. Andiamo ora a generalizzare questo risultato per sorgenti indipendenti da coordinate diverse da $x^0$.

Considero una teoria di campi di componenti $\phi_{1}(x),\phi_{2}(x),\dots,\phi_{n}(x)$
Prendiamo la densità di lagrangiana $\mathfrak{L}(\phi_{k},\partial_{\mu}\phi_{k},x)$ e immaginiamo che non dioenda esplicimente da una delle coordinate $x^0,x^1,x^2,x^3$ che chiameremo $x^\sigma$, ciò implica che la sorgente sia indipendente da una di queste 4 coordinate.
Allora:
$$
	\frac{ \partial \mathfrak{L}(\phi_{k},\partial_{\mu}\phi_{k},x)}{ \partial x^\sigma } = 0
$$
Tuttavia $\mathfrak{L}$ dipende ancora implicitamente da $x^\sigma$ nel seguente modo:
$$
\partial_{\sigma}\mathfrak{L}(\phi_{k},\partial_{\mu}\phi_{k},x) = \sum_{k}\frac{ \partial \mathfrak{L} }{ \partial \phi_{k} } \partial_{\sigma}\phi_{k} + \frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k})}\partial_{\sigma}\partial_{\mu}\phi_{k} 
$$
Cerchiamo ora un candidato per una corrente conservata (cioè tale che $\partial_\mu T^{\mu}=0$, non per forza usando un quadrivettore, posso anche scegliere tensori di rango superiore).
Il candidato in questione è un tensore di rango $(1,1)$ costruito nel seguente modo:
$$
	T_{\sigma}^{\;\mu}(x) = \delta^\mu_{\sigma}\mathfrak{L}-\sum_{k}(\partial_{\sigma}\phi_{k})\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) } 
$$
Svolgiamo i calcoli per verificare che questa sia una corrente conservata, sfruttando i calcoli già svolti per $\partial_{\sigma}\mathfrak{L}$ :
$$
	\begin{aligned}
	\partial_{\mu}T_{\sigma}^{\,\mu} &= \partial_{\sigma}\mathfrak{L}-\sum_{k}\left[ ( \partial_{\mu}\partial_{\sigma}\phi_{k})\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) } +\left( \partial_{\sigma}\phi_{k}  \right)\partial_{\mu}\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) } \right] \\
	&= \sum_{k}\left[\frac{ \partial \mathfrak{L} }{ \partial \phi_{k} } \partial_{\sigma}\phi_{k} + \frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k})}\partial_{\sigma}\partial_{\mu}\phi_{k} - ( \partial_{\mu}\partial_{\sigma}\phi_{k})\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) } - \left( \partial_{\sigma}\phi_{k}  \right)\partial_{\mu}\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) }\right] \\
	&=\sum_{k}(\partial_{\sigma}\phi_{k})\left[ \frac{ \partial \mathfrak{L} }{ \partial \phi_{k} } - \partial_{\mu}\frac{ \partial \mathfrak{L} }{ \partial (\partial_{\mu}\phi_{k}) } \right] = 0
	\end{aligned}
$$
dove l'ultima uguaglianza è ottenuta da Eulero-Lagrange.

Pertanto, se la lagrangiana è indipendente dalle coordinate $x^\sigma$ la quantità:
$$
	P_{\sigma}=\int d\mathbf{x}T_{\sigma}^{\,0}(x)
$$
è una quantità conservata.
La quantità $P^0=-P_{0}$ è detta energia del sistema, mentre la quantità $P^1=P_{1}$ è la prima componenete del momento del sistema, e lo stesso si può dire per $P^2$ e $P^3$. 
Dunque in maniera analoga a quanto noto per i punti materiali, in presenza di coordinate cicliche ritroviamo rispettivamente energia e momenti coniugati.
Inoltre quando $T_{\sigma}^{\,\mu}$ è un tensore, la quanità $P_{\sigma}$ forma un quadri(co)vettore, il quadrimomento.
Questo tensore prende il nome di tensore energia impulso

### Tensore energia impulso a partire dalla densità Hamiltoniana


In maniera simile a quanto fatto per la singola particella, partendo dalla densità lagrangiana $\mathcal{L}$ possiamo definire un momento coniugato corrispondente:
$$
	\pi^r_{\mu}=\frac{ \partial \mathcal{L} }{ \partial (\partial^\mu \phi_r) }, \quad\pi^r(t,\vec{x})=\pi^r_{0}(t,\vec{x})

$$
e la corrispondente densità Hamiltoniana:
$$
	\mathcal{H}(\phi_{r},\partial_{i}\phi_{r};\pi^r) = \dot{\phi_{r}}\pi^r-\mathcal{L}(\phi_{r},\partial_{i}\phi_{r})
$$
a differenza della densità lagrangiana, la densità Hamiltoniana non è lorentz-invariante. Ovviamento possiamo ottenere l'Hamiltoniana del sistema andando a integrare la densità Hamiltoniana nello spazio.
$$
	H=\int_{V}d^3x\,\mathcal{H}
$$
si può dimostrare che $H$ si conserva nel tempo per ogni configurazione di campi $\phi_{r}$ che soddisfa Eulero-Lagrange ma in questo caso è più semplice lavorare su di un problema più generale.
Definiamo il Tensore energia-impulso nel seguente modo (coincide con quello definito nella sezione precedente!).
$$
	T_{\mu \nu}=-(\partial_{\mu} \phi_{r})\pi^r_{\nu}+\eta_{\mu \nu}\mathcal{L}
$$
Che per costruzione si trasforma come un tensore di rango 2.
La componente 00 di questo tensore è:
$$
	T_{00}=\dot{\phi_{r}}\pi^r-\mathcal{L}=\mathcal{H}
$$
Per dimostrare la conservazione dell'energia calcoliamo a questo punto la divergenza di $T_{\mu \nu}$.
$$
	\begin{aligned}
	\partial^\nu T_{\mu \nu}&=-(\partial^\nu \partial_{\mu}\phi_{r})\pi^r_{\nu}-(\partial_{\mu}\phi_{r})(\partial^\nu \pi^r_{\nu})+\partial_{\mu}\mathcal{L}\\
	&=(\partial^\nu \partial_{\mu}\phi_{r})\pi^r_{\nu}-(\partial_{\mu}\phi_{r})(\partial^\nu \pi^r_{\nu})+\left\{  \frac{ \partial \mathcal{L} }{ \partial \phi_{r} }\partial_{\mu}\phi_{r}+ \frac{ \partial \mathcal{L} }{ \partial (\partial_{\nu}\phi_{r}) } \partial^\nu(\partial_{\mu}\phi_{r})  \right\}
	\end{aligned}
$$
I termini tra parentesi escono dall'aver derivato $\mathcal{L}$.
Sostituendo la definizione di $\pi^r_{\nu}$ e le equazioni di Eulero-Lagrange, tutti i termini si elidono e resto con: $\partial^\nu T_{\mu \nu}=0$ pertanto a questo posso associare delle leggi di continuità.
In particolare posso definire il seguente quadrivettore:
$$
	P_{\mu} = \int_{V}d^3x\,T_{\mu_{0}}
$$
E trovo che:
$$
	P_{0} = \int_{V}d^3x\,T_{00} = \int_{V}d^3x\, \mathcal{H} = H
$$
Ora posso finalmente verificare la conservazione dell'energia:
$$
	\partial^0 P_{0} = \int_{V}d^3x\,\partial^0T_{00}=-\int_{V}d^3x\,\partial^iT_{0i} =0
$$
Dove nell'ultimo passaggio abbiamo applicato il teorema della divergenza e la condizione di annullamento al bordo.

## Domande aperte / cose da rivedere
- [x] Capire cosa significa forma covariante
- [ ] Teorema della divergenza 4-dimensionale

## Collegamenti
- Lezione precedente: [[Formulazione di una teoria di campo (classica) col formalismo lagrangiano]]

