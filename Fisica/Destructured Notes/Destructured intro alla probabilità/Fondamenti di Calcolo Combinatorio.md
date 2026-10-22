
**Lezione associata:** [[1.Introduzione e concetti base di teoria della probabilità]]
___

Occupiamoci di un ripasso di calcolo combinatorio, utile in molti ambiti dello studio della probabilità.

- **Permutazioni** di $n$ oggetti (con ordine): 
  $$
  	p(n)=n!
  $$
- **Disposizioni** di $k\leq n$ oggetti con ORDINE: 
  $$
  	D(n,k)=\frac{n!}{(n-k)!}
  $$
- **Combinazioni** di $k\leq n$ oggetti SENZA ORDINE: 
  $$
  	C(n,k)=\frac{n!}{(n-k)!\, k!}=\binom{n}{k}
  $$

Facciamo un esempio in cui sfruttiamo quanto fatto fin'ora.
___
**ESEMPIO:** Probabilità di vincita alla ruota.

Immagino di avere $n=90$ numeri e di estrarne $k=5$.

Calcoliamo l'equità del singolo estratto supponendo che la vincita sia $V_{1}=11,23$ volte la posta:
$$
	P(1)=\frac{1}{90}+\frac{1}{89} \frac{89}{90}+ \frac{89}{90} \frac{88}{89} \frac{1}{88}+\dots= \frac{5}{90}=\frac{1}{18}=0,0\bar{5}
$$
Abbiamo sommato la probabilità di estrarre il numero da noi scelto alla prima estrazione alla probabilità di estrarlo alla seconda estrazione moltiplicato per la probabilità di ARRIVARE alla seconda estrazione e così via per le palline successive.
$$
	E_{1}= <V_{1}> = V_{1}\cdot P(1)=0,62
$$
Calcoliamo ora l'equità del doppio estratto con $V_{2}=250$.
Calcoliamo la probabilità di doppio estratto con il calcolo combinatorio, usando la nozione di probabilità frequentista.
$$
	\# \text{ estrazioni possibili}=\binom{90}{5}=\frac{90!}{5!\,85!} 
$$
$$
	\# \text{ estrazioni favorevoli} = \binom{88}{3} = \frac{88!}{3!\,85!}
$$
nel calcolo delle estrazioni favorevoli ho tenuto fissi 2 numeri su 5 (quelli che ho scelto) e ho fatto variare gli altri.
$$
	P(2)= \frac{\# \text{ favorevoli}}{\# \text{ possibili}} = \frac{\binom{88}{3}}{\binom{90}{5}}=\frac{88!}{3!\,85!} \frac{5!\,85!}{90!}=\frac{5\cdot4}{90\cdot 89}=\frac{2}{801}\simeq 0,0025
$$
$$
	E_{2}=0,0025 \cdot 250 \simeq 0,62
$$
e così via per il triplo, il quarto e il quinto estratto.

Per quanto riguarda i fattoriali, si ricorda anche l'approssimazione di Stirling
$$
	n! \sim \sqrt{ 2\pi n }\left( \frac{n}{e} \right)^n, \quad \text{per } n\to \infty
$$