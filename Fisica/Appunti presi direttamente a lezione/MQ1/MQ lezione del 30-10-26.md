
Continuiamo con la discussione inerente i principi fondativi della meccanica quantistica.

3. Interpretazione statistica generalizzata
"Gli autovalori degli opertatori $\hat{A}$ associati alle osservabili $a$ sono tutti e soli i possibili risultati di una misura sperimentale di $a$. Posto che ogni stato $\ket{\alpha}$ può essere espresso nella base degli autostati di $\hat{A}$ (e tale base è ON)".
$$
	\underbrace{\ket{\alpha} =\sum c_{n}^{(\alpha)}\ket{a_{n}} }_{\text{spettro discreto}} \qquad \underbrace{\ket{\alpha} =\int d\sigma\, c_{\alpha}(\sigma) \ket{a_{\sigma}} }_{\text{spettro continuo}}
$$
A questo punto, è possibile interpretare $|c^{(\alpha)}_{n}|^2$ come **probabilità** di ottenere il valore $a_{n}$ effettuando una misura di $a$ sullo stato $\ket{\alpha}$ (per spettro discreto).
Ed è possibile imterpretare $|c_{\alpha}(\sigma)|^2$ come **densità di probabilità** di ottenere il valore $a_{\sigma}$ effettuando una misura di $a$ sullo stato $\ket{\alpha}$.
E si ha che $c_{n}^{(\alpha)}=\langle a_{n}|\alpha \rangle$ e $c_{\alpha}(\sigma)=\langle a_{\sigma}|\alpha \rangle$.

Abbiamo anche già dimostrato che queste probabilità sono normalizzate:
$$
	\left( \sum_{n} |c^{(\alpha)}_{n}|^2 =1=\int d\sigma\, |c_{\alpha}(\sigma)|^2\right)
$$

4. Precisazioni sul processo di misura
La misura di un osservabile $a$ in uno stato $\ket{\alpha}$ in meccanica quantistica implica un processo in 2 fasi.

- **Preparazione**
	Viene identificato lo stato $\ket{\alpha}$. Cioè vengono fatte delle misure preliminari di un insieme di osservabili $\{ a_{1},\dots,a_{p} \}$ sufficienti a caratterizzare univocamente lo stato $\ket{\alpha}$.
	- Per poter fare ciò, devo conoscere lo spazio $\mathcal{H}$ in modo sufficientemente preciso da sapere come $\ket{\alpha}$ possa essere univocamente caratterizzato.
	- Nel caso della meccanica classica, tale conoscenza dello stato $\ket{\alpha}$ corrispondeva ad una determinazione totale di TUTTE le osservabili fisiche. Preso un punto nello spazio delle fasi $\{ q_{i},p_{i} \}$, tutte le funzioni $Q(q_{i},p_{i})$ sono determinate e la loro evoluzione temporale è dettata da $H$.
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

	 Ne concludiamo che la misura (e più generalmente un interazione con un apparato sperimentale esterno e "macroscopico") ha modificato in maniera irreversibile lo stato del sistema $\implies$ il processo di misura NON è descritto dall'EdS.


5. Relazioni di indeterminazione

Dati i punti $1 \sim{4}$ le relazioni di indeterminazione emergono come teoremi anzichè come principi indipendenti. I passi per arrivare al teorema sono i seguenti:

- In uno stato $\ket{\alpha}$ le osservabili $a$ e $B$ hanno ENTRAMBE valori definiti se e solo se $\ket{\alpha}$ è autostato sia di $\hat{A}$ che di $\hat{B}$:
$$
	\hat{A}\ket{\alpha} = a_{\alpha} \ket{\alpha}  \qquad \hat{B}\ket{\alpha} =b_{\alpha}\ket{\alpha} 
