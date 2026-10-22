
**Lezione associata:** [[1.Introduzione e concetti base di teoria della probabilità]]
___

Andando a costruire sulle basi solide fornite dalla [[Teoria assiomatica della probabilità]], andiamo a studiare alcuni teoremi base della probabiliità classica.

-  $A,B \subset \Omega$ sono indipendenti $\iff P(A\cap B)=P(A)P(B)$
Andiamo a dimostrarlo con l'approccio frequentista:
$$
	P(A\cap B)=\frac{N(A\cap B)}{N}=\frac{N(A \cap B)}{N(B)} \frac{N(B)}{N}
$$
Se A e B sono indipendenti allora $\frac{N(A\cap B)}{N(B)}=P(A)$ se $A$ e $B$ sono indipendenti, infatti è come se stessi andando a calcolare la frequenza con cui si avvera A su un sottoinsieme più ristretto di $\Omega$, ma la frequenza resta sempre la stessa visto che non dipende dal sottoinsieme $B \subset \Omega$.
Dunque:
$$
	P(A\cap B)=\frac{N(A\cap B)}{N(B)} \frac{N(B)}{N}=P(A)P(B)
$$
E ho dimostrato il risultato. $\blacksquare$

- $P(A \cup B)=P(A)+P(B)-P(A \cap B)\leq P(A)+P(B)$
Per dimostrarlo sfruttiamo il seguente schema:

![[Pasted image 20260930221725.png]]

Considero i seguenti insiemi, disgiunti per costruzione:
$$
\begin{aligned}
C_{1}&=A-(A\cap B)\\
C_{2}&=A \cap B \\
C_{3}&=B-(A\cap B)
\end{aligned}
$$
scriviamo le probabilità associate a questi insiemi:
$$
	\begin{aligned}
	P(C_{1})=P(A)-P(A\cap B)\\
	P(C_{3})=P(B)-P(A\cap B)\\
	\end{aligned}
$$
e otteniamo che:
$$
	\begin{aligned}
	P(A \cup B)&=P(C_{1})+P(C_{2})+P(C_{3})=P(A)+P(B)+P(A\cap B)-2P(A\cap B)\\
	&=P(A)+P(B)-P(A\cap B)
	\end{aligned}
$$
$\blacksquare$