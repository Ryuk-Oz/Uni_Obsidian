---
corso: Intro Probabilità
data: 2026-09-24
tags:
  - lezione
argomenti:
  - Probabilità
lezione-precedente:
source:
---


> [!info] Contesto
> Corso: Intro Probabilità
> Argomenti previsti: Definizioni storiche di probabilità, probabilità assiomatica, probabilità classica, calcolo combinatorio

## Riassunto veloce



## Appunti

Iniziamo dalle 2 definizioni storiche di probabilità:

- **Probabilià classica/Frequentista** (De Moivre $\sim 1718$), comoda per eventi discreti
$$
	P=\frac{\#\text{casi favorevoli}}{\#\text{casi possibili}}
$$
- **Probabilità soggettivista** (de Finetti), comoda per probabilità che non ricadono nel caso precedente, come le probabilità di mercato. Equivale alla "fiducia" che io ho nell'avverarsi di un vento.
### Teoria Assiomatica

Nel 1900 Hilbert annuncia la necessità di assiomatizzare la teoria della probabilità in quanto unico modo di definirla efficacemente (come ha fatto Euclide con la geometria). Questo viene fatto nel 1933 da Kolmogorov.

Consideriamo dunque un insieme $\Omega$ di eventi elementari (spazio degli eventi) e $I$, una famiglia di eventi contenuta in $\Omega$. Allora valgono i seguenti assiomi:
1. $I$ è un algebra di insiemi, cioè: 
   $$
   	\forall \, A,B\in I \Rightarrow \{ A \cup B, A\cap B, \bar{A}=\Omega-A \} \in I
   $$
2. $\forall \, A \in I$ associo un numero reale $P(A)\geq 0$ che chiamo "Probabilità di A"
3. $P(\Omega)=1$
4. Se $A\cap B=\emptyset$ cioè i due insiemi sono disgiunti, $\Rightarrow$ $P(A \cap B)=P(A)+P(B)$

Da questi 4 assiomi posso costruire tutta la teoria della probabilità.

#### Corollari di questi assiomi:

- $P(\bar{A})=1-P(A)$ (dimostrazione banale)
- $P(\emptyset)=0$ (dimostrazione banale)
- $0\leq P(A)\leq {1}$ (dimostrazione per assurdo)

Studiamo ora cosa succede nel caso in cui l'insieme $\Omega$ diventi continuo. 
Ad esempio $\Omega \subset \mathbb{R}$. Un elemento $A$ della famiglia $I$ diventa un intervallo continuo.
$$
	A=[a,b)
$$
![[Pasted image 20260925000239.png]]

La probabilità di $A$ è la sua misura, per definirla devo introdurre una funzione di distribuzione:
$$
	F_{X}(x) \equiv P[X\leq x] = \int^X_{-\infty}p(x)dx
$$
dove abbiamo introdotto anche una funzione densità di probabilità:
$$
	p_{X}(x)=\frac{dF_{X}}{dx}
$$
e la probabilità di $A$ diventa:
$$
	P(A)=\int^a_{b}p(x)dx
$$
### Probabilità classica

Ora che abbiamo verificato che la teoria che staimo andando a studiare si fonda su basi matematiche solide, andiamo a studiare alcuni teoremi della probablità classica.

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

### Ripasso di Calcolo Combinatorio

Procediamo adesso con un ripasso di calcolo combinatorio, utile più avanti.

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

## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

