
**Prerequisiti essenziali:** [[Legge dei grandi numeri]] [[Funzioni Caratteristiche]]

Con l'uso delle funzioni caratteristiche è possibile raffinare la legge dei grandi numeri, arrivando al Teorema Centrale del Limite.

**Enunciato:**
    Siano $x_{1},x_{2},\dots,x_{N}$ variabili aletorie indipendenti ed identicamente distribuite, con $\langle x \rangle = \mu$ e varianza $\sigma^2$ FINITA. Definiamo $z_{N}$ come:
$$
	z_{N}\equiv \frac{1}{\sigma \sqrt{ N }} \sum^N_{i=1} (x_{i}-\mu)
$$
    Se $N\gg 1$ $\implies p(z)=N(0,1)=\frac{1}{\sqrt{ 2\pi }}e^{ -z^2/2 }$ distribuzione normale standard con $\mu=0$ e $\sigma^2=1$
    Qualunque sia la ditribuzione di probabilità.

**Dim:**
    Introduciamo $y_{N}=x_{1}'+x_{2}'+\dots+x'_{N}$. Con $xì_{i}=x_{i}-\mu$.
    Scriviamo la funzione caratteristica di questa variabile:
$$
	\phi_{y_{N}}(t)=\prod \phi_{x'_{j}}(t) \underset{\text{var. iid}}{=} [\phi_{x'_{j}}(t)]^N
$$
    Definisco una nuova variabile $z=\frac{1}{\sigma \sqrt{ N }}y_{N}$, qua uso l'ipotesi che la varianza sia finita.
$$
	\phi_{z}=\phi_{y}\left( \frac{t}{\sigma \sqrt{ N }} \right)=\left[ \phi_{x'}\left( \frac{t}{\sigma \sqrt{ N }} \right) \right]^N
$$
    Sviluppo la funzione caratteristica di una variabile aleatoria qualunque, per una distribuzione di probabilità qualunque (per $t\ll{1}$).
$$
	\phi_{x}=\int e^{ itx } p(x)dx \simeq \int\left( 1+itx-\frac{1}{2}t^2x^2+\dots \right)p(x)dx=1+it\langle x \rangle -\frac{1}{2}t^2\langle x^2 \rangle+\dots 
$$
    Applichiamolo $\phi_{x'}$:
$$
\begin{aligned}
\phi_{x'}\left( \frac{t}{\sigma \sqrt{ N }} \right)&=1+\frac{it}{\sigma \sqrt{ N }}\langle x-\mu \rangle -\frac{1}{2} \frac{t^2}{\sigma^2N}\langle x^2-\mu^2 \rangle =\\
&= 1-\frac{1}{2} \frac{t^2}{N}
\end{aligned}
$$
    Dunque:
$$
	\phi_{Z}=\left( 1-\frac{1}{2} \frac{t^2}{N}+O(t^2) \right)^N \underset{N\gg{1}}{\simeq} e^{ N\ln(1-\frac{1}{2}t^2/N) }\simeq e^{ -Nt^2/(2N) }=e^{ -t^2/2 }
$$
    Dunque:
$$
	p_{Z}(z)=\frac{1}{2\pi}\int e^{ -itz }e^{ -t^2/2 } dt=\frac{1}{\sqrt{ 2\pi }}e^{ -z^2/2 } \qquad \forall p(x)
$$
    Per risolvere l'integrale ho completato il quadrato. $\blacksquare$.

**Esempio di distribuzione che viola il TLC**: Distribuzione di Cauchy.

Consideriamo la seguente distribuzione di probabilità:
$$
	p(x)= \frac{1}{\pi(1+x^2)}
$$
Verifichiamo sia normalizzata:
$$
	\int p(x)dx=\frac{1}{\pi} [\tan(x)]^\infty_{-\infty} =1
$$
Per simmetria notiamo che $\langle x \rangle=0$ e $\sigma^2=\infty$, cioè non rispetta le ipotesi del TLC.
La funzione caratteristica (che non calcoliamo esplicitamente) è:
$$
	\phi_{x}(t)=e^{ -|t| }
$$
Abbiamo anche che $y_{N}=\sum x'_{i}=\sum x_{i}\implies \phi_{y}=e^{ -N|t| }$.
Non possiamo definire $z_{N}$ nel modo classico, definiamolo allora come $z_{N}=\frac{1}{N}\sum_{i}x_{i}$.
$$
	\phi_{z}=e^{ -t }=\phi_{x} \implies p_{z}(t)=p_{x}(t)
$$

**Lezione Associata:** [[4.Distribuzioni di Probabilità continue (di variabili aleatorie)]]