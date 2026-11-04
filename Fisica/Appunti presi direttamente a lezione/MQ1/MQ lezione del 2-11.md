
Quanta informazione perdiamo se 2 operatori non commutano?

Deriviamo finalmente le relazioni di indeterminazione.

Prendiamo 2 operatori autoaggiunti $A$ e $B$ che rappresentano 2 osservabili fisiche $a,b$.
autoaggiunti dunque:
$$
	A=A^{\dagger},\quad B=B^{\dagger}, \qquad D(A)=D(A^{\dagger}), \quad D(B)=D(B^{\dagger})
$$
Pertanto, se $[A,B]=iC\implies C=C^{\dagger}(\neq0)$.
Consideriamo anche uno stato $\ket{\alpha}\in \mathcal{H}$ t.c. $\{ \ket{\alpha}, A\ket{\alpha}, B\ket{\alpha} \}\in D(A)\cap D(B)$ perchè voglio poter applicare gli operatori (anche in sequenza) senza uscire da $\mathcal{H}$.
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

**Osservazioni varie**:
- Se $[A,B]=0$ non ci sono vincoli
- $[x,p]=i\hbar\implies \Delta_{\alpha}x\cdot \Delta_{\alpha}p\geq \frac{\hbar}{2}$, per qualunque stato $\ket{\alpha}$.

Come posso caratterizzare gli stati che minimizzano la relazione di indeterminazione? Ovvero, quali sono gli stati per cui $\Delta_{\alpha}A\cdot \Delta_{\alpha}B=\frac{1}{2} |\langle -i[A,B] \rangle|$?
$$
	\ket{\alpha} \, / \quad \lVert O_{\alpha}(\lambda)\ket{\alpha} \rVert =0 
$$
Questo succede per $\lambda=\lambda_{min}$ dove $\lambda_{min}$ è la soluzione a $b^2-4ac=0$, cioè:
$$
	\lambda=-\frac{b}{2a}= \frac{\langle -i[A,B] \rangle_{\alpha} }{2(\Delta_{\alpha}B)^2} 
$$
Ricordiamo che in $\mathcal{H}$, $\lVert O_{\alpha}(\lambda)\ket{\alpha} \rVert=0\iff O_{\alpha}(\lambda)\ket{\alpha}=0$. Dunque:
$$
	O_{\alpha}(\lambda)\ket{\alpha} =[A-\langle A \rangle _{\alpha}+i\lambda_{min} (B-\langle B \rangle _{\alpha})]\ket{\alpha}=0 
$$
Passiamo alla funzione d'onda (FORMALIZZA I PASSAGGI).
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

### Insiemi completi di osservabili compatibili (ICOC, CSCO in inglese)

- Date $\{ a_{i} \}$, $i=1,\dots,p$ sono compatibili se i corrispondenti operatori commutano (sono cioè simultaneamente misurabili).
$$
	[A_{i},A_{j}]=0 \qquad \forall i,j=1,\dots,p
$$
- Diciamo che $a$ e $b$ sono INDIPENDENTI se la misura di una di esse non determina il risultato di una misura dell'altra. (DIVERSA DALLA DEFINIZIONE DI INDIP: PROBABILISTICA?)
  Se due osservabili sono compatibili e indipendenti $\implies$ ci deve seere degenerazione
  $\exists$ diversi stati $\ket{a_{i}, \cdot}\in$ autovalori diversi di $B$.
  Dunque ha più senso chiamare lo stato non più $\ket{a_{i}}$ ma:
  $\ket{a_{i}}\to\ket{a_{i},b_{i}} \, /\, \begin{cases}A\ket{a_i, b_{j}} =a_{i}\ket{{a_{i}, b_{j}}} \\  B\ket{{a_{i}, b_{j}}}=b_{j} \ket{{a_{i}, b_{j}}}\end{cases}$
- Dato un sistema fisico $S$ gli stati di $\mathcal{H}_{S}$ sono completamente caratterizzati quando ho misurato $p$ osservabili complete e indipendenti e tali da rimuovere la degenerazione.
  In questo caso dico di avere un ICOC.


