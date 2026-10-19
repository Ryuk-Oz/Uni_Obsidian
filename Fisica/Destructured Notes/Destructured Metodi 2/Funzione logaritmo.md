Consideriamo la funzione logaritmo: 
$$
	w=f(z)=\log z; \quad z=|z|e^{i\theta}
$$
l'idea da cui partiamo per lo studio del logaritmo complesso è quella di studiarlo come continuazione analitica del logaritmo reale $\log x$ con $x \in \mathbb{R}$.

Sappiamo che la funzione esponenziale complessa $z=e^w$ è una mappa $\mathbb{C}_{z}\to\mathbb{C}_{w}^\infty$, dunque $\log z$ definito come l'inverso della funzione esponenziale è mal definito.

##### 1) Provo a limitare il dominio

Come per la radice proviamo a definire l'inversa limitando l'intervallo di $\theta$ ammessi:
$$
	\theta\in I_{2\pi}: -\pi<\theta\leq \pi
$$
e otteniamo la funzione
$$
	w=\log z=\log(|z|e^{i\theta})=\log |z| + i\theta
$$
che è una possibile continuazione analitica di $\log x$ perchè le due funzioni coincidono in $\mathbb{R}^+$ (che contiene infiniti punti di accumulazione) per $\theta=0$.
Il dominio di $w$ è una striscia di ampiezza $2\pi$.

![[Pasted image 20260930145524.png]]

Esattamente come succedeva per la radice, $\log z=\log |z|+i\theta$ ha un taglio.
Con questo intervallo di $\theta$ la funzione è definita su $\mathbb{C}-\{ \mathbb{R}_{-} \}=D_{1}$; su $\mathbb{R_{-}}$ ho un taglio.

![[Pasted image 20260930145823.png|583]]

Andiamo a verificarlo:
$$
	\begin{aligned}
	L_{+}&=\lim_{ \varepsilon \to 0 }(\log(\rho e^{i(\pi-\varepsilon)}))=\log \rho + i\pi \\ 
	L_{-}&=\lim_{ \varepsilon \to 0 } (\log(\rho e^{i(-\pi+\varepsilon)}))=\log \rho-i\pi \\
	L_{+}-L_{-}&=2\pi i
	\end{aligned}
$$
Il taglio resta presente qualunque sia la scelta di $I_{2\pi}$, dunque andando a definire l'inversa così, ho sempre una regione (il taglio) in cui la funzione logaritmo non è analitica.

Andando ad esempio a scegliere $-\frac{\pi}{2}<\theta\leq \frac{3\pi}{2}$ ho:

![[Pasted image 20260930150410.png]]

$$
	\begin{aligned}
	L_{R}&=\lim_{ \varepsilon \to 0 } (\log(\rho e^{i(-\pi/2+\varepsilon)}))=\log \rho-\frac{i\pi}{2}\\
	L_{{L}}&=\lim_{ \varepsilon \to 0 } (\log \rho e^{i(3\pi/2-\varepsilon)})=\log \rho + i\frac{3}{2}\pi\\
	L_{L}-L_{R}&=2\pi i 
	\end{aligned}
$$
La funzione è definita su $\mathbb{C}-\{ I^{-} \}=D_{2}$
la differenza tra i 2 valori che assume la funzione prima e dopo il taglio resta uguale.

Si nota subito che le due scelte non sono completamente sovrapponibili.

![[Pasted image 20260930151123.png]]

Sappiamo dai teoremi studiati in precedenza che in $D_{C}$ le due funzioni devono coincidere, verifichiamolo:
$$
	\begin{aligned}
	\log(i) &=^1 \log(1e^{i\pi/2}) = \frac{i\pi}{2} \\
	&=^2 \log(1e^{i\pi/2})=\frac{i\pi}{2}
	\end{aligned}
$$
Se invece scelgo $z_{0} \in D_{NC}$, le due funzioni saranno diverse:
$$ \begin{aligned}
z_{0}=-\frac{1}{\sqrt{ 2 }}-\frac{i}{\sqrt{ 2 }} &=^1 1e^{-i 3/2 \pi} \to \log z_{0} = -i \frac{3}{2}\pi \\
&=^2 1e^{i 5/4 \pi}\to \log z_{0}=i \frac{5}{4}\pi 
\end{aligned}
$$
- **Oss:** la scelta $2\pi<\theta\leq{4}\pi$ non è una buona scelta per definire il logaritmo complesso perchè non coincide con $\log x$ da nessuna parte, quindi non mi restituisce una continuazione analitica del logaritmo reale.

Come fatto anche per la radice quadrata, cambiamo approccio per provare a risolvere questi problemi.

##### 2) Considero tutte le $\infty$ copie di $\mathbb{C}_{z}$

In maniera molto poco formale considero $-\infty<\theta<\infty$.
Più formalmente mappo $\theta \to \theta+2\pi n$ e vado a definire vari "piani/fogli". Ad esempio:
$$
	\begin{aligned}
	\text{Foglio zero:} &\quad 0\leq \theta_{0}<2\pi\\
	\text{Foglio n-esimo:} &\quad\theta_{0}\leq \theta_{n}<\theta_{0}+2\pi n
	\end{aligned}
$$
In questo caso il dominio diventa $\Pi = \cup_{i}\mathbb{C}_{i}$, superficie di Riemann del logaritmo.
$$
	\log z|_{n} = L_{n}(z)= \log \rho + i\theta+i 2\pi n; \quad n\in \mathbb{Z}
$$
Ogni foglio avrà il proprio taglio su $\mathbb{R}^{+}$.
Infatti, per un qualunque $n$ fissato abbiamo:
$$
	\begin{aligned}
	L_{n}^+&=\log \rho + i{2}\pi n \\
	L_{n}^-&=\log \rho + i_{2}\pi +i{2}\pi n \\
	\implies L_{n}^- - L_{n}^+ &= 2\pi i
	\end{aligned}
$$
dal calcolo esplicito notiamo che $L_{n}^-=L_{n+1}^+$. Dunque se costruisco $\Pi$ come una superficie il cui lembo inferiore del foglio $n$-esimo si incolla al lembo superiore del foglio $n+1$-esimo ottengo una funzione continua. Questa superficie prende il nome di **Superficie di Riemann** (del logaritmo).

![[Pasted image 20260930163714.png|405]]

Pertanto la funzione $\log z$ definita sulla superficie di Riemann:
$$
	f:\Pi\to \mathbb{C}
$$
non è più una funzione polidroma ma diventa una funzione **globalmente analitica**.

- **NOTA BENE:** potremmo andare a definire $\phi(z)\equiv\log z$ come:
$$
	\phi(z)=\int^z_{1} \frac{1}{z'} \, dz'
$$
e otterremo lo stesso risultato. Infatti, andando ad integrare lungo una curva $\gamma_{n}$ che gira $n$ volte attorno all'origine , il valore di $\phi(z)$ finisce varia col numero di giri che compiamo, aumentando di $i 2\pi n$ ad ogni giro.

- **Oss:** ogni funzione polidroma necessita di una superficie di Riemann costruita ad-hoc per essere resa globalmente analitica.