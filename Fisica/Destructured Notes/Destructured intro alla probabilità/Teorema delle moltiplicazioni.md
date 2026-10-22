
Il teorema delle moltiplicazioni, così come il teorema della probabilità completa, è una diretta conseguenza del teorema di Bayes.
$$
	P(A_{1}\cap A_{2}\cap\dots\cap A_{N})=P(A_{1})P(A_{2}|A_{1})P(A_{3}|A_{2}\cap A_{1})\dots P(A_{N}|A_{1}\cap A_{2}\cap\dots\cap A_{N-1})
$$
La dimostrazione si fa per induzione sfruttando la definizione di probabilità condizionata e la formula di Bayes.

Di seguito è fornito un esempio tipico di applicazione del problema.

**Probabilità che in una classe si trovino 2 persone nate lo stesso giorno**

Sfruttiamo il teorema delle moltiplicazioni per calcolare qual è il numero minimo di persone tale che la probabilità che 2 siano nati lo stesso giorno sia maggiore del $50\%$ (ovvimente $N\leq365$).
Definisco i 2 eventi:
$$
	\begin{aligned}
	A &= \text{almeno 2 persone sono nate lo stesso giorno}\\
	\bar{A} &= \text{tutti sono nati in giorni diversi}
	\end{aligned}
$$
ad ogni persona possiamo definire $A_{k}$ nel seguente modo:
$$
	\begin{aligned}
	A_{1}&=\text{2 non è nato lo stesso giorno di 1}\\
	A_{2}&=\text{3 non è nato lo stesso giorno di 1 o di 2}\\
	&.\\
	&.\\
	&.\\
	A_{n-1}&= \, n \text{ non è nato lo stesso giorno di 1 o di 2 o } \dots \text{ di } n-1
	
	\end{aligned}
$$
Pertanto l'evento $\bar{A}$ sarà:
$$
	\bar{A}=A_{1}\cap A_{2}\cap A_{3}\dots \cap A_{n-1}
$$
applichiamo il teorema delle moltiplicazioni:
$$
	P(\bar{A})=P(A_{1})P(A_{2}|A_{1})P(A_{3}|A_{1}\cap A_{2})\dots P(A_{n-1}|A_{1}\cap A_{2}\cap A_{3}\dots \cap A_{n-2})
$$
Calcoliamo i termini che compaiono in questa espressione
$$
	\begin{aligned}
	P(A_{1})=1-\frac{1}{365} \quad \quad P(A_{2}|A_{1})=1-\frac{2}{365} \qquad P(A_{n-1}|\dots)=1-\frac{n-1}{365}
	\end{aligned}
$$
dunque:
$$
	\begin{aligned}
	P(\bar{A})&=\prod_{k=1}^{n-1}\left( 1-\frac{k}{365} \right)\\
	P(A)&=1-\prod_{k=1}^{n-1}\left( 1-\frac{k}{365} \right)
	\end{aligned}
$$
Questa forma è ovviamente molto lunga da sommare ma possiamo approssimarla per valori piccoli di $k$ (e dunque di $n$).
$$
	\begin{aligned}
	P(\bar{A})&=e^{ \log \prod(1-k/365) }=\exp\left[ \sum_{k=1}^{n-1} \log\left( 1-\frac{k}{365} \right)\right]\\
	&\simeq \exp\left[ -\sum_{k=1}^{n-1} \frac{k}{365} \right]= \exp\left[ -\frac{n(n-1)}{2\cdot 365} \right]
	\end{aligned}
$$
Svolgendo il conto otteniamo una percentuale $p(A)\simeq 0,507$ per $n=23$ e $0,094$ per $n=60$.