**Es:** Particella in moto su un cerchio $S^1$, posso fissare il raggio WLOG, ad esempio $R=1$.
$$
	\mathcal{H} \sim L^2(S^1) \qquad x\in[0,2\pi)
$$
Sul cerchio devo richiedere l'ulteriore condizione di periodicità per non avere ramificazioni
Considero:
$$
	\psi_{n}(x) \propto e^{ inx }\quad \text{autofunzioni di } \quad p=-i\hbar \frac{d}{dx}
$$
Achtung! Sto lavorando con degli angoli in realtà. Quindi non è propriamente la quantità di moto.
Dunque:
$$
	-i\hbar \frac{d\psi_{n}}{dx}=\hbar n \psi_{n}(x)\to p_{n}=\hbar n, \; \Delta_{n}p=0
$$
...MA... $\Delta_{n}x\leq 2\pi\implies \Delta_{n}x\cdot \Delta_{n}p=0$ e ho una violazione del principio di indeterminazione.
Il motivo è che $e^{ inx } \not\in D(x)$ perchè $xe^{ inx }$ non è periodico. 
Si tratta di stati che non soddisfano le ipotesi delle relazioni di indeterminazioni, dunque non è un problema.

### Relazione di indeterminazione tra E e t

si può vedere anche:
$$
	\Delta E \cdot \Delta t \geq \frac{\hbar}{2}
$$
"più è piccola l'incertezza su $E$, più tempo ho per misurarla".
Ma ho un problema, $t$ non è un osservabile e non posso associarvi un operatore, allora come calcolo $\Delta t$?
In meccanica non relativistica non misuro mai il tempo, misuro sempre qualcosa ad un dato tempo, $t$ è un parametro.
Abbiamo sempre discusso di $\mathcal{H}$ ad un tempo fissato.


FINIAMO QUESTA COSA DOMANI; ORA VEDIAMO UN'ALTRA ROBA

### Teorema di Ehrenfest

$Q$ osservabile, $Q=Q^{\dagger}$, $\ket{\alpha}\in \mathcal{H}$.
$$
	\begin{aligned}
	\frac{d}{dt}\bra{\alpha} Q\ket{\alpha} =\left( \frac{d}{dt} \bra{\alpha}  \right) Q \ket{\alpha} + \bra{\alpha} \frac{dQ}{dt} \ket{\alpha} +\bra{\alpha}Q \left( \frac{d}{dt} \ket{\alpha} \right) 
	\end{aligned}
$$
A queto punto sfrutto l'eq. di shrodinger:
$$
	i\hbar \frac{d}{dt} \ket{\alpha}  = H \ket{\alpha} 
$$
e:
$$
	-i\hbar \frac{d}{dt} \bra{\alpha}  = \bra{\alpha} HQ \ket{\alpha} 
$$
Dunque:
$$
	\begin{aligned}
	\frac{d}{dt} \langle Q \rangle _{\alpha} = \frac{i}{\hbar} \bra{\alpha} HQ \ket{\alpha} + \langle \frac{ \partial Q }{ \partial t }  \rangle _{\alpha}- \frac{i}{\hbar} \bra{\alpha} QH\ket{\alpha} = \langle  \frac{ \partial Q }{ \partial t }  \rangle _{\alpha} +\frac{i}{\hbar} \langle [H,Q] \rangle _{\alpha}
	\end{aligned}
$$
 Dunque:
 $$
	\frac{d}{dt} \langle Q \rangle _{\alpha} = \langle  \frac{ \partial Q }{ \partial t }  \rangle _{\alpha} +\frac{i}{\hbar} \langle [H,Q] \rangle _{\alpha}
 $$
 Che è totalmente analogo a quello che trovo in meccanica classica:
$$
	\frac{dA}{dt} = \frac{ \partial A }{ \partial t } + \{ A,H \}_{\text{pp}}
 $$
 Ho una corrispondenza biunivoca tra le parentesi di poisson in meccanica classica e il commutatore in meccanica quantistica.