$$
  Infatti, immaginando di avere un sistema preparato nello stato $\ket{\alpha}$, e misurando ad esempio $a$, se $\ket{\alpha}$ non fosse autostato di $\hat{B}$, troverei: $\ket{\alpha}=\sum_{n} c_{n}^{(\alpha)}\ket{b_{n}}$ con $c_{n}^{(\alpha)}\neq \delta_{n\alpha}$.
  Pertanto la misura di $B$ avrebbe uno spettro di risultati possibili e non sarebbe pertanto definito in $\ket{\alpha}$.
- Più in generale, due osservabili $a$ e $B$ possono essere simultaneamente definite se e solo se ammettono una base di AUTOVETTORI COMUNI, cioè:
$$
	\exists \{ \ket{a_{n},b_{n}}  \}\; / \;\begin{cases}
	\hat{A}\ket{a_{n},b_{n}}=a_{n}\ket{a_{n},b_{n}} \\
	\hat{B} \ket{a_{n},b_{n}} =b_{n}\ket{a_{n},b_{n}}  
	\end{cases} \quad \text{e} \quad \forall \alpha \in \mathcal{H},\quad\ket{\alpha} =\sum_{n,m} c_{n,m}^{(\alpha)}\ket{a_{n},b_{m}} 
$$
  Infatti in tal caso, una misura di $a$ non preclude mai una misura di $B$, perchè misurando $\hat{A}$ vado a porre il sistema in un autostato di $\hat{A}$ che è sempre anche autostato di $\hat{B}$ e la misura di $\hat{B}$ è dunque definita senza andare a modificare lo stato.
  (In caso di autostati degeneri, lo stato può essere modificato ma rimane in un sottospazio di $\mathcal{H}$ con lo stesso autovalore di $\hat{A}$).
- **Teorema:** due operatori autoaggiunti $\hat{A}$, $\hat{B}$ ammettono una base comune di autovettori se e solo se commutano. Cioè:
$$
	\forall \ket{\alpha} \in \mathcal{H},\quad (\hat{A}\hat{B}-\hat{B}\hat{A})\, \ket{\alpha} \equiv [\hat{A},\hat{B}]\ket{\alpha} =0
