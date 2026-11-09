
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

**Lezione Associata:** [[Commutatori e relazioni di indeterminazione]]