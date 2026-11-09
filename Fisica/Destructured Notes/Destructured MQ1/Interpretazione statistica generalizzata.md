
Il terzo postulato è il seguente: 
"Gli autovalori degli opertatori $\hat{A}$ associati alle osservabili $a$ sono **tutti e soli i possibili risultati** di una misura sperimentale di $a$. 
Posto che ogni stato $\ket{\alpha}$ può essere espresso nella base degli autostati di $\hat{A}$ (e tale base è ON), 
$$
	\underbrace{\ket{\alpha} =\sum c_{n}^{(\alpha)}\ket{a_{n}} }_{\text{spettro discreto}} \qquad \underbrace{\ket{\alpha} =\int d\sigma\, c_{\alpha}(\sigma) \ket{a_{\sigma}} }_{\text{spettro continuo}}
$$
è possibile interpretare $|c^{(\alpha)}_{n}|^2$ come **probabilità** di ottenere il valore $a_{n}$ effettuando una misura di $a$ sullo stato $\ket{\alpha}$ (per spettro discreto).
Ed è possibile imterpretare $|c_{\alpha}(\sigma)|^2$ come **densità di probabilità** di ottenere il valore $a_{\sigma}$ effettuando una misura di $a$ sullo stato $\ket{\alpha}$.
E si ha che $c_{n}^{(\alpha)}=\langle a_{n}|\alpha \rangle$ e $c_{\alpha}(\sigma)=\langle a_{\sigma}|\alpha \rangle$."

Abbiamo anche già dimostrato che queste probabilità sono normalizzate:
$$
	\left( \sum_{n} |c^{(\alpha)}_{n}|^2 =1=\int d\sigma\, |c_{\alpha}(\sigma)|^2\right)
$$
#### Precisazioni sul processo di misura

La misura di un osservabile $a$ in uno stato $\ket{\alpha}$ in meccanica quantistica implica un processo in 2 fasi.

- **Preparazione**
	Viene identificato lo stato $\ket{\alpha}$. Cioè vengono fatte delle misure preliminari di un insieme di osservabili $\{ a_{1},\dots,a_{p} \}$ sufficienti a caratterizzare univocamente lo stato $\ket{\alpha}$.
	**Achtung!**
	- Per poter fare ciò, devo conoscere lo spazio $\mathcal{H}$ in modo sufficientemente preciso da sapere come $\ket{\alpha}$ possa essere univocamente caratterizzato.
	- Nel caso della meccanica classica, tale conoscenza dello stato $\ket{\alpha}$ corrispondeva ad una determinazione di TUTTE le osservabili fisiche. Preso un punto nello spazio delle fasi $\{ q_{i},p_{i} \}$, tutte le funzioni $Q(q_{i},p_{i})$ sono determinate e la loro evoluzione temporale è dettata da $H$.
	- Nel caso della meccanica quantistica, invece, una volta misurate $p$ osservabili $a_{i}$ che caratterizzano univocamente lo stato $\ket{\alpha}$, esistono in generale altre osservabili indipendenti $B_{k}$ il cui valore NON è determinato
	- Il processo di preparazione da noi descritto è idealizzato, in un caso realistico non tutte le $a_{p}$ possono essere misurate e diciamo che non è stato preparato uno "STATO PURO" $\ket{\alpha}$, ma una "MISCELA STATISTICA" di dati $\ket{\alpha_{\sigma}}$. Per trattare tale situazione si introduce il formalismo della matrice densità
	- Ipotizziamo che la preparazione sia IDENTICAMENTE RIPETIBILE, così da permetterci molte misure su stati $\ket{\alpha}$ identici.

- **Misura** (di una quantità ignota)
	Si effettua una misura di una generica osservabile in $\{ a_{i},B_{k} \}$ che si immagina essere ripetuta molte volte su stati identici $\ket{\alpha}$
	- Se si misura una delle $a_{i}$ si trova con certezza il valore determinato dalla preparazione, $\ket{\alpha}$ autostato di ciascuna $a_{i}$ (ad ogni osservabile $a_{i}$ posso associare un operatore e $\ket{\alpha}$ è autostato per ciascuno di tali operatori.)
	- Se misuro un'altra osservabile $B$ (e $\hat{B}$ operatore autoaggiunto corrisponente), dato lo sviluppo:
	$$
		\ket{\alpha} =\sum_{n} c_{n}^{(\alpha)} \ket{b_{n}} \qquad \text{e} \qquad \hat{B}\ket{b_{n}} =b_{n}\ket{b_{n}} 
	 $$
	 troverò il valore $b_{n}$ con una probabilità pari a $|c_{n}^{(\alpha)}|^2$.
	- Se effettuo immediatamente un altra misura di $B$ (senza far interagire il sistema con altro), ritrovo con certezza $b_{n}$. Cioè:
	 **PRIMA:** il sistema sta nello stato $\ket{\alpha}$, preparato
	 **DOPO** (la misura di $B$)**:** il sistema di trova nello stato $\ket{b_{n}}$, autostato di $B$.
	 
	 Ne concludiamo che la misura (e più generalmente un interazione con un apparato sperimentale esterno e "macroscopico") modifica in maniera irreversibile lo stato del sistema $\implies$ il processo di misura NON è descritto dall'EdS.

**Lezione Associata:** [[6.Principi Fondativi della meccanica quantistica]]