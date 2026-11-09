
## Indice dei sottoargomenti

4.1) [[Proprietà dei commutatori]]
4.2) [[Derivazione delle relazioni di indeterminazione]]

## Appunti

Dopo aver postulato lo spazio degli stati fisici, l'interpretazione statistica e la corrispondenza tra osservabili ed operatori, è possibile parlare del principio di indeterminazione.
Dati i 3 postulati precedenti, questo può essere fatto sotto forma di Teorema e non più di postulato.
Prima però dobbiamo fare alcune considerazioni ulteriori.
- In uno stato $\ket{\alpha}$ le osservabili $a$ e $B$ hanno ENTRAMBE valori definiti se e solo se $\ket{\alpha}$ è autostato sia di $\hat{A}$ che di $\hat{B}$:
$$
	\hat{A}\ket{\alpha} = a_{\alpha} \ket{\alpha}  \qquad \hat{B}\ket{\alpha} =b_{\alpha}\ket{\alpha} 
$$
  Infatti, immaginando di avere un sistema preparato nello stato $\ket{\alpha}$, e misurando ad esempio $a$, se $\ket{\alpha}$ non fosse autostato di $\hat{B}$, troverei: $\ket{\alpha}=\sum_{n} c_{n}^{(\alpha)}\ket{b_{n}}$ con $c_{n}^{(\alpha)}\neq \delta_{n\alpha}$.
  Pertanto la misura di $B$ avrebbe uno spettro di risultati possibili e non sarebbe definita in $\ket{\alpha}$.
- Più in generale, due osservabili $a$ e $B$ possono essere simultaneamente definite se e solo se ammettono una base di AUTOVETTORI COMUNI, cioè:
$$
	\exists \{ \ket{a_{n},b_{n}}  \}\; / \;\begin{cases}
	\hat{A}\ket{a_{n},b_{n}}=a_{n}\ket{a_{n},b_{n}} \\
	\hat{B} \ket{a_{n},b_{n}} =b_{n}\ket{a_{n},b_{n}}  
	\end{cases} \quad \text{e} \quad \forall \alpha \in \mathcal{H},\quad\ket{\alpha} =\sum_{n,m} c_{n,m}^{(\alpha)}\ket{a_{n},b_{m}} 
$$
  Infatti in tal caso, una misura di $a$ non preclude mai una misura di $B$, perchè misurando $\hat{A}$ vado a porre il sistema in un autostato di $\hat{A}$ che è sempre anche autostato di $\hat{B}$ e la misura di $\hat{B}$ è definita senza andare a modificare lo stato.
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
Nel caso di $a_{n}$ è degenere, cioè $\hat{A}\ket{nl}=a_{n}\ket{nl}$ con $l=1,\dots d_{n}$ e posso sempre trovare una base di autostati di $\hat{B}$, cioè: $\exists \{ \ket{nk},\; k=1,\dots,d_{n} \}\, / \, \ket{nk}=\sum_{l=1}^{d_{n}}c_{l}^{(k)}\ket{nl}$ con $\hat{B}\ket{nk}=b_{k}\ket{nk}$. E ho "completato" la dimostrazione.

### Proprietà dei commutatori

Gli operatori lineari su $\mathcal{H}$ costituiscono un'algebra, con l'operazione di commutazione. Per questo motivo è importante andare a studiare le proprietà dei commutatori.
Le seguenti proprietà sono ovvie:

- Antisimmetria: $[A,B]=-[B,A]$. Possiamo anche definire l'ANTI-COMMUTATORE, che è invece simmetrico: $\{ A,B \}=AB+BA$
- Linearità: $[A,B+C]=[A,B]+[B,C]$
- Commutatatore tra prodotti: $[A,BC]=[A,B]C+B[A,C]$
- Identità di Jacobi: $[A,[B,C]]+[C,[A,B]]+[B,[C,A]]=0$
- Hermeticità: In modo analogo a quanto trovato per spazi di dimensione finita, il prodotto di due operatori Hermitiani non è Hermitiano, in generale:
  $(AB)^{\dagger}=B^{\dagger}A^{\dagger}\implies \text{ se } A^{\dagger}=A, \;B^{\dagger}=B;\quad (AB)^{\dagger}=BA$. 
  Ne segue che se $A=A^{\dagger}$ e $B=B^{\dagger}$, posto $[A,B]=iC$ e $\{ A,B \}=D$, 
  si ha $C=C^{\dagger}$ e $D=D^{\dagger}$.)

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

### Derivazione delle relazioni di indeterminazione

