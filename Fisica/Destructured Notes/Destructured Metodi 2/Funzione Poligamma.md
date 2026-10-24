
**ESSENZIALE:** [[Rappresentazione integrale della funzione Digamma]]

**Idea:** Possiamo generalizzare la funzione Digamma a derivate logaritmiche superiori, e otteniamo la funzione poligamma.
$$
	\psi^{(k)}=\frac{d^k}{dz^k} \log \Gamma(z)=\frac{d^{k-1}}{dz^{k-1}}\psi (z)
$$
Molte delle rappresentazioni integrali di $\psi$ sono generalizzabili per la funzione poligamma andando a introdurre le derivate superiori.
Ad esempio:
$$
	\psi^{(k)}=\sum^\infty_{n=0} \frac{(-1)^{k+1}(k+1)!}{(n+z)^{k+1}}
$$
$$
	\psi^{(k)}=-\int^1_{0} dx\, \frac{x^{z-1}(\log z)^k}{1-x}
$$
Il termine costante $\frac{1}{n+1}$ scompare derivando!

Molto spesso possiamo ricondurre serie infinite a somme di funzioni $\psi$.
Ad esempio, supponiamo di dover sommare la seguente serie:
$$
\begin{aligned}
\sum^\infty_{k=1} \frac{1}{(k+a)(k+b)}&=\frac{1}{b-a}\sum^\infty_{k=1}\left( \frac{1}{k+a}-\frac{1}{k+b} \right)=\\
&=\frac{1}{b-a}\sum^\infty_{k=1}\left( \frac{1}{k-1+a+1}-\frac{1}{k-1+b-1} \right)=\\
&=\frac{1}{b-a}\sum^\infty_{n=0}\left( \frac{1}{n+a+1}-\frac{1}{n+b+1} \right)=\\
&=\frac{1}{b-a}\sum^\infty_{n=0}\left[ -\gamma+\frac{1}{n+1}-\frac{1}{n+(b+1)}-\left( -\gamma+\frac{1}{n+1}-\frac{1}{n+(a+1)} \right) \right]
\end{aligned}
$$
Ora posso andare ad accoppiare i termini della serie in modo diverso:
$$
	\sum^\infty_{k=1} \frac{1}{(k+a)(k+b)}=\frac{1}{b-a}(\psi(b+1)-\psi(a+1))
$$
Questo è il modo più semplice per andare a sommare la serie perchè non avendola mai spezzata, non ho mai scritto pezzi di serie divergenti.

**Oss:** Non sappiamo ancora come si comporta $\Gamma$ all'infinito. Per farlo dobbiamo aspettare di vedere gli sviluppi asintotici. Ci darà la formula di stirling!

**Lezione Associata:** [[5. Funzione Digamma]]