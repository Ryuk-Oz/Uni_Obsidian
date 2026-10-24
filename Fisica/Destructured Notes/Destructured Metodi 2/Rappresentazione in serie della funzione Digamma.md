
**ESSENZIALE:** [[Rappresentazione integrale della funzione Digamma]], [[Definizione e proprietà della funzione Digamma]]


Partendo dalla rappresentazione integrale è possibile scrivere una rappresentazione in serie della funzione Gamma.

Parto da:
$$
		\psi(z)=-\gamma+\int^1_{0} \frac{dw}{w}\, \frac{w-w^z}{1-w}=-\gamma+\int_{0}^1 dw\, \frac{1-w^{z-1}}{1-w}
$$
$$
	\frac{1}{1-x}=\sum_{k=0}^\infty x^k
$$
è uniformemente convergente quindi posso integrare termine a termine
$$
	
	\begin{aligned}
	\psi(z)&=-\gamma+\sum^\infty_{k=0} \int^1_{0} dx\, (1-x^{z-1})x^k=-\gamma+\sum^\infty_{k=0}\left( \int^1_{0} dx\, x^k -\int^1_{0} dx\, x^{k+z-1}\right)=\\
	&=-\gamma+\sum^\infty_{k=0}\left[ \frac{x^{k+1}}{k+1}|_{_{0}}^{^1} -\frac{x^{k+z}}{k+z}|^{^1}_{_{0}}\right]=-\gamma+\sum^\infty_{k=0}\left( \frac{1}{k+1} - \frac{1}{k+z} \right)=\\
	&=-\gamma-\frac{1}{z}+\sum^\infty_{k=1}\left[ \frac{1}{k}-\frac{1}{k+z} \right]=-\gamma-\frac{1}{z}+\sum^\infty_{k=1} \frac{z}{k(k+z)}
	\end{aligned}
$$
La serie converge a causa della differenza. Presi separatamente la serie diverge. Questo si vede bene alla fine. La serie tutta insieme va come $\frac{1}{k^2}$.
Da qua si notano subito le singolarità di $\psi$ in $z=0,-1,-2\dots$

Questa forma in serie ci permette di scrivere una nuova rappresentazione per la funzione $\Gamma$.
Integriamo la $\psi$ nel seguente modo:
$$
	\begin{aligned}
		\int^z_{0} \psi(w+1) dw &= \int^z_{0} dw \frac{d}{dw}\{ \log \Gamma(w+1) \}=[\log \Gamma(w+1]^{^z}_{_{0}}=\log \Gamma(z+1)-\log \Gamma(1)\\
		&=\int^z_{0} dw\, \left( -\gamma+\sum^\infty_{n=0} \left( \frac{1}{n+1}-\frac{1}{n+1+w} \right) \right)=\\
		&=-\gamma z+\sum^\infty_{n=0} \left( \frac{z}{n+1}-\log\left( \frac{n+1+z}{n+1} \right) \right)=-\gamma z+\sum^\infty_{n=1}\left( \frac{z}{n}-\log\left( \frac{n+z}{n} \right) \right)=\\
		&=-\gamma z+\sum^\infty_{n=1} \left( \frac{z}{n}-\log\left( 1+\frac{z}{n} \right) \right)=-\gamma z+\sum^\infty_{n=1} \log\left[ e^{ z/n }\left( 1+\frac{z}{n} \right)^{-1} \right]\\
		\implies \log\Gamma(z+1)&=-\gamma z +\sum^\infty_{n=1} \log\left[ e^{ z/n }\left( 1+\frac{z}{n} \right)^{-1} \right]=e^{ -\gamma z }\prod^\infty_{n=1} e^{ z/n } \left( 1+\frac{z}{n} \right)^{-1}
	\end{aligned}
$$
Da qua si possono ricavare facilmente tutte le proprietà della $\Gamma$.

**OSS:** molte delle rappresentazioni che abbiamo trovato si possono usare per calcolare la costante $\gamma$

**Lezione Associata:** [[5. Funzione Digamma]]