Prendiamo 2 operatori autoaggiunti $A$ e $B$ che rappresentano 2 osservabili fisiche $a,b$.
autoaggiunti dunque:
$$
	A=A^{\dagger},\quad B=B^{\dagger}, \qquad D(A)=D(A^{\dagger}), \quad D(B)=D(B^{\dagger})
$$
Pertanto, se $[A,B]=iC\implies C=C^{\dagger}(\neq0)$.
Consideriamo anche uno stato $\ket{\alpha}\in \mathcal{H}$ t.c. $\{ \ket{\alpha}, A\ket{\alpha}, B\ket{\alpha} \}\in D(A)\cap D(B)$ ( richiedo che appartenga all'intersezione dei domini perchè voglio poter applicare gli operatori (anche in sequenza) senza uscire da $\mathcal{H}$.)
Mi interessano operatori centrati in $0$, definiamo allora dei nuovi operatori.
Definisco un operatore $\tilde{A}_{\alpha}=A-\langle A \rangle_{\alpha}=A-\langle \alpha|A|\alpha \rangle$.
Faccio lo stesso con B: $\tilde{B}_{\alpha}=B-\langle B \rangle_{\alpha}=B-\bra{\alpha}B\ket{\alpha}$.
Ho ottenuto 2 nuovi operatori tali che:
$$
	\langle \tilde{A}_{\alpha} \rangle _{\alpha}= \langle A-\langle A \rangle _{\alpha} \rangle _{\alpha}= \langle A \rangle _{\alpha}-\langle A \rangle _{\alpha}=0
$$
e idem per $\langle \tilde{B}_{\alpha} \rangle$.
**Oss:** sommare o togliere operatori costanti non comporta una variazione sul commutatore:
$$
	[\tilde{A}_{\alpha},\tilde{B}_{\alpha}]=[A,B]=iC
$$
Studiare il valore medio del quadrato è molto più interessante.
$$
	\begin{aligned}
	\langle \tilde{A}^2_{\alpha} \rangle &=\langle (A-\langle A \rangle _{\alpha})^2 \rangle _{\alpha}=\langle A^2+\langle A \rangle ^2_{\alpha}-2\langle A \rangle _{\alpha}A \rangle _{\alpha}=\\
	&=\langle A^2 \rangle _{\alpha}+\langle A \rangle _{\alpha}^2-2 \langle A \rangle ^2_{\alpha}=\langle A^2 \rangle _{\alpha}-\langle A \rangle ^2_{\alpha}=(\Delta_{\alpha}A)^2
	\end{aligned}
$$
e idemo: $\langle \tilde{B}_{\alpha}^2 \rangle_{\alpha}=(\Delta_{\alpha}B)^2$.
Costruisco una famiglia a 1 parametro di operatori:
$$
	O_{\alpha}(\lambda)\equiv \tilde{A}_{\alpha}+i\lambda \tilde{B}_{\alpha} \qquad\lambda\in \mathbb{R}
$$
Osserviamo che l'operatore così costruito NON è hermitiano:
$$
	O^{\dagger}_{\alpha}(\lambda)=\tilde{A}_{\alpha}-i\lambda \tilde{B}_{\alpha} \qquad
$$
per $\ket{\alpha}\in D(A)\cap D(B) \implies O_{\alpha}(\lambda)\ket{\alpha}\in \mathcal{H}$. Dunque $O_{\alpha}(\lambda)$ è normalizzabile.
Dunque:
$$
	\begin{aligned}
	0\leq \lVert O_{\alpha}(\lambda) \rVert &=\bra{\alpha} O^{\dagger}_{\alpha}(\lambda)O_{\alpha}(\lambda)\ket{\alpha} \qquad \forall \lambda \in \mathbb{R}\\
	&=\bra{\alpha} (\tilde{A}_{\alpha}-i\lambda\tilde{B}_{\alpha})(\tilde{A}_{\alpha}+i\lambda \tilde{B}_{\alpha})\ket{\alpha} =\bra{\alpha} \tilde{A}^2_{\alpha}\ket{\alpha} +\lambda^2\bra{\alpha} \tilde{B}_{\alpha}\ket{\alpha} +i\lambda \bra{\alpha} [\tilde{A},\tilde{B}]\ket{\alpha} =\\
	&=\langle \tilde{A}^2_{\alpha} \rangle_{\alpha}+\lambda^2 \langle \tilde{B}^2_{\alpha} \rangle _{\alpha}-\lambda \langle C \rangle _{\alpha}=(\Delta_{\alpha} A)^2+\lambda^2(\Delta_{\alpha}B)^2-\lambda \langle C \rangle _{\alpha} 
	\end{aligned}
$$
Abbiamo ottenuto:
$$
	(\Delta_{\alpha} A)^2+\lambda^2(\Delta_{\alpha}B)^2-\lambda \langle C \rangle _{\alpha} \geq 0
$$
è una parabola in $\lambda$, rivolta verso l'alto. Questa parabola è $\geq 0$ solo se non interseca mai l'asse reale, cioè $b^2-4ac\leq 0$.
Dunque:
$$
	\langle C \rangle _{\alpha}^2-4 (\Delta_{\alpha}B)^2(\Delta_{\alpha}A)^2\leq0 \implies \Delta_{\alpha}A \cdot \Delta_{\alpha }B \geq \frac{1}{2} |\langle C \rangle _{\alpha}|
$$
E abbiamo ottenuto una:
>[!summary] **Relazione di indeterminazione in generale**
>
>$$
>	\Delta_{\alpha}A\cdot \Delta_{\alpha}B \geq \frac{1}{2} |\langle -i[A,B] \rangle _{\alpha}|
>$$

**Osservazioni**:
- Se $[A,B]=0$ non ci sono vincoli
- $[x,p]=i\hbar\implies \Delta_{\alpha}x\cdot \Delta_{\alpha}p\geq \frac{\hbar}{2}$, per qualunque stato $\ket{\alpha}$.

Come posso caratterizzare gli stati che minimizzano la relazione di indeterminazione? Ovvero, quali sono gli stati per cui $\Delta_{\alpha}A\cdot \Delta_{\alpha}B=\frac{1}{2} |\langle -i[A,B] \rangle|$?
$$
	\ket{\alpha} \quad / \quad \lVert O_{\alpha}(\lambda)\ket{\alpha} \rVert =0 
$$
Questo succede per $\lambda=\lambda_{min}$ dove $\lambda_{min}$ è la soluzione a $b^2-4ac=0$, cioè:
$$
	\lambda=-\frac{b}{2a}= \frac{\langle -i[A,B] \rangle_{\alpha} }{2(\Delta_{\alpha}B)^2} 
$$
Ricordiamo che in $\mathcal{H}$, $\lVert O_{\alpha}(\lambda)\ket{\alpha} \rVert=0\iff O_{\alpha}(\lambda)\ket{\alpha}=0$. Dunque:
$$
	O_{\alpha}(\lambda)\ket{\alpha} =[A-\langle A \rangle _{\alpha}+i\lambda_{min} (B-\langle B \rangle _{\alpha})]\ket{\alpha}=0 
$$
Passiamo alla funzione d'onda:
$$
	\implies \left[ -i (A_{\text{Op. diff}}- \langle A \rangle _{\alpha} )+ \frac{\langle -i[A,B] \rangle _{\alpha}}{2(\Delta_{x}B)^2}(B_{\text{Op. diff.}}-\langle B \rangle _{\alpha}) \right] \psi_{\alpha}(\vec{r})=0
$$
è un'equazione differenziale.
Prendiamo:
$$
	\begin{aligned}
	A&\to p_{x} \implies A_{\text{Op. diff.}}=-i\hbar \frac{d}{dx}\\
	B&\to x \implies B_{\text{Op. diff.}} = x
	\end{aligned}
$$
Pertanto l'equazione diventa:
$$
	\left[ -i \left( -i\hbar \frac{d}{dx} - \langle p_{x} \rangle _{\alpha} \right)-\frac{\hbar}{2(\Delta_{\alpha}x)^2}(x-\langle x \rangle _{\alpha}) \right]\psi_{\alpha}(x)=0
$$
La sappiamo risolvere per separazione di variabili:
$$
	\frac{d\psi_{\alpha}}{dx} =\left( \frac{i}{\hbar} \langle p_{x} \rangle _{\alpha}- \frac{x-\langle x \rangle _{\alpha}}{2(\Delta_{\alpha}x)^2} \right)\psi_{\alpha}(x)
$$
La soluzione è:
$$
	\psi_{\alpha}(x)=N\exp\left[ -\frac{(x-\langle x \rangle _{\alpha})^2}{4(\Delta_{\alpha}x)^2} \right] e^{ \frac{i}{\hbar }\langle p_{x} \rangle_{\alpha}x }
$$
Abbiamo verificato che la funzione che minimizza l'incertezza è il pacchetto gaussiano.

**Lezione Associata**: [[6.Principi Fondativi della meccanica quantistica]]