
Continuiamo la derivazione di risultati noti con il formalismo dei bra e dei ket.

Recap lezione precedente: stati continui non appartengono allo spazio di Hilbert ma soddisfano le condizioni di ortonormalità generalizzata quindi li usiamo comunque perchè comodi.

Analisi degli operatori $\hat{p}$ e $\hat{x}$ nel linguaggio dei bra e dei ket.
$$
	\hat{p}\ket{p} =p \ket{p} 
$$
$$
	\hat{x}\ket{x} =x \ket{x} 
$$
con $\hat{p}$ operatore, $\ket{p}$ vettore e $p$ scalare.
Si tratta di una notazione indipendente dalla rappresentazione usata.
Abbiamo visto che:
$$
	\langle p|p' \rangle  =\delta(p-p') 
$$
$$
	\langle x|y \rangle =\delta(x-y)
$$
= Ortogonalità generalizzata
$\langle p|p \rangle$ e $\langle x|x \rangle$ non esistono.

Abbiamo anche visto:
$$
	\begin{aligned}
	\int dp \ket{p} \bra{p} &= \mathbb{1}\\
	\int dx \ket{x} \bra{x} &= \mathbb{1}\\
	\end{aligned}
$$
= Completezza generalizzata

Paragonandolo al caso discreto abbiamo:
$\hat{H} \ket{n}=E_{n}\ket{n}$
$\langle n|m \rangle=\delta_{nm}$
$\sum_{n} \ket{n}\bra{n}=\mathbb{1}$
$\forall \ket{\alpha}\in \mathcal{H} \quad : \quad \ket{\alpha}=\sum_{n}c_{n} \ket{n}$ con $c_{n}=\langle n|\alpha \rangle$.
E $|c_{n}|^2= P(E_{n})$.

Estendendo quest'ultima cosa a stati discreti abbiamo:
$$
	\forall \ket{\alpha} \in \mathcal{H} \qquad \ket{\alpha} =\int dy\, \psi_{\alpha}(y) \ket{y} 
$$
Questo ci permette di scrivere il prodotto scalare come:
$$
	\langle x|\alpha \rangle=\int dy \, \psi_{\alpha}(y) \langle x|y \rangle =\psi_{\alpha}(x) 
$$
Continuando il paragone col caso discreto abbiamo che:
$$
\begin{aligned}
&|\psi_{\alpha}(x)|^2 \quad \text{è la densità di probabilità di trovare } \\
&x \text{ facendo una misura di posizione nello stato } \ket{\alpha} 
\end{aligned}
$$

