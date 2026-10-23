
Continuiamo la discussione della funzione $\psi$.
$$
	\psi=\frac{d}{dz}\log \Gamma(z)=\frac{\Gamma'(z)}{\Gamma(z)}
$$
L'ultima cosa che abbiamo fatto è stata la rappresentazione integrale della Digamma:
$$
	\psi(z)=\int^\infty_{0} \frac{dx}{x} \left( e^{ -x }- \frac{1}{(x+1)^z} \right) 
$$
Ricorda, l'integrale converge solo se considero i 2 termini tutti insieme.

Cosa posso fare per studiare questo integrale?
Deformando il cammino di integrazione (prova a disegnare questo cammino), l'integrale è uguale a:
$$
		\psi(z)=\int^\infty_{0} \frac{dx}{x} \left( e^{ -x }- \frac{1}{(x+1)^z} \right) =\lim_{ \varepsilon \to 0 } \int^\infty_{\varepsilon} \frac{dx}{x} \left( e^{ -x }- \frac{1}{(x+1)^z} \right) 
$$
A questo punto posso calcolare il secondo pezzo per $\varepsilon>0$
$$
	B=\int^\infty_{\varepsilon} \frac{dy}{y(1+y)^z} =\int^\infty_{\log(1+\varepsilon)} dx \, e^{ x } \frac{e^{ -xz }}{e^{ x }-1}\underset{\varepsilon\to_{0}}{\sim}\int^\infty_{\varepsilon} dx \, \frac{e^{ x-xz }}{e^{ x }-1}=\int^\infty_{\varepsilon}dx\, \frac{e^{ -xz }}{1-e^{ -x }}
$$
Dove abbiamo cambiato variabile: $1+y=e^{ x }\implies dy=e^{ x }dx$
A questo punto lo riporto nel limite di prima:
$$
	\lim_{ \varepsilon \to 0 }  \int^\infty_{\varepsilon} dx\, \left[ \frac{e^{ -x }}{x} - \frac{e^{ -xz }}{1-e^{ -x }} \right]
$$
E questo lo sappiamo calcolare. Ho trovato una **seconda** rappresentazione integrale di $\psi$
$$
	\psi(z)=\int^\infty_{0} dx\,  \left[ \frac{e^{ -x }}{x} - \frac{e^{ -xz }}{1-e^{ -x }} \right]
$$
Ora proviamo ad aggiungere e togliere $\psi(1)$.
$$
\begin{aligned}
\psi(z)&=\psi(z)+\psi(1)-\psi(1)=\psi(z)-\gamma-\psi(1)=\\
&=\int^\infty_{0} dx\,  \left[ \frac{e^{ -x }}{x} - \frac{e^{ -xz }}{1-e^{ -x }} \right] -\gamma - \int^\infty_{0} dx\,  \left[ \frac{e^{ -x }}{x} - \frac{e^{ -x }}{1-e^{ -x }} \right] = \\
&= \int^\infty_{0} dx\,  \left[  \frac{e^{ -x }-e^{ -xz }}{1-e^{ -x }} \right]-\gamma
\end{aligned}
$$
E ho trovato una **terza** rappresentazione integrale.
Ulteriormente potrei andare a chiamare $e^{ -x }=w\implies-e^{ -x }dx=dw\implies dx=-\frac{dw}{w}$
$$
	\psi(z)=-\gamma+\int^1_{0} \frac{dw}{w}\, \frac{w-w^z}{1-w}=-\gamma+\int_{0}^1 dw\, \frac{1-w^{z-1}}{1-w}
$$
E ho trovato una **quarta** rappresentazione integrale.

Da quest'ultima rappresentazione è possibile trovare una rappresentazione di $\psi$ in serie di potenza.
$$
	\frac{1}{1-x}=\sum_{k=0}^\infty x^k
$$
è uniformemente convergente quindi posso integrare termine a termine
$$
	
	\begin{aligned}
	\psi(z)&=-\gamma+\sum^\infty_{k=0} \int^1_{0} dx\, (1-x^{z-1})x^k=-\gamma+\sum^\infty_{k=0}\left( \int^1_{0} dx\, x^k -\int^1_{0} dx\, x^{k+z-1}\right)=\\
	&=-\gamma+\sum^\infty_{k=0}\left[ \frac{x^{k+1}}{k+1}|_{_{0}}^{^1} -\frac{x^{k+z}}{k+z}|^{^1}_{_{0}}\right]=-\gamma+\sum^\infty_{k=0}\left( \frac{1}{k+1} - \frac{1}{k+z} \right)=\\
	&=-\gamma-\frac{1}{z}+\sum^\infty_{k=1}\left[ \frac{1}{k}-\frac{1}{k+z} \right]=-\gamma-\frac{1}{z}+\sum^\infty_{k=1} \frac{z}{k(k+z)}
	\end{aligned}
$$
La serie converge a causa della differenza. Presi separatamente la serie diverge. Questo si vede bene alla fine. La serie tutta insieme va come $\frac{1}{k^2}$.
Da qua si notano subito le singolarità di $\psi$ in $z=0,-1,-2\dots$

Questa forma in serie ci permette di scrivere una nuova rappresentazione per la funzione $\Gamma$.
Integriamo la $\psi$ nel seguente modo:
$$
	\begin{aligned}
		\int^z_{0} \psi(w+1) dw &= \int^z_{0} dw \frac{d}{dw}\{ \log \Gamma(w+1) \}=[\log \Gamma(w+1]^{^z}_{_{0}}=\log \Gamma(z+1)-\log \Gamma(1)\\
		&=\int^z_{0} dw\, \left( -\gamma+\sum^\infty_{n=0} \left( \frac{1}{n+1}-\frac{1}{n+1+w} \right) \right)=\\
		&=-\gamma z+\sum^\infty_{n=0} \left( \frac{z}{n+1}-\log\left( \frac{n+1+z}{n+1} \right) \right)=-\gamma z+\sum^\infty_{n=1}\left( \frac{z}{n}-\log\left( \frac{n+z}{n} \right) \right)=\\
		&=-\gamma z+\sum^\infty_{n=1} \left( \frac{z}{n}-\log\left( 1+\frac{z}{n} \right) \right)=-\gamma z+\sum^\infty_{n=1} \log\left[ e^{ z/n }\left( 1+\frac{z}{n} \right)^{-1} \right]\\
		\implies \log\Gamma(z+1)&=-\gamma z +\sum^\infty_{n=1} \log\left[ e^{ z/n }\left( 1+\frac{z}{n} \right)^{-1} \right]=e^{ -\gamma z }\prod^\infty_{n=1} e^{ z/n } \left( 1+\frac{z}{n} \right)^{-1}
	\end{aligned}
$$
Da qua si possono ricavare facilmente tutte le proprietà della $\Gamma$.

**OSS:** molte delle rappresentazioni che abbiamo trovato si possono usare per calcolare la costante $\gamma$

**Idea:** Possiamo generalizzare questo approccio a derivate logaritmiche superiori, e otteniamo la funzione poligamma.
$$
	\psi^{(k)}=\frac{d^k}{dz^k} \log \Gamma(z)=\frac{d^{k-1}}{dz^{k-1}}\psi (z)
$$
Molte delle rappresentazioni integrali di $\psi$ sono generalizzabili per la funzione poligamma andando a introdurre le derivate superiori.
Ad esempio:
$$
	\psi^{(k)}=\sum^\infty_{n=0} \frac{(-1)^{k+1}(k+1)!}{(n+z)^{k+1}}
$$
$$
	\psi^{(k)}=-\int^1_{0} dx\, \frac{x^{z-1}(\log z)^k}{1-x}
$$
Il termine costante $\frac{1}{n+1}$ scompare derivando!

Molto spesso possiamo ricondurre serie infinite a somme di funzioni $\psi$.
Ad esempio, supponiamo di dover sommare la seguente serie:
$$
\begin{aligned}
\sum^\infty_{k=1} \frac{1}{(k+a)(k+b)}&=\frac{1}{b-a}\sum^\infty_{k=1}\left( \frac{1}{k+a}-\frac{1}{k+b} \right)=\\
&=\frac{1}{b-a}\sum^\infty_{k=1}\left( \frac{1}{k-1+a+1}-\frac{1}{k-1+b-1} \right)=\\
&=\frac{1}{b-a}\sum^\infty_{n=0}\left( \frac{1}{n+a+1}-\frac{1}{n+b+1} \right)=\\
&=\frac{1}{b-a}\sum^\infty_{n=0}\left[ -\gamma+\frac{1}{n+1}-\frac{1}{n+(b+1)}-\left( -\gamma+\frac{1}{n+1}-\frac{1}{n+(a+1)} \right) \right]
\end{aligned}
$$
Ora posso andare ad accoppiare i termini della serie in modo diverso:
$$
	\sum^\infty_{k=1} \frac{1}{(k+a)(k+b)}=\frac{1}{b-a}(\psi(b+1)-\psi(a+1))
$$
Questo è il modo più semplice per andare a sommare la serie perchè non avendola mai spezzata, non ho mai scritto pezzi di serie divergenti.

**Oss:** Non sappiamo ancora come si comporta $\Gamma$ all'infinito. Per farlo dobbiamo aspettare di vedere gli sviluppi asintotici. Ci darà la formula di stirling!

### Esercizi

**Esercizio 1**
$$
	f(z)=\sin \frac{\pi}{z} \Gamma\left( \frac{1}{2z}+1 \right)
$$
Studiare le singolarità isolate e calcolarne il residuo in ogni singolarità isolata
$$\sin \frac{\pi}{z}$$
Ha zeri in $\frac{\pi}{z}=k\pi$  dunque $z_{k}=\frac{1}{k}$ con $k\in \mathbb{Z}$ è un punto di accumulazione di zeri.
 $\implies z=0$ ho una singolarità essenziale.
$$
	\Gamma\left( \frac{1}{2z}+1 \right)
$$
$\frac{1}{2z}+1=-n$ con $n=0,1,2,\dots$
Cioè $\frac{1}{2z}=-l$ con $l=1,2,3,\dots$
$z_{l}=-\frac{1}{2l}$ sono poli di semplici della Gamma.
Questi punti sono tutti un sottoinsieme di $z_{k}$, dunque non ho singolarità isolate, ma solo la singolarità essenziale causata dal seno.

Quindi riassumendo: non ho singolarità in $z\neq 0$ e in $z=0$ ho una singolarità essenziale.
Ulteriormente ho zeri semplici in $z_{k}=\frac{1}{k}$ con $k=1,2,\dots \cup k=-1,-3,-5,\dots$

Per dimostrare che $z_{l}=-\frac{1}{2l}$ sono poli semplici sviluppando la funzione $\Gamma$ in un modo furbo, conviene sempre verificare che siano proprio semplici.
$$
	\Gamma\left( \frac{1}{2z}+1 \right)= \frac{\Gamma\left( \frac{1}{2z}+1+n \right)}{\left( \frac{1}{2z}+1 \right)\left( \frac{1}{2z}+2 \right)\dots\left( \frac{1}{2z}+n \right)}
$$
$$
	\frac{1}{2z+n}=\frac{2z}{1+2nz}
$$
E vediamo i poli semplici.
Alternativamente:
$$
	\Gamma\left( \frac{1}{2z}+1 \right)=\frac{\pi}{\sin\left( \frac{1}{2z}+1 \right)} \frac{1}{\Gamma\left( -\frac{1}{2z} \right)}
$$
Nei punti in cui $\frac{1}{2z}+1$ sono interi negativi, $\Gamma\left( -\frac{1}{2z} \right)$ non si annulla mai, e per studiare gli zeri mi basta studiare il comportamento del senp.

Non sappiamo ancora sviluppare la Gamma per argomenti che vanno a infinito, dunque non sappiamo ancora sviluppare questa funzione in un intorno di $z=0$.

Ma, poichè non ho altre singolarità e la funzione è monodroma, posso studiare il residuo col teorema dei residui.
$$
	\text{Res}f_{0}=-\text{Res}f_{\infty}
$$
$$
	f \underset{z\to \infty}{\sim} \frac{\pi}{z}\Gamma(1)=\frac{\pi}{z}\implies \text{Res} f_{\infty}=-\pi
$$
e:
$$
	\underset{z=0}{\text{Res}}[f(z)]=\pi
$$

**Esempio 2**

$$
	I=\oint_{\gamma} \Gamma\left( 1+\frac{4}{z^2} \right)dz
$$
Con $\gamma$:
![[Pasted image 20261023095918.png|319]]

Posso calcolare l'integrale con il teorema dei residui.
Studio le singolarità della $\Gamma$.
Ha singolarità in $1+\frac{4}{z^2}=-n$ con $n=0,1,2,\dots$
Cioè:
$$
	\frac{4}{z^2}=-k \qquad k=1,2,\dots
$$
$$
	\implies z^2=-\frac{4}{k}\to z_{k\pm}=\pm \frac{i 2}{\sqrt{ k }}
$$
Cioè $2i$, $\frac{2i}{\sqrt{ 2 }}, \frac{2i}{\sqrt{ 3 }},\dots$ e gli stessi punti con segno invertito.
Vediamo dal cammino che l'unico punto esterno a $\gamma$ è $z=-2i$.
Questa volta $z=0$ ha una singolarità non isolata, perchè è un punto di accumulazione di poli.
Fortunatamente posso calcolare l'integrale col teorema dei residui.
$$
	I=-2\pi i[\underset{z=-2i}{\text{Res}}f+\underset{z=\infty}{\text{Res}f}]
$$
Ma il residuo all'infinito è nullo perchè la funzione è pari, quindi nello sviluppo non compare $\frac{1}{z}$.
Mi basta calcolare il residuo in $z=-2i$.
$$
	\Gamma\left( 1+\frac{4}{z^2} \right)=\frac{\Gamma\left( 2+\frac{4}{z^2} \right)}{1+\frac{4}{z^2}}=z^2 \frac{\Gamma\left( 2+\frac{4}{z^2} \right)}{(z-2i)(z+2i)}
$$
$$
	\lim_{ z \to -2i }z^2 \frac{\Gamma\left( 2+\frac{4}{z^2} \right)}{z-2i}=-4 \frac{\Gamma(1)}{-4i} =-i
$$
e 
$$
	I=-2\pi
$$
