
Consideriamo $X$, variabile aleatoria. Sia $p_{X}(x)$ la densità di probabilità associata a questa variabile. (Dunque $p_{X}(x)dx=P[x\leq X\leq x+dx]$).
Sia $y=f(x)$ una qualunque funzione invertibile. Qual è la densità di probabilità $p_{Y}(y)$?

![[Pasted image 20261007152600.png|532]]

Anche cambiando variabile la probabilità finale deve restare invariata, dunque:
$$
	P[x\leq X\leq x+dx]=P[y\leq Y\leq y+dy] \implies p_{X}(x)dx=p_{Y}(y)dy
$$
a questo punto sfruttiamo i teoremi dell'analisi classica:
$$p_{Y}(y)=p_{X}(x) | \frac{dx}{dy}| =p_{X}(x) \frac{1}{|f'(x)|}$$
In più dimensioni facciamo uso del determinante del Jacobiano, come sempre.

Facciamo subito un esempio pratico. Partiamo dalla Gaussiana: $p_{X}(x)=\frac{1}{\sqrt{ 2\pi }}e^{ -x^2/2 }$.
Consideriamo $y=x^2=f(x) \implies f'(x)=2x=2 \sqrt{ y }$ e applichiamo quanto appena detto.
$$
	p_{Y}(y)=\frac{1}{\sqrt{ 2\pi }}e^{ -y/2 } \frac{1}{2\sqrt{ y }}=\frac{1}{2\sqrt{ 2\pi y }}e^{ -y/2 }
$$
e abbiamo ottenuto la distribuzione $\chi^2$ con $k=1$.

![[Pasted image 20261007153305.png]]

**Lezione Associata:** [[4.Distribuzioni di Probabilità continue (di variabili aleatorie)]]