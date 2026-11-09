
Dimostrazioni/spiegazioni della legge di Belford

Abbiamo già discusso il fatto che la legge di Belford debba essere una legge invariante di scala, e di come la distribuzione apparentemente più naturale, la distribuzione uniforme, non è invariante di scala.
Come posso ristabilire l'invarianza di scala?
La distribuzione uniforme è invariante rispetto a somme (traslazioni), come passo dal prodotto alla somma? Uso il logaritmo.
$$
	Y\equiv \log_{10}(X)=\frac{\ln x}{\ln_{10}}
$$
se $Y$ è distribuito uniformemente, allora è invariante per somma e $X$ è invariante di scala!
$$
	X\to \lambda X \qquad y\to \log(\lambda X)= \log_{10}(\lambda)+\log_{10}(X)=Y+\text{cost}
$$
Qual è la densità della $x$?
La densità di probabilità della $Y$ è costante, $q(Y)=c$
$$
	p(x)dx=c dx \implies p(x)=c \frac{dx}{dy}=\frac{c}{x\ln(10)}
$$
Dunque:
$$
	P(d=1)=\int_{1}^2 p(x)dx = \frac{c}{\ln 10} \int_{1}^2 \frac{dx}{x}\propto \ln 2-\ln 1
$$
e:
$$
	P(d)\propto \ln(d+1)-\ln(d)=\ln\left( \frac{d+1}{d} \right)
$$
E abbiamo ritrovato la legge di Belford.

Ultima applicazione delle catene di Markov.

Modello di Wright-Fisher (~1930), ripreso da kimura negli anni 70

Si tratta di un modello che si occupa di **genetic drift**.

Consideriamo una popolazione di $N$ individui con un gene che può avere 2 stati (un allele), A e B.

In ogni istante ho $k(t)$ individui A e $N-k(t)$ individui B. E ho come probabilità di estrazione rispettivamente:
$$
	p_{A}=\frac{k}{N} \qquad p_{B}= \frac{N-k}{N}
$$
e probabilità di saltare da uno stato $k$ a uno stato $k'$ data da:
$$
\begin{aligned}
P(k(t)\to k'(t+1))&=\binom{N}{k'(t+1)} p_{A}^{k'(t+1)} p_{B}^{N-k'(t+1)} = \\
&=\binom{N}{k'(t+1)} \left( \frac{k(t)}{N} \right)^{k'(t+1)}\left( \frac{N-k(t)}{N} \right)^{N-k'(t+1)} = W_{k,k'}
\end{aligned}
	
$$
Si tratta di un random walk in cui ogni salto non è più necessariamente di uno, bensì avviene un rimescolamento e posso saltare anche molto lontano.

Vediamo dove va a finire un random walk di questo tipo, cioè cerchiamo la distribuzione stazionaria: 
$$
	\vec{\pi} = \vec{\pi} \cdot W
$$
$$
	\pi_{i} = \sum_{j} \pi_{j} W_{ji}
$$
Verifichiamo che $\vec{\pi}=(a,0,0,0,\dots, 1-a)$.
Cioè $\pi_{0}=a$, $\pi_{N}=1-a$ e tutti gli altri sono nulli.
Cioè alla fine tutti gli alleli saranno di tipo $A$ o $B$.
Verifichiamo che la $\vec{\pi}$ appena descritti soddisfi la Kolmogorov Backward
$$
	\begin{cases}
	\pi_{0} = \sum_{j} \pi_{j} W_{j0}=\pi_{0}W_{00}+\pi_{n}W_{n0} \\
	0=\pi_{i}=\sum_{j} \pi_{j W_{ji}} =\pi_{0} W_{0k}+\pi_{N}W_{Nk} \quad \forall i \neq 0,N \\
	\pi_{N}= \pi_{N}W_{NN} + \pi_{0}W_{0N}
	\end{cases}
$$
$$
	W_{00}=1, W_{NN}=0
$$
Sostituendo troviamo (verifica a casa)
$$
	\begin{cases}
	\pi_{0}=\pi_{0} \\
	\pi_{i}=\sum_{j} \pi_{j W_{ji}} =0 \quad \forall i \neq 0,N \\
	\pi_{N}=\pi_{N}
	\end{cases}
$$
Dunque $\vec{\pi}=(a , \dots, 1-a)$ soddisfa la kolmogorov backward.

$\langle k(t) \rangle$ è costante, il numero medio di individui di tipo A è costante.
$\langle k(t+1) \rangle = \sum_{k=0}^N k p_{k} (t+1) =\sum_{k=0}^Nk \sum_{j} p_{j}(t)W_{jk}=\sum_{j}^N p_{j}(t)\sum_{k=0}^Nk W_{jk}$.

Vedi appunti giulia



Esercizio simil esame:

Catena di Markov a 2 stati con matrice:
$$
	W=\begin{pmatrix}
	\frac{1}{4} & 0 & \frac{3}{4} \\
	\frac{1}{4} & \frac{1}{2} & \frac{1}{4} \\
	\frac{1}{2} & 0 & \frac{1}{2}
	\end{pmatrix}
$$
Calcolare la probabilità di andare in 2 passi da $1$ a $2$:
$$
	W^{(2)}_{12}=\sum_{j}W_{1j} W_{j_{2}}=W_{11}W_{12}+W_{12}W_{12}+W_{13}+W_{32}=0
$$
Da 2 a $2$:
$$
	W_{22}^{(2)}= \dots = \frac{1}{4}
$$
da 1 a 1:
$$
	W_{11}^{(2)}=\dots=\frac{7}{16}
$$
Prova a casa con disegno.
Calcolare la distribuzione invariante.
$$
	\pi_{i}=\sum_{j}\pi_{j} W_{ji}
$$
$$
	\begin{cases}
	\pi_{1}=\pi_{1}\cdot \frac{1}{4}+\pi_{2} \cdot \frac{1}{4}+\pi_{3} \cdot \frac{1}{2} \\
	\pi_{2} = \pi_{1} \cdot\frac{1}{2} \\
	\pi_{3}+\pi_{2}+\pi_{1}=1
	\end{cases}
$$
risolvendo si trova:
$$
	\vec{\pi}=\left( \frac{2}{5},0, \frac{3}{5} \right)
$$

Esercizio 2: probabilità poker alla prima mano

5 carte su 40. Sia $P_{k}$ la probabilità di estrarre $k$ assi.
$$
	P_{0}= \frac{36}{40} \frac{35}{39} \frac{34}{38} \frac{33}{37} \frac{32}{36} \simeq 0.57
$$
Probabilità di $k>0$ è $1-P_{0}$.
$$
	P_{1}=\left( \frac{4}{40} \frac{36}{39} \frac{35}{38} \frac{34}{37} \frac{33}{36}\right)\cdot 5 =0.358
$$
Moltiplico per $5$ perchè l'asso potrebbe essere in qualunque posizione
$$
	P_{2} = \left( \frac{4}{40} \frac{3}{39} \frac{36}{38} \frac{35}{37} \frac{34}{36} \right) \binom{5}{2} = 0,0651
$$
$$
	P_{4}=\left( \frac{4}{40} \frac{3}{39} \frac{2}{38} \frac{1}{37} \frac{36}{36}\right) \binom{5}{4}=
$$

