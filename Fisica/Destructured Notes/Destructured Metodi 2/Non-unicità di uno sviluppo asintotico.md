
**Essenziale:** [[Definizione di sviluppo asintotico]]

Data una funzione $f(z)$ lo sviluppo asintotico per $z\to z_{0}$ con $z\in D$ è unico.
La dimostrazione è facile sfruttando la definizione di resto n-esimo.
$$
	R_{n}(z)=f(z)-\sum_{l=0}^{n-1} a_{l}\, \varphi_{l}(z)=o(\varphi_{n-1})
$$
Se lo sviluppo è unico, i coefficienti assumono un valore univoco. Per dimostrarlo, iniziamo calcolando il resto 1-esimo di $f(z)$:
$$
	R_{1}(z)=f(z)-a_{0}\varphi_{0}=o(\varphi_{0})
$$
Cioè:
$$
	\underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)-a_{0}\varphi_{0}(z)}{\varphi_{0}(z)}=0 \implies \underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)}{\varphi_{0}(z)}=a_{0}
$$
Analogamente:
$$
	R_{2}=f(z)-a_{0}\varphi_{0}(z)-a_{1}\varphi_{1}(z)=o(\varphi_{1}(z))
$$
Cioè:
$$
		\underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)-a_{0}\varphi_{0}(z)-a_{1}\varphi_{1}(z)}{\varphi_{1}(z)}=0 \implies \underset{z\in D}{\lim_{ z \to z_{0} } } \frac{f(z)-a_{0}\varphi_{0}}{\varphi_{1}(z)}=a_{1}
$$
E così via:
$$
	a_{n}=\lim_{ z \to z_{0} } \frac{\left( f-\sum^{n-1}_{l=0} a_{l}\varphi_{l} \right)}{\varphi_{n}}
$$

Tuttavia non vale il contrario. Preso uno sviluppo asintotico, non possiamo ricostruire $f$ in maniera univoca.

Facciamo un esempio:
$z\to \infty$ e $D=\left\{  z\in\mathbb{C} \, / \, |argz|<\frac{\pi}{2}-\delta \right\}$ (semipiano positivo con assi verticali leggermente inclinati).
![[Pasted image 20261102145733.png]]
Prendo come successione asintotica: $\left\{  \varphi_{l}=\frac{1}{z^l}  \right\}$.
Considero $e^{ -z }$:
$$
	a_{0}=\underset{z\in D}{\lim_{ z \to \infty } } e^{ -z }=0 \qquad a_{1}=\underset{z\in D}{\lim_{ z \to \infty } } \frac{e^{ -z }}{\frac{1}{z}}=0
$$
Continuando si trova:
$$
	a_{n}=\underset{z\in D}{\lim_{ z \to \infty } } e^{ -z }z^n=0
$$
Dunque: $e^{ z }\sim{0}$ per $z\to \infty$, $z\in D$.
Dunque, considerando $f(z)$:
$$
	f(z)=\sum^\infty_{l} a_{l} \frac{1}{z^l}
$$
posso sempre trovare una funzione $g(z)=f(z)+kz^m e^{ -z }\sim \sum^\infty_{l=0} a_{l} \frac{1}{z^l}$ per $z\to \infty$, $z \in D$.
In fisica, termini di questo tipo, che non emergono da uno sviluppo asintotico, sono noti come termini non perturbativi.

**Lezione Associata:** [[7. Sviluppi Asintotici]]