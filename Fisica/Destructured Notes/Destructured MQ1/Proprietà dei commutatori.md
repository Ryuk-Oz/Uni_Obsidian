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

**Lezione Associata:** [[Commutatori e relazioni di indeterminazione]]