Facciamo ora l'analogo per l'impulso:
$$
	\forall \ket{\alpha} \in \mathcal{H} \qquad \ket{\alpha} =\int dp' A_{\alpha}(p') \ket{p'} 
$$
E come prima otteniamo (risolvendo l'integrale per il prodotto scalare):
$$
	A_{\alpha}(p)\equiv \langle p|\alpha \rangle 
$$
Ieri abbiamo calcolaro le autofunzioni di $\hat{p}$. Questo ci permette di calcolare:
$$
	\langle x|p \rangle \equiv\psi_{p}(x)= \frac{1}{\sqrt{ 2\pi \hbar }} e^{ i/\hbar \, p\,x }
$$
Adesso posso fare il contrario:
$$
	\langle p|x \rangle = \langle x|p \rangle ^* = \frac{1}{\sqrt{ 2\pi \hbar }} e^{ -i/\hbar \, p\,x}
$$
In quest'ottica le trasformate e le antitrasformate di fourier emergono come semplice applicazione della completezza di $\ket{p}$ e $\ket{x}$.

Preso $\ket{\alpha}\in \mathcal{H}$:
$$
	\psi_{\alpha}(x)=\langle x|\alpha \rangle= \underbrace{\int dp \, \langle x|p \rangle \langle p|\alpha \rangle }_{\int dp \ket{p} \bra{p} = \mathbb{1}} =\frac{1}{\sqrt{ 2\pi \hbar }} \int dp \, A_{\alpha}(p) e^{ i/\hbar \, p\,x }
$$
E posso fare lo stesso al contrario, ottenendo l'antitrasformata.

Si vede semplicemente che normalizzare lo stato equivale a normalizzarlo per ogni sua rappresentazione in basi diverse.
$$
\begin{aligned}
1=\langle \alpha|\alpha \rangle &=\sum_{n} \langle \alpha|n \rangle \langle n|\alpha \rangle =\sum_{n} c_{n}^* c_{n}=\sum_{n}|c_{n}|^2 \\
& =\int dx \, \langle \alpha|x \rangle \langle x|\alpha \rangle = \int dx \, |\psi_{\alpha}(x)|^2\\
&=\int dp \, \langle \alpha|p \rangle \langle p|\alpha \rangle =\int dp |A_{\alpha}(p)|^2
\end{aligned}
$$

**Elementi di matrice di un operatore $Q$**.
$$
	\begin{aligned}
	\bra{\alpha_{1}} Q\ket{\alpha_{2}} &=\int dx\,dy\, \langle \alpha_{1}|x \rangle \bra{x} Q\ket{y} \langle y|\alpha_{2} \rangle=\\
	&=\int dx dy\; \psi_{\alpha_{1}}^*(x) \, \bra{x} Q \ket{y} \, \psi_{\alpha_{2}}(y)
	\end{aligned} 
$$
Abbiamo un "problema", l'operatore nell'integrale dipende da 2 variabili, noi siamo abituati a lavorare con operatori a una variabile. Questo non è un problema reale, perchè tutti gli operatori unidimensionali sono rappresentabili come matrici diagonali e portano fuori una delta di Dirac.
$$
	\text{se } Q=Q(x) \implies \bra{x} Q\ket{y} = Q(x)\cdot \delta(x-y)
$$
e l'integrale diventa:
$$
	\bra{\alpha_{1}} Q\ket{\alpha_{2}} =\int dx\, \psi_{\alpha_{1}}^*(x) Q(x)\psi_{\alpha_{2}}(x)
$$
La situazione è più delicata quando parliamo di operatori che dipendono dall'impulso:
$$
	Q=Q(p)\implies \bra{x} Q\ket{y} \equiv Q_{xy}=\delta (x-y) \cdot Q\left( -i\hbar \frac{d}{dx} \right)
$$
E ritrovo l'integrale che abbiamo usato fino ad ora.

### Rappresentazione spettrale di un operatore Q (autoaggiunto)

Se $Q$ è autoaggiunto, allora ammette una base ortonormale di autovettori:
$$
	Q \ket{n} =q_{n} \ket{n} 
$$
Allora:
$$
	\begin{aligned}
	\langle n|m \rangle &=\delta _{nm}\\
	\sum_{n}\ket{n} \bra{n} &= \mathbb{1}
	\end{aligned}
$$
E possiamo rappresentare l'operatore in questo modo (rappresentazione spettrale):
$$
	Q=\sum_{n} q_{n} \ket{n} \bra{n} 
$$
Verifichiamolo.
Ricordando che $\forall \ket{\alpha}\in \mathcal{H}$ ho: $\ket{\alpha}=\sum_{n} c_{n} \ket{n}$, troviamo:
$$
	\begin{aligned}
	Q \ket{\alpha} &= \sum_{n} \alpha_{n} Q \ket{n}=\sum_{n} \alpha_{n} q_{n} \ket{n}   =\sum_{n} q_{n} \ket{n} \langle n|\alpha \rangle = \sum_{n}q_{n} \ket{n} \bra{n} \underbrace{\sum_{m} \alpha_{m} \ket{m}}_{\ket{\alpha} }
	\end{aligned}
$$
Dunque $Q=\sum_{n} q_{n} \ket{n} \bra{n}$. $\blacksquare$

**Rappresentazione della delta di Dirac**.
$$
	\forall \ket{\alpha} \in \mathcal{H} \quad \text{scelgo una base } \{ \ket{n}  \} \text{ ON}
$$
Riscrivo $\ket{\alpha}$ in questa base:
$$
	\ket{\alpha} =\sum_{n} c_{n}^{(\alpha)} \ket{n} 
$$
Sappiamo che:
$$
	\langle x|\alpha \rangle \equiv \psi_{\alpha}(x)=\sum_{n} c_{n}^{(\alpha)} \langle x|n \rangle =\sum_{n} c_{n}^{(\alpha)} \psi_{n}(x)
$$
Posso riscrivere questo in modo diverso:
$$
	\langle x|\alpha \rangle =\sum_{n} \langle x|n \rangle \langle n|\alpha \rangle =\sum_{n} \int dy\, \langle x|n \rangle \langle n|y \rangle \langle y|\alpha \rangle =\sum_{n}\int dy\, \psi_{n}(x) \psi_{n}^* (y) \psi_{\alpha}(y)
$$
Unendo le due rappresentazioni otteniamo:
$$
	\psi_{\alpha}(x)=\sum_{n} \int dy\, \psi_{n}(x) \psi_{n}^* (y) \psi_{\alpha}(y) =\int dy \, \left[ \sum_{n} \psi_{n}(x) \psi_{n}^* (y) \right] \psi_{\alpha}(y)
$$
Pertanto:
$$
	\sum_{n} \psi_{n}(x)\psi_{n}^*(y)=\delta(x-y)
$$
### Principi fondativi della meccanica quantistica

#### 1. Spazio degli stati fisici

Dato un sistema $S$, gli stati possibili per $S$ sono in corrispondenza biunivoca con i "raggi" di uno spazio di Hilbert $\mathcal{H}_{S}$ su $\mathbb{C}$.
Facciamo alcune assunzioni:
- Supponiamo che $\mathcal{H}_{S}$ sia SEPARABILE e COMPLETO
- Se lo spazio delle configurazioni di $S$ è un volume $V_{S}$, con $\mathbb{R}^{3n}$ , allora $\mathcal{H}_{S}$ è isomorfo a $L^2(V_{S})$.
- I RAGGI in $\mathcal{H}_{S}$ sono classi di equivalenza di vettori, posso modulare la norma e la fase: 
$$
  	\ket{\alpha}  \sim k \ket{\alpha} \sim e^{ i\theta } \ket{\alpha} 
  $$
  L'insieme di tutti i vettori $\ket{\alpha}$, cioè l'insieme delle osservabili fisiche è:
$$
 \bar{\mathcal{H}}_{S}\equiv \{ \ket{\alpha}  \} \equiv \frac{\mathcal{H}_{S}}{\mathbb{C}}
$$
- Una possibile rappresentazione dello stato fisico è la sua FUNZIONE D'ONDA in $V_{S}$
$$
	\langle \vec{r}|\alpha \rangle \equiv \psi_{\alpha}(\vec{r})
  $$
- Lo spazio $\mathcal{H}_{S}$ (e quindi lo spazio $\bar{\mathcal{H}}_{S}$) è lo spazio degli stati a TEMPO FISSATO. L'evoluzione temporale è dettata dall'EdS.

#### 2. Corrispondenza tra osservabili fisiche e operatori lineari su $\mathcal{H}_{S}$.

Tutte le osservabili fisiche $A_{S}=A_{S}(\{ q \}, \{ p \})$ del sistema $S$ sono rappresentate in $\mathcal{H}_{S}$ da OPERATORI LINEARI AUTOAGGIUNTI $\hat{A}$.
Questi operatori hanno equazioni agli autovalori:
$$
	\hat{A}\ket{a_{\sigma}} =a_{\sigma}\ket{a_{\sigma}} 
$$
Osservazioni varie:
- gli $a_{\sigma}$ possono formare uno spettro discreto $a_{\sigma}\in \mathbb{N}$ , oppure possono avere uno spettro continuo, ovvero $a_{\sigma}\in \mathbb{R}$.
- I corrispondenti autovettori $\ket{a_{\sigma}}$ formano basi ON in senso stretto nel caso discreto e basi ortogonali in senso generalizzato nel caso continuo.
- Interpreto $\{ a_{\sigma} \}$ come l'insieme dei possibili risultati per le misure di $A$.
- Gli stati $\ket{a_{\sigma}}$ sono stati nei quali una misura di $A$ fornisce sempre $a_{\sigma}$ con $P(a_{\sigma})=1$. Infatti:
$$
	\begin{aligned}
	\langle \hat{A} \rangle _{\sigma}&\equiv \bra{a_{\sigma}} \hat{A}\ket{a_{\sigma}} =a_{\sigma} \langle a_{\sigma}|a_{\sigma} \rangle =a_{\sigma}\\
	\langle \hat{A}^2 \rangle _{\sigma}&\equiv \bra{a_{\sigma}} \hat{A}^2\ket{a_{\sigma}} =a^2_{\sigma} \langle a_{\sigma}|a_{\sigma} \rangle =a_{\sigma}^2\\
	\implies&(\Delta \hat{A})_{\sigma}=\sqrt{ \langle \hat{A}^2 \rangle _{\sigma}-\langle \hat{A} \rangle _{\sigma}^2 }=0
	\end{aligned}
$$
- Gli autovalori $a_{\sigma}$ possono essere degeneri, cioè avere autospazi di dimensioni maggiori di 1.





