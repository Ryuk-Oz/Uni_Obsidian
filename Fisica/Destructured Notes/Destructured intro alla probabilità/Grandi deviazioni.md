
**Strettamente correlato a:** [[Teorema del limite centrale]]

Occupiamoci dello studio delle code di una distribuzione di probabilità, dove non vale il TLC.
Studiamo cosa succede con un esempio concreto, quello di una moneta truccata:
$$
\begin{cases}
X=1 \qquad \text{probabilità }p \\
X=-1 \qquad \text{probabilità } (1-p)
\end{cases}
$$
$$
	Y_{N}=\frac{1}{N}\sum_{i}^N x_{i}
$$
Calcoliamo la probabilità di avere $k$ lanci positivi in $N$ lanci (e dunque $N-k$ lanci negativi).
$$
	Y_{N}=\frac{1}{N}(k-(N-k))=\frac{1}{N}(2k-N)=\frac{2k}{N}-1
$$
$$
	\begin{aligned}
	P\left( Y_{N}=\frac{2k}{N}-1 \right)&=\frac{N!}{k!(N-k)!}p^k (1-p)^{N-k} \underset{N\gg1}{=}\quad \text{usando l'appr. di Stirling}\\
	&=\frac{\sqrt{ 2\pi N }N^Ne^{ -N }}{\sqrt{ 2\pi k }\,k^ke^{ -k }\sqrt{ 2\pi(N-k) }(N-k)!e^{ -(N-k) }}p^k(1-p)^{N-k}=\\
	\\
	\text{sostituisco} \qquad f&\equiv \frac{k}{N} \qquad e \qquad 1-f\equiv N-\frac{k}{N}\\
	\\
	&=\frac{\sqrt{ N }}{\sqrt{ Nf }} \frac{N^Ne^{ -N }}{(Nf)^{Nf}e^{ -Nf }} \frac{1}{\sqrt{ 2\pi N(1-f) }[N(1-f)]^{N(1-f)}e^{ -N(1-f) }}p^{Nf}(1-p)^{N(1-f)}=\\
	&=\frac{1}{\sqrt{ 2\pi }} \frac{1}{\sqrt{ Nf(1-f) }} \frac{1}{f^{Nf}(1-f)^{N(1-f)}}p^{Nf}(1-p)^{N(1-f)}=\\
	&=\frac{1}{\sqrt{ 2\pi }} \frac{1}{\sqrt{ Nf(1-f) }} \left( \frac{p}{f} \right)^{Nf} \left( \frac{1-p}{1-f} \right)^{N(1-f)}=\\
	&=\frac{1}{\sqrt{ 2\pi }} e^{ -1/2 \log(Nf(1-f)) } e^{ -Nf\log(f/p) } e^{ -N(1-f)\log(\frac{1-f}{1-p}) }
	\end{aligned}
$$
In forma più compatta possiamo scrivere:
$$
	p(Y_{N}=2f-1)=\frac{1}{\sqrt{ 2\pi Nf(1-f) }} e^{ -NI(p,f) }
$$
Dove $I(p,f)=f\ln\left( \frac{f}{p} \right)+(1-f)\ln\left( \frac{1-f}{1-p} \right)$ corrisponde all'entropia realtiva degli eventi (nel caso Bernoulliano) e prende il nome di Funzione di Cramer, che dipende solo dalla distribuzione di partenza e rappresenta un caso più generale del TLC, valido anche per grandi deviazioni.
Si può dimostrare che per priccoli spostamenti di $Y$ rispetto al valore medio si viene a ritrovare il TLC.

**Lezione Associata:** [[4.Distribuzioni di Probabilità continue (di variabili aleatorie)]]