$$
  **Dimostrazione:**
	CONDIZIONE NECESSARIA:
	 $\exists \{ \ket{\alpha_{n},\beta_{n}} \}\, / \, \hat{A}\ket{a_{n},b_{n}}=a_{n}\ket{a_{n},b_{n}},\; \hat{B}\ket{a_{n},b_{n}}=b_{n}\ket{a_{n},b_{n}}$  
	 e $\forall \ket{\alpha}\in \mathcal{H}, \, \ket{\alpha}=\sum_{n,m}c^{(\alpha)}_{nm}\ket{a_{n},b_{m}}$.
	 Allora $\forall \ket{a_{n},b_{n}}:\quad (\hat{A}\hat{B}-\hat{B}\hat{A})\ket{a_{n},b_{n}}=(a_{n}b_{n}-b_{n}a_{n})\ket{a_{n},b_{n}}=0$
	CONDIZIONE SUFFICIENTE (caso non degenere):
	 Sia $[\hat{A},\hat{B}]=0$, e $\hat{A}\ket{a_{n}}=a_{n}\ket{a_{n}}$ con ciasun $\ket{a_{n}}$ non degenere (dunque l'autospazione di $a_{n}$ è unidimensionale.)
	 Allora $(\hat{A}\hat{B}-\hat{B}\hat{A})\ket{a_{n}}=0\implies \hat{A}(\hat{B}\ket{a_{n}})=a_{n}\hat{B}\ket{a_{n}}$. Pertanto, $\hat{B}\ket{a_{n}}$ è autostato di $\hat{A}$ appartenente allo stesso autovalore $a_{n}$ dello stato $\ket{a_{n}}$. Se l'autovalore non è degenere ne segue che $\hat{B}\ket{a_{n}}\propto \ket{a_{n}}\implies \exists b\, /\, \hat{B}\ket{a_{n}}=b\ket{a_{n}}$.
	 Dunque gli autostati di $\hat{A}$ (che formano una base ON) sono anche autostati di $\hat{B}$ e i 2 operatori ammettono una base comune di autostati. $\blacksquare$.
Nel caso di a_{n}$ è degenere, cioè $\hat{A}\ket{nl}=a_{n}\ket{nl}$ con $l=1,\dots d_{n}$ e posso sempre trovare una base di autostati di $\hat{B}$, cioè: $\exists \{ \ket{nk},\; k=1,\dots,d_{n} \}\, / \, \ket{nk}=\sum_{l=1}^{d_{n}}c_{l}^{(k)}\ket{nl}$ con $\hat{B}\ket{nk}=b_{k}\ket{nk}$. E ho "completato" la dimostrazione.

**Proprietà dei commutatori**:

Gli operatori lineari su $\mathcal{H}$ costituiscono un'algebra, con l'operazione di commutazione. Per questo motivo è importante andare a studiare le proprietà dei commutatori.
Le seguenti proprietà sono ovvie:

- Antisimmetria: $[A,B]=-[B,A]$. Possiamo anche definire l'ANTI-COMMUTATORE, che è invece simmetrico: $\{ A,B \}=AB+BA$
- Linearità: $[A,B+C]=[A,B]+[B,C]$
- Commutatatore tra prodotti: $[A,BC]=[A,B]C+B[A,C]$
- Identità di Jacobi: $[A,[B,C]]+[C,[A,B]]+[B,[C,A]]=0$
- Hermeticità: In modo analogo a quanto trovato per spazi di dimensione finita, il prodotto di due operatori Hermitiani non è Hermitiano, in generale:
  $(AB)^{\dagger}=B^{\dagger}A^{\dagger}\implies \text{ se } A^{\dagger}=A, \;B^{\dagger}=B;\quad (AB)^{\dagger}=BA$. 
  Ne segue che se $A=A^{\dagger}$ e $B=B^{\dagger}$, posto $[A,B]=iC$ e $\{ A,B \}=D$, 
  si ha $C=C^{\dagger}$ e $D=D^{\dagger}$.

Quando andiamo ad effettuare il calcolo esplicito dei commutatori, lo facciamo facendoli agire su di un vettore, ad esempio:
$$
	[x,p]\psi=-i\hbar x \frac{d\psi}{dt}-\left( -i\hbar \frac{d}{dx} \right)(x\psi)=i\hbar \psi\quad \forall \psi
$$
Quindi scriviamo $[x,p]=i\hbar \mathbb{1}_{\mathcal{H}}$.
Spesso possiamo ridurre il calcolo di un commutatore più complesso al calcolo di questo.
$$
	H= \frac{|\vec{p}|^2}{2m}+V(\vec{r})\implies[\hat{H},\hat{x}]=\frac{1}{2m}[\hat{p}_{x}^2+\hat{p}_{y}^2+\hat{p}_{z}^2,\hat{x}]
$$
$V(\vec{r})$ compare perchè $[\hat{x}, f(\hat{x},\hat{y},\hat{z})]=0$, in quanto $\hat{x},\hat{y},\hat{z}$ agiscono moltiplicativamente.
Ulteriormente ho $[x_{i},p_{j}]=i\hbar\delta_{ij}$, dunque:
$$
	[\hat{H},\hat{x}]=\frac{1}{2m}[\hat{p}_{x}^2,\hat{x}]=\frac{1}{2m}(\hat{p}_{x}[\hat{p}_{x},\hat{x}]+[\hat{p}_{x},\hat{x}]\hat{p}_{x})=-i\hbar \frac{\hat{p}_{x}}{m}
$$
In quest'ultimo esempio ci siamo avvalsi solo delle proprietà e della nostra conoscenza di $[\hat{x},\hat{p}_{x}]$.

Abbiamo detto che se 2 operatori commutano, allora ammettono una base di autovettori comune (e le osservabili associate sono perfettamente definite). 
A questo punto è lecito chiedersi: quanta informazione perdo se 2 operatori non commutano?


