
**Utile da sapere:** [[Moto Browniano]]

Il modello del random walk è un semplice modello di processo stocastico diffusivo e discreto.
Iniziamo con lo studio di un modello unidimensionale per poi studiare modelli a dimensione generica.

![[Pasted image 20261026155649.png]]

$$
	\begin{aligned}
	&x_{n+1}=x_{n}+v_{n}\\
	&v_{n}=\pm1 \quad \text{con probabilità (scorrelata) } p=\frac{1}{2}\\
	&x_{0}=0 \quad x_{n}=\sum^n_{k=1}v_{k}
	\end{aligned}
$$
Studiamo i momenti della distribuzione:
$$
	\langle x_{n} \rangle =\sum^n_{k=1} \langle v_{k} \rangle =0
$$
La posizione media della particella è $0$. Cosa succede invece per la varianza:
$$
	\sigma^2=\langle x_{n}^2 \rangle = \langle \left( \sum^n_{k=1} v_{k} \right)^2 \rangle = \langle \sum^n_{i,j=1} v_{i}v_{j} \rangle =  \langle \sum_{i} v_{i} \sum_{j} v_{j} \rangle=\sum_{i,j=1}^n \langle v_{i} v_{j} \rangle
$$
Pocihè gli eventi $v_{n}$ sono tra loro scorrelati: $\langle v_{j} v_{i} \rangle=\langle v_{i} \rangle\langle v_{j} \rangle=\delta_{ij}$. Dunque:
$$
	\langle x^2_{n} \rangle =\sum^n_{i} \langle v_{i}^2 \rangle =n
$$
$n$ è il numero di passi, che corrisponde al tempo, la distanza dal centro aumenta in modo lineare al tempo, dunque si tratta di un processo diffusivo.

Qual è la probabilità di trovarci in un certo stato $x_{n}$?
Per trovarci nello stato $x_{n}=k$ devo aver effettuato $\frac{n}{2}+\frac{k}{2}$ passi "$+1$" e $\frac{n}{2}-\frac{k}{2}$ passi "$-1$".
$$
	p(x_{n}=k)=\binom{n}{\frac{n+k}{2}} \left( \frac{1}{2} \right)^{(n+k)/2} \left( \frac{1}{2} \right)^{(n-k)/2}
$$
Sviluppando il conto con l'approssimazione di Stirling otteniamo:
$$
	p(x_{n})= \frac{1}{\sqrt{ 2\pi n }} e^{ -x_{n}^2/(2n) }
$$
Cioè una gaussiana che si allarga nel tempo.
Se invece il dominio fosse limitato la situazione cambierebbe e parleremmo di Random Walk con barriere.

**Lezione Associata:** [[5. Moto Browniano e Random Walk]]