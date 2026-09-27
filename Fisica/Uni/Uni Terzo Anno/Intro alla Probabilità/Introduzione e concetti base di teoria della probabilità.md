---
corso: Intro Probabilità
data: 2026-09-24
tags:
  - lezione
argomenti: []
lezione-precedente:
source:
---


> [!info] Contesto
> Corso: undefined
> Argomenti previsti: 

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
E ho dimostrato il risultato.


## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

