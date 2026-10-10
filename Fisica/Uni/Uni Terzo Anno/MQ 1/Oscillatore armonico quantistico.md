---
corso: Meccanica Quantistica 1
data: 2026-10-10
tags:
  - lezione
argomenti: []
lezione-precedente: "[[Equazione di Shrödinger]]"
source:
---


> [!info] Contesto
> Corso: Meccanica Quantistica 1
> Argomenti previsti: 

## Riassunto veloce


## Appunti

In questa sezione ci occupiamo di un'esempio particolarmente interessante, quello dell'oscillatore armonico. Una delle poche cose che tutti i fisici concordano di saper risolvere in maniera esatta

#### 1. L'oscillatore armonico classico

Per prima cosa partiamo da un ripasso di quella che è la teoria classica.
L'oscillatore armonico classico è una particella puntiforme di massa $m$ soggetta ad una forza elastica di richiamo che segue la legge di Hooke. 
$$
	F=-Kx
$$
l'equazione del moto è dunque 
$$
	m\ddot{x}+Kx=0
$$
Sappiamo risolvere quest'equazione, che ha come soluzione generale:
$$
	x(t)=A\cos(\omega t+\varphi), \quad \omega=\sqrt{ \frac{K}{m} }
$$
La forza elastica considerata è una forza conservativa, pertanto è derivabile da un potenziale che non dipende dal tempo: 
$$
	V(x)=\frac{1}{2}m \omega^2 x^2 \iff F=-\frac{dV}{dx}
$$
Dunque possiamo analizzare lo stesso problema sfruttando il formalismo lagrangiano e quello hamiltoniano. La lagrangiana del sistema è:
$$
	L=T-V=\frac{1}{2}m\dot{x}^2-\frac{1}{2}m\omega^2x^2
$$
Invece l'Hamiltoniana è:
$$
	\begin{aligned}
	p&=\frac{ \partial L }{ \partial \dot{x} } =m\dot{x} \implies \dot{x}=\frac{p}{m}\\
	H&=p\dot{x}-L=\frac{p^2}{m}-\frac{1}{2} \frac{p^2}{m}+\frac{1}{2}m\omega^2x^2=\frac{1}{2} \frac{p^2}{m}+\frac{1}{2}m\omega^2x^2=T+V
	\end{aligned}
$$
Il sistema è conservativo come atteso.
Ricordiamo che l'importanza dello studio di un oscillatore armonico sta nel fatto che tutte le oscillazioni attorno a un punto di equilibrio stabile di un sistema si riducono a sovrapposizioni di oscillatori armonici.

#### 2. Equazione di Shrödinger con un potenziale elastico

Riscriviamo l'equazione di Shrödinger STAZIONARIA nel caso di un potenziale di questo tipo.
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

#### 3. Proprietà dei polinomi di Hermite

I polinomi di Hermite sono un insieme di polinomi ortogonali in $L^2(-\infty,+\infty)$. 
Di seguito ne elenchiamo alcune proprietà utili.

1. Esiste una funzione generatrice per i polinomi di Hermite.
   Posto $S(z,\xi)\equiv e^{ -z^2+2z\xi }$ si ha che: 
   $$
	S(z,\xi)=\sum^\infty_{n=0} \frac{z^n}{n!}H_{n}(\xi)
   $$
   cioè:$$H_{n}(\xi)=\frac{ \partial^nS }{ \partial z^n }|_{z=0}$$
2. Vale la seguente formula per la derivata: 
$$
   	\begin{aligned}
	\frac{ \partial S }{ \partial \xi }=2zS&\implies \sum^\infty_{n=0} \frac{z^n}{n!}H'_{n}(\xi) =2z\sum^\infty_{n=0} \frac{z^n}{n!}H_{n}(\xi)=\sum_{n=0}^\infty 2 \frac{z^{n+1}}{n!}H_{n}(\xi)\\
	(H'_{0}(\xi)=0)&\implies \sum^\infty_{n=1} \frac{z^n}{n!}H'_{n}(\xi)=2\sum^\infty_{n=1} \frac{z^n}{(n-1)!}H_{n-1}(\xi)\\
	&\implies H'_{n}(\xi)=2nH_{n-1}(\xi)
	\end{aligned}
   $$
3. I polinomi di Hermite sono legati da una relazione di ricorrenza:
$$
	\begin{aligned}
	\frac{ \partial s }{ \partial z }=2(\xi-z)S &\implies \sum_{n=0} \frac{z^{n-1}}{(n-1)!}H_{n}(\xi)=2 \sum_{n=0} \frac{(\xi-z)z^n}{n!}H_{n}(\xi)\\
	&\implies \sum_{n=0} \frac{z^n}{n!}H_{n+1}(\xi)=2\sum_{n=0} \frac{(\xi-z)z^n}{n!}H_{n}(\xi)\\
	&\implies H_{n+1}-2\xi H_{n}(\xi)+2nH_{n-1}(\xi)=0 \quad (n=1,2,\dots)
	\end{aligned}
$$
   Se combiniamo i punti (2) e (3) otteniamo l'equazione differenziale si cui sono soluzione
4. Sono soluzione di una particolare equazione differenziale, detta equazione di Hermite.
   Deriviamo 2 volte la relazione di ricorrenza:
$$
	\begin{aligned}
	H_{n+1}'-2\xi H_{n}'-2H_{n}+2nH_{n-1}'&=0\\
	H_{n+1}''-2\xi H_{n}''-4H'_{n}+2nH_{n-1}''&=0
	\end{aligned}
$$
   A questo punto applichiamo la formula per le derivate:
$$
	\begin{cases}
	H''_{n+1}=(H'_{n+1})'=2(n+1)H'_{n}=4n(n+1)H_{n-1} \\
	H''_{n}=2nH'_{n-1} \\ \\
	H'_{n}=2nH_{n-1}
	\end{cases}
   $$
   Sostituiamo all'interno della relazione di ricorrenza derivata 2 volte:
$$
	4n(n+1)H_{n-1}-\xi 4nH'_{n-1}-8nH_{n-1}+2nH''_{n-1}=0; \quad (n-1=0,1,\dots)
   $$
   Sostituendo $n-1$ con $n$ otteniamo:
$$
	\implies H''_{n}-2\xi H'_{n}+2nH_{n}=0
$$
   Che è esattamente l'equazione che abbiamo risolto, per $\varepsilon-1=n$
5. Per trovare i polinomi di Hermite vale la seguente formula, detta formula di Rodriguez:
$$
\begin{aligned}
H_{n}(\xi)&=\frac{ \partial^n S }{ \partial z^n }|_{z=0}=\frac{ \partial ^n }{ \partial z^n } e^{ -z^2+2z\xi }|_{z=0}\\
&=e^{ \xi^2 }\frac{ \partial ^n }{ \partial z^n } e^{ -(z-\xi)^2 }|_{z=0}=(-1)^n e^{ \xi^2 }\frac{ \partial ^n }{ \partial \xi^n }e^{ -(z-\xi)^2 }|_{z=0}\\
&=(-1)^n e^{ \xi^2 } \frac{d^n}{d\xi^n}e^{ -\xi^2 } 
\end{aligned}   	
   $$
   Da questa formula si ritrovano le condizioni sulla parità di cui parlavamo prima:
$$
	H_{n}(-\xi)=(-1)^n H_{n}(\xi)
   $$

## Domande per revisione
- [ ] 

## Collegamenti
- Lezione precedente: [[]]
- Concetti collegati: [[]]

