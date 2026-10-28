
Consideriamo $N$ variabili aleatorie $x_{1},x_{2},\dots,x_N$ (consideriamole per semplicità indipendenti e identicamente distribuite), con valore medio $<x> = \mu$ e varianza $\sigma^2$.
Prendiamo la media aritmetica $Y_{N}=\frac{1}{N}\sum^\infty_{i=1}x_{i}$. La media così definita è tale che $\sigma_{Y_{N}}^2=\frac{\sigma^2}{N}$.
Per $N\gg{1}$ il valore di $Y_{N}$ converge al valore medio della distribuzione. 
$$
	\lim_{ N \to \infty } Y_{N}=\mu
$$
Per dimostrare il risultato è necessario sfruttare la disuguaglianza di Chebychev:
$$
	P(|x- \langle x \rangle|\geq\varepsilon)\leq \frac{\sigma^2}{\varepsilon^2}
$$
Questa è la probabilità che $x$ si discosti dal valore medio di un valore maggiore di $\varepsilon$.

**Dim della disuguaglianza:**
$$
	\begin{aligned}
	P(|x-\langle x \rangle|\leq\varepsilon)&=\int_{-\infty}^{\langle x \rangle-\varepsilon} p(x)dx + \int^\infty_{\langle x \rangle+\varepsilon} p(x)dx\\
	 &\leq \int^{\langle x \rangle-\varepsilon}_{-\infty} \frac{(x-\langle x \rangle)^2}{\varepsilon^2}p(x)dx+\int^\infty_{\langle x \rangle+\varepsilon} \frac{(x-\langle x \rangle)^2}{\varepsilon^2}p(x)dx\\
	 &\leq \int^\infty_{-\infty} \frac{(x-\langle x \rangle)^2}{\varepsilon^2}p(x)dx=\frac{\sigma^2}{\varepsilon^2} \qquad \blacksquare
	\end{aligned}
$$
Sfruttando la disuguaglianza, dimostrare la legge dei grandi numeri diventa banale.
$$
	P(|Y_{N}-\langle Y \rangle|\geq \varepsilon)=P\left( | \frac{1}{N}\sum x_{i}-\langle x \rangle|\geq\varepsilon \right)\leq \frac{\sigma^2_{Y}}{\varepsilon^2}= \frac{\sigma^2_{x}}{N\varepsilon^2}
$$
Questa disuguaglianza vale per ogni valore di $\varepsilon$. 
Facendo il limite per $N\to \infty$ di questa probabilità otteniamo:
$$
\lim_{ N \to \infty } P\left( | \frac{1}{N}\sum x_{i}-\langle x \rangle| \right)=0
$$
Cioè la media aritmetica coincide col valore medio della distribuzione.

**Lezione associata:** [[4.Distribuzioni di Probabilità continue (di variabili aleatorie)]]