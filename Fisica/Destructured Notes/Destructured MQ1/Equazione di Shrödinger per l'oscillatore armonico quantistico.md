
**Argomenti utili:** [[Soluzione all'EdS per potenziali conservativi]]

Riscriviamo l'equazione di Shrödinger STAZIONARIA nel caso di un potenziale elastico 
($V= \frac{1}{2}m\omega^2x^2)$.
$$
	\begin{aligned}
	\hat{H}\psi=E\psi &\implies-\frac{\hbar^2}{2m} \frac{d^2\psi}{dx^2}+\frac{1}{2}m \omega^2 x^2 \psi=E\psi\\
	&\implies \frac{\hbar^2}{2m} \frac{d^2\psi}{dx^2}+\left( E-\frac{1}{2} m\omega^2x^2 \right)\psi=0
	\end{aligned}
	$$
Introduciamo delle variabili ausiliarie per poter lavorare con grandezze e parametri ADIMENSIONALI. In particolare cerchiamo: 
$$
	\xi=\alpha x; \quad \varepsilon=\beta E
$$
con $[\alpha]=L^{-1}$ e $[\beta]=[E^{-1}]$.  Dobbiamo trovare $\alpha$ e $\beta$.
Per $\beta$ emerge in maniera abbastanza naturale la scelta $\beta=\frac{1}{\hbar \omega}$. A questo punto notiamo che:
$$
	[E]=ML^2 T^{-2} \implies\left[ \hbar \frac{\omega}{m} \right]=L^2 T^{-2}\implies\left[ \frac{\hbar}{m\omega} \right] = L^2
$$
Dunque possiamo andare a scegliere $\alpha =\sqrt{ \frac{m\omega}{\hbar} }$.
Usiamo dunque come nuove variabili: 
$$
	\xi=\sqrt{ \frac{m\omega}{\hbar} }x \quad \text{e} \quad \varepsilon=\frac{2E}{\hbar \omega}
$$
dove il termine moltiplicativo $2$ è stato introdotto per togliere i vari $\frac{1}{2}$ dall'equazione.
Sostitendo nell'equazione otteniamo:
$$
	\frac{d^2\psi}{d^2\xi}+(\varepsilon-\xi^2)\psi=0
$$
Per trovare una soluzione a questa equazione andiamo per prima cosa ad imporre che sia well behaved all'$\infty$.  Per farlo studiamo l'equazione asintotica all'infinito e escludiamo le soluzioni ill-behaved. Partendo dal risultato all'infinito andiamo poi a studiare il caso generale.

Cerchiamo dunque una soluzione asintotica, cioè una soluzione per $\xi\to \pm \infty$. Dato che un potenziale elastico da luogo ad una buca di potenziale prabolica infinita, valgono le condizioni al contorno per cui $\psi(\xi)\to0$ per $\xi\to \pm \infty$ (annullamento al bordo).
Ulteriormente, per $\varepsilon$ finita abbiamo che l'equazione si riconduce a: 
$$
	\frac{d^2\psi}{d\xi^2}-\xi^2 \psi =0
$$
La soluzione a tale equazione è $\psi \propto\exp\left[ \pm \frac{1}{2} \xi^2 \right]$. Dove solo la soluzione negativa è compatibile con le condizioni al contorno.
Per risolvere l'equazione completa (nel caso non asintotico) poniamo: 
$$
	\psi(\xi)=\exp\left[ - \frac{1}{2}\xi^2 \right]H(\xi)
$$
Andiamo a cercare $H(\xi)$ con la condizione che $H(\xi)$ non vada a cambiare il comportamento asintotico per $\xi\to \pm \infty$.

Sostituiamo la nostra soluzione nell'equazione di partenza e cerchiamo $H(\xi)$.
$$
	\frac{d\psi}{d\xi} =-\xi H(\xi)e^{ -\frac{1}{2}\xi^2 }+\frac{dH}{d\xi}e^{ -\frac{1}{2}\xi^2 }
$$
$$
	\implies \frac{d^2\psi}{d\xi^2}=\frac{d^2H}{d\xi^2}e^{ -\frac{1}{2}\xi^2 }-2\xi  \frac{dH}{d\xi}e^{ -\frac{1}{2}\xi^2 } -H(\xi)e^{ -\frac{1}{2}\xi^2 }+\xi^2H(\xi)e^{ -\frac{1}{2}\xi^2 }
$$
Raccogliamo e togliamo il fattore $e^{ -\frac{1}{2}\xi^2 }$ e riscriviamo l'equazione:
$$
	\begin{aligned}
	\frac{d^2H}{d\xi^2}-2\xi  \frac{dH}{d\xi}-(1-\xi^2) H(\xi)+(\varepsilon-\xi^2)H(\xi)&=0 \\
	\implies \frac{d^2H}{d\xi^2}-2\xi  \frac{dH}{d\xi} +(\varepsilon-1)H(\xi) &=0
	\end{aligned}
$$
Da Metodi 1 ricordiamo che le soluzioni di ODE del secondo grado come queste possono avere singolarità SOLO nei punti singolari dei coefficienti dell'equazione differenziale. Pertanto $H(\xi)$ sarà regolare ovunque, tranne che, eventualmente, all'infinito.

Cerchiamo una soluzione a questa equazione per serie, sviluppando con Taylor attorno ad un punto regolare dell'equazione, che scegliamo come $\xi=0$. (Adesso è chiaro il motivo per cui volevamo lavorare con variabili adimensionali).

$$
	H(\xi)=\xi^s(a_{0}+a_{1}\xi+a_{2}\xi^2+\dots+a_{n}\xi^n+\dots)
$$
con $s\geq0$, $s \in \mathbb{N}$ affinchè $H$ sia regolare in $\xi=0$, e $a_{0}\neq 0$. (Ho imposto $a_{0} \neq0$ altrimenti non posso trovare una relazione di ricorrenza).
In questo modo l'equazione diventa una relazione di ricorrenza per i coefficienti $a_{n}$. Abbiamo:
$$
	\begin{aligned}
	\frac{dH}{d\xi}&=s \xi^{s-1}(a_{0}+a_{1}\xi+a_{2}\xi^2+\dots)+\xi^s(a_{1}+2a_{2}\xi+\dots)\\
	&=\xi^{s-1}\left[ sa_{0}+(1+s)a_{1}\xi+(2+s)a_{2}\xi^2+\dots \right]
	\end{aligned}
$$
$$
	\begin{aligned}
	\frac{d^2H}{d\xi^2}&=(s-1)\xi^{s-2}[sa_{0}+(1+s)a_{1}\xi+(2+s)a_{2}\xi^2+\dots]+\xi^{s-1}[(1+s)a_{1}+2(2+s)a_{2}\xi+\dots]=\\
	&=\xi^{s-2}[s(s-1)a_{0}+((s-1)(1+s)+(1+s))a_{1}\xi+((s-1)(2+s)+2(2+s))a_{2}\xi^2+\dots]=\\
	&=\xi^{s-2}[(s-1)s\,a_{0}+s(s+1)a_{1}\xi+(s+2)(s+1)a_{2}\xi^2+\dots]
	\end{aligned}
$$

Sostituendo nell'equazione abbiamo:
$$
	\begin{aligned}
	&\xi^{s-2}[(s-1)s\,a_{0}+s(s+1)a_{1}\xi+(s+2)(s+1)a_{2}\xi^2+\dots]\\
	&-2\xi^s[sa_{0}+(1+s)a_{1}\xi+(2+s)a_{2}\xi^2+\dots]+\\
	&+(\varepsilon-1)\xi^s(a_{0}+a_{1}\xi+a_{2}\xi^2+\dots)=0
	\end{aligned}
$$
I coefficienti delle potenze di $\xi$ si devono tutti annullare separatamente.
$$
	\begin{aligned}
	\xi^{s-2}&: \quad s(s-1)a_{0}=0\implies s=\begin{cases}
	0 \\
	1
	\end{cases} \text{ perchè } a_{0} \neq0\\
	\xi^{s-1}&: \quad s(s+1)a_{1}=0 \implies s=0 \text{ oppure } a_{1}=0 \\
	\xi^s&:\quad (s+2)(s+1)a_{2}-(2s+1-\varepsilon)a_{0}=0\\
	\xi^{s+1}&: \quad (s+3)(s+2)a_{3}-(2s+3-\varepsilon)a_{1}=0\\
	.\\
	.\\
	.\\
	\xi^{s+n}&: \quad (s+n+1)(s+n+2)a_{n+2}-(2s+2n+1-\varepsilon)a_{n}=0\\
	.\\
	.\\
	.\\
	\end{aligned}
$$
Studiamo le implicazioni di queste relazioni di ricorrenza:

1. Sono presenti 2 relazioni di ricorrenza separate, una per $a_{2k}$ e una per $a_{2k+1}$.
   Dalle relazioni vediamo che $s$ può assumere come valori solo zero e uno. Nel caso in cui si ha $s=1$ dobbiamo avere $a_{1}=0$ e dunque $a_{2k+1}=0$. Soluzioni di questo tipo sono dispari. 
$$
	H(\xi)=a_{0}\xi+a_{2}\xi^3+\dots
   $$
   Il caso $s=0$ con $a_{1}\neq0$ ha parità non definita. Tuttavia sappiamo che tutte le soluzioni normalizzabili (cioè quelle che ci interessano) hanno parità definita. Pertanto avremo $a_{1}= 0$ sempre e le soluzioni con $s=0$ saranno le soluzioni pari.
   $$
	H(\xi)=a_{0}+a_{2}\xi^2+\dots
   $$
2. La serie deve terminare, cioè $H(\xi)$ dev'essere un polinomio. Se la serie non terminasse, il comportamento per grande $\xi$ sarebbe determinato da $a_{n}$ per grande $n$.
$$
	\frac{a_{n+2}}{a_{n}}=\frac{2s+2n+1-\xi}{(s+n+1)(s+n+2)}\underset{n\to \infty}{\to} \frac{2}{n}
$$
   e avremmo:
   $$
	H(\xi)=\sum_{n_{pari}} \frac{\xi^n}{(n/2)!}=\sum_{m} \frac{(\xi^2)^m}{m!}=e^{\xi^2}
   $$
   Dunque all'infinito $\psi$ andrebbe come una funzione costante e non sarebbe normalizzabile
3. L'**energia è quantizzata**. Perchè $H(\xi)$ sia un polinomio, deve esistere un valore di $n$ tale che $n\neq 0$ e $n+2=0$.
$$
	a_{n+2}= \frac{2s+2n+1-\varepsilon}{(s+n+1)(s+n+2)}a_{n}\implies \exists \,n:\; 2s+2n+1=\varepsilon\equiv\varepsilon_{n}
$$
   Osserviamo che $n$ è sempre pari ($n=2k$) e $s\in \{ 0,1 \}$. 
   Dunque $\varepsilon_{n}\in \{ 4k+1,4k+3 \}, \; k=0,1,\dots$
   Cioè $\varepsilon_{n}$ è un generico numero dispari: $\varepsilon_{n}=2n+1$ con $n$ generico $\in \mathbb{N}$. (Diverso dall'$n$ di prima)
   $$
	\implies E_{n}=\left( n+\frac{1}{2} \right)\hbar \omega
   $$
   E la soluzione generale ha forma:
   
>[!summary] Soluzione dell'oscillatore armonico quantistico
>
>$$
>	\psi_{n}(\xi)=N_{n}H_{n}(\psi)e^{ -\frac{1}{2}\xi^2 }
>$$

Dove $H_{n}(\xi)$ è un polinomio di grado $n$ che soddisfa:
$$
	H_{n}(-\xi)=(-1)^n H_{n}(\xi ); \quad H''_{n}(\xi)-2\xi H'_{n}(\xi)+2nH_{n}(\xi)=0
$$
Polinomi di questo tipo si dicono polinomi di Hermite.
$N_{n}$ è la costante di normalizzazione.

**Lezione Associata:** [[4.Oscillatore armonico quantistico]]