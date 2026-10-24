
**Prerequisiti:** [[Definizione della funzione Gamma]]

Proviamo a sfruttare ciò che sappiamo per la funzione $\Gamma$ per provare a scrivere la funzione $\psi$ in forma integrale.
Ricordiamo che:
$$
	\Gamma(z)=\int^\infty_{0} e^{ -t } t^{z-1} dt
$$
$$
	\Gamma'(z)=\int^\infty_{0} e^{ ^-t } t^{z-1} \log t\, dt
$$
Per prima cosa voglio dimostrare che (Rappresentazione di Schwinger del Logaritmo):
$$
	I(t)=\int^\infty_{0} \frac{e^{ -x }-e^{ -xt }}{x} dx = \log(t) \qquad \mathrm{Re}(t)>0
$$
Presi singolarmente $\frac{e^{ -x }}{x}$ e $\frac{e^{ -xt }}{x}$ non sono integrabili vicino allo zero.
Consideriamo i 2 esponenziali insieme:
$$
	\frac{e^{ -x }-e^{ -xt }}{x} \underset{x\to_{0}}{\sim} \frac{1-x-1+xt+O(x^2)}{x} \sim t-1+O(x)
$$
La risultante è regolare in $x=0$ ed è integrabile.
A questo punto derivo da entrambi i lati e sfrutto il TFCI:
$$
	\frac{dI}{dt}=\int^\infty_{0} dx \frac{x}{x}e^{ -xt }=\frac{1}{t}=\frac{d}{dt}\log(t)
$$
Inoltre il punto iniziale è uguale: $I(1)=0=\log 1$.
Ho dunque dimostrato l'uguaglianza. $\blacksquare$

A questo punto posso andare a riscrivere $\Gamma'(z)$ nel seguente modo:
$$
\begin{aligned}
\Gamma'(z)&=\int^\infty_{0} \frac{dx}{x} \int^\infty_{0} dt \, e^{ -t } t^{z-1} (e^{ -x }-e^{ -xt })=\\
&=\int^\infty_{0} \frac{dx}{x} [e^{ -x }\Gamma(z)]-\underbrace{\int^\infty_{0} dt\, e^{ -t(x+1) }t^{z-1}}_{A} 
\end{aligned}
$$
Occupiamoci di calcolare $A$. Facciamo il seguente cambio di variabile: $w=t(x+1)$, $dw=(x+1)dt$
$$
	A=\int^\infty_{0} \frac{dw}{x+1} e^{ -w } \left( \frac{w}{x+1} \right)^{z-1}=\frac{1}{(x+1)^z} \Gamma(z) 
$$
Quindi possiamo riscrivere $\Gamma'(z)$ come:
$$
	\Gamma'(z)=\Gamma(z)\int^\infty_{0} \frac{dx}{x}\left[ e^{ -x }-\frac{1}{(x+1)^z} \right]
$$
Dunque possiamo andare a scrivere la funzione Digamma come:
$$
	\psi(z)=\int^\infty_{0} \frac{dx}{x}\left[ e^{ -x }-\frac{1}{(x+1)^z} \right]
$$
**Ricorda:** l'integrale converge solo se considero i 2 termini tutti insieme.

Cosa posso fare per studiare questo integrale?
Deformando il cammino di integrazione per girare attorno all'origine, l'integrale è uguale a:
$$
		\psi(z)=\int^\infty_{0} \frac{dx}{x} \left( e^{ -x }- \frac{1}{(x+1)^z} \right) =\lim_{ \varepsilon \to 0 } \int^\infty_{\varepsilon} \frac{dx}{x} \left( e^{ -x }- \frac{1}{(x+1)^z} \right) 
$$
A questo punto posso calcolare il secondo pezzo per $\varepsilon>0$
$$
	B=\int^\infty_{\varepsilon} \frac{dy}{y(1+y)^z} =\int^\infty_{\log(1+\varepsilon)} dx \, e^{ x } \frac{e^{ -xz }}{e^{ x }-1}\underset{\varepsilon\to_{0}}{\sim}\int^\infty_{\varepsilon} dx \, \frac{e^{ x-xz }}{e^{ x }-1}=\int^\infty_{\varepsilon}dx\, \frac{e^{ -xz }}{1-e^{ -x }}
$$
Dove abbiamo cambiato variabile: $1+y=e^{ x }\implies dy=e^{ x }dx$
Lo riporto nel limite di prima:
$$
	\lim_{ \varepsilon \to 0 }  \int^\infty_{\varepsilon} dx\, \left[ \frac{e^{ -x }}{x} - \frac{e^{ -xz }}{1-e^{ -x }} \right]
$$
E questo lo sappiamo calcolare. Ho trovato una ==**seconda** rappresentazione integrale== di $\psi$
$$
	\psi(z)=\int^\infty_{0} dx\,  \left[ \frac{e^{ -x }}{x} - \frac{e^{ -xz }}{1-e^{ -x }} \right]
$$
Proviamo ad aggiungere e togliere $\psi(1)$.
$$
\begin{aligned}
\psi(z)&=\psi(z)+\psi(1)-\psi(1)=\psi(z)-\gamma-\psi(1)=\\
&=\int^\infty_{0} dx\,  \left[ \frac{e^{ -x }}{x} - \frac{e^{ -xz }}{1-e^{ -x }} \right] -\gamma - \int^\infty_{0} dx\,  \left[ \frac{e^{ -x }}{x} - \frac{e^{ -x }}{1-e^{ -x }} \right] = \\
&= \int^\infty_{0} dx\,  \left[  \frac{e^{ -x }-e^{ -xz }}{1-e^{ -x }} \right]-\gamma
\end{aligned}
$$
E ho trovato una ==**terza** rappresentazione integrale==.
Ulteriormente potrei andare a chiamare $e^{ -x }=w\implies-e^{ -x }dx=dw\implies dx=-\frac{dw}{w}$
$$
	\psi(z)=-\gamma+\int^1_{0} \frac{dw}{w}\, \frac{w-w^z}{1-w}=-\gamma+\int_{0}^1 dw\, \frac{1-w^{z-1}}{1-w}
$$
E ho trovato una ==**quarta** rappresentazione integrale==.


**Lezione associata:** [[5. Funzione Digamma]]