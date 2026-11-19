
Approssimazione di integrali sul piano complesso tramite sviluppi asintotici.
$$
	I(t)=\int^b_{a, \gamma} e^{ tf(z) }g(z)dz, \quad t\to +\infty, \quad f,g \text{ analitiche in } E\in \mathbb{C}; \quad \gamma\in E
$$
Supponiamo ulteriormente che $\exists z_{0} \in E:f'(z_{0})=0$.
Per il teorema di Cauchy posso deformare $\gamma$, cammino di integrazione, fino a farla passare per $z_{0}$. Chiamo questa nuova curva $\gamma'$.

![[Pasted image 20261111135654.png|563]]

Se riesco a far sì che $\mathrm{Re}f(x)$ abbia un massimo, allora posso riuscire a dimostrare che:
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty \\
	&t\in D
	\end{aligned}}{\sim} e^{ i\varphi }e^{ tf(z_{0}) }g(z_{0})\sqrt{ \frac{\pi}{At} }\left( 1+O\left( \frac{1}{t}\right) \right)
$$
con $A$, $\varphi$, parametri legati a $f$ e $\gamma$.
Iniziamo sviluppando $f(z)$ attorno a $z_{0}$:
$$
	f(z)=f(z_{0})+\frac{1}{2}f''(z_{0})(z-z_{0})^2+O((z-z_{0})^3)
$$
Per ogni intorno $I_{\delta}(z_{0})$ posso riscrivere $\frac{1}{2}f''(z_{0})=A e^{ i\alpha }$.
E posso riscrivere:
$$
	f(z)-f(z_{0})=Ae^{ i\varphi }(z-z_{0})^2+\dots
$$
In un intorno sufficientemente piccolo, il pezzo di curva che attraversa $I_{\delta}(z_{0})$ è un pezzo di retta passante per l'origine, cioè il suo diametro. Dunque:
$$
	z-z_{0}=\rho e^{ i\varphi }
$$
con $-\delta < \rho < \delta$ e $\varphi$ fissato. (Si tratta della parametrizzazione dei punti della curva contenuti nell'intorno). Dunque:
$$
	f(z)-f(z_{0})=A\rho^2 e^{ i(\alpha+2\varphi) }
$$
Ne prendo parte immaginaria e parte reale.
$$
	\begin{cases}
	\mathrm{Re}f(z)-\mathrm{Re}f(z_{0})=A\rho^2\cos(\alpha+2\varphi) \\
	\mathrm{Im}f(z)-\mathrm{Im}f(z_{0})=A\rho^2\sin(\alpha+2\varphi)
	\end{cases}
$$
Cioè, nell'intorno di un punto stazionario di una funzione analitica $f$, nè la parte reale, nè la parte immaginaria di $f$ hanno un massimo o un minimo, hanno bensì un **punto a sella**. Il fatto che io veda un massimo o un minimo dipende dalla fase ($\alpha+2\varphi$) con cui attraverso $z_{0}$.
Noi sappiamo studiare bene funzioni reali attorno a un massimo, allora per studiare l'andamento di $\mathrm{Re}f(z)$ ci interessa il caso in cui $\cos(\alpha+2\varphi)<0$. 
La scelta migliore che possiamo fare è attraversare l'intervallo con la fase data da:
$$
	\cos(\alpha+2\varphi)=-1\implies \alpha+2\varphi=\pi+2k\pi
$$
$$
	\varphi=\frac{\pi}{2}-\frac{\alpha}{2}+k\pi
$$
In base a $k$, posso avere 2 situazioni opposte:
$$
	\begin{cases}
	\varphi=\frac{\pi}{2}-\frac{\alpha}{2} \\
	\varphi=\frac{\pi}{2}-\frac{\alpha}{2}+\pi
	\end{cases}
$$
Ma io sto studiando una funzione complessa, allora mi interessa anche la parte immaginaria, che mi da un contributo del tipo $e^{ it\mathrm{Im}f(x) }$.
Dal lemma di Riemann sappiamo che:
$$
	\int^\infty_{-\infty} dx \; e^{ itx }g(x)=0
$$
Quello che fa $f(x)$ è cambiare il "tasso" con cui l'argomento dell'integrale oscilla, e il risultato è sempre nullo.
Questo è apparentemente problematico. A cosa mi serve studiare il max della parte reale se poi l'argomento preso tutto insieme oscilla?
...MA... per gli angoli nei quali $\cos(\alpha+2\varphi)=-1$, ho che la parte immaginaria è stazionaria ed il contributo è puramente reale.

Come abbiamo visto nel caso reale, l'unico contributo significativo dello sviluppo è dato dall'intorno del massimo. Dunque:

$$
	I(t)\underset{\begin{aligned}
	&t\to \infty \\
	&t\in D
	\end{aligned}}{\sim} \int^{z_{0}+\delta e^{ i\varphi }}_{z_{0}-\delta e^{ i\varphi }} dz\, e^{ tf(z) } g(z)
$$
Sviluppiamo $f(z)$ e $g(z)$.
$$
	f(z)=f(z_{0})+\frac{1}{2}f''(z_{0})(z-z_{0})^2+\sum^\infty_{l=3}f_{l}(z-z_{0})^l
$$
$$
	g(z)=g(z_{0})+\sum^\infty_{k=1}g_{k}(z-z_{0})^k
$$
A questo punto parametrizzo $z-z_{0}$ usando $\rho$. ($z-z_{0}=\rho e^{ i\varphi }$).
$$
	dz=e^{ i\varphi }d\rho
$$
Dunque:
$$
	I(t)\sim\int^\delta_{-\delta} e^{ i\varphi } d\rho\, e^{ tf(z_{0}) }e^{ -tA\rho^2 }e^{ t\sum^\infty_{l=3} f_{l}\rho^l e^{ il\varphi } }\left( g(z_{0})+\sum^\infty_{k=1}g_{k}\rho^ke^{ ik\varphi } \right)
$$
Come abbiamo già fatto nel caso reale, questo $\sim \int^\infty_{-\infty}\dots$
$$
	I(t)\sim e^{ i\varphi }e^{ tf(z_{0}) }\int^\infty_{-\infty}d\rho e^{ -tA\rho^2 }(1+\dots)(g(z_{0})+\dots)
$$
Troncando la serie al primo termine abbiamo:
$$
	I(t)\sim e^{ i\varphi }e^{ tf(z_{0}) }g(z_{0})\int^\infty_{-\infty} d\rho \; e^{ -tA\rho^2 }=e^{ i\varphi }e^{ tf(z_{0}) }g(z_{0})\sqrt{ \frac{\pi}{At} }
$$

Supponiamo di voler fare andare $t\to \infty$ lungo una certa direzione $\theta$, nel caso reale che abbiamo già ampiamente discusso.
A quel punto, mi basta riparametrizzare $t$: $t'=te^{ i\theta }$, ora accorpo $e^{ i\theta }$ dentro a $f$ e mando $t\to \infty$. In questo modo mi sono ricondotto al caso complesso che abbiamo appena studiato.

Facciamo un esempio concreto:

$$
	I(t)= \int_{\gamma} e^{ 1/2\,t(z-1/z)} z^{-\nu-1} dz
$$
$z^{-\nu-1}$ è una funzione polidroma. Metto il taglio sul semiasse reale $\mathbb{R}_{-}$.
Con $\gamma$ curva che parte dall'origine e passa sopra il taglio.
Studiamo $f(z)$.
$$
	f(z)=\frac{1}{2}\left( z-\frac{1}{z} \right)
$$
$$
	f'(z)=\frac{1}{z}\left( 1+\frac{1}{z^2} \right)
$$
Cerchiamo i punti stazionari.
$f'(z)=0\implies z=\pm i$. $z_{1}=e^{ i\pi/2 }$, $z_{2}=e^{ -i\pi/2 }$.
Troviamo che $\mathrm{Re}f(z_{1})=\mathrm{Re}f(z_{2})=0$. Come scelgo la fase?
Vado avanti con il calcolo della derivata seconda.
$$
	f''(z)=-\frac{1}{z^3}
$$
$$
	\begin{cases}
	f''(z_{1})=-e^{-i 3\pi/2 }=e^{ \pm i\pi } e^{ -i{3}\pi/2 } \\
	f''(z_{2})=-e^{i 3\pi/2  }
	\end{cases}
$$
Mi concentro sullo studio di $z_{1}$.
$$
	\varphi=\frac{\pi}{2}+\frac{3}{4}\pi-\frac{\pi}{2}+k\pi
$$
L'ambiguità del $\pm i\pi$ che avevo in $f''(z_{1})$ è contenuta in $k$.
per $k=0$ ho $\varphi=\frac{3}{4}\pi$, per $k=1$ ho $\varphi=\frac{7}{4}\pi$

![[Pasted image 20261111145222.png]]
(MIGLIORA IL DISEGNO)
Quale deformazione di $\gamma$ uso?
Devo avere un massimo in $f(z_{0})$, dunque voglio passare solo per i punti in cui $\mathrm{Re}f(z)<\mathrm{Re}f(z_{0})=0$.
$$
	\mathrm{Re}f(z) = \frac{1}{2} \left( x-\frac{x}{x^2+y^2} \right)=0 \implies x(x^2+y^2-1)=0
$$
Cioè $\{ x=0 \}\cup \{ x^2+y^2=1 \}$. Come ci aspettavamo, sia $i$ che $-i$ si trovano nell'intersezione di questi 2 insiemi.
![[Pasted image 20261111145759.png]]
La curva verde è quella passante solo per regioni in cui $\mathrm{Re}f(z)<\mathrm{Re}f(z_{0})$, lungo quella curva, è vero che tutto il contributo dell'integrale viene dato dall'intorno di $i$.
Non sempre la disuquazione che ci viene fuori è risolvibile esattamente. Cosa ci salva? Posso sempre fare un ragionamento simile localmente.
Passiamo da $\varphi\to \varphi+\frac{\pi}{2}$ e $\alpha+2\varphi\to \alpha+2\varphi+\pi$, questa fase è quella corrispondente a un minimo della parte reale. A metà tra i 2 angoli si trova la fase per cui il coseno fa $0$. In questo modo posso dividere (localmente) l'intorno di $z_{0}$ in 4 quadranti, 2 in cui la $\mathrm{Re}f(z)>\mathrm{Re}f(z_{0})$ e 2 in cui $\mathrm{Re}f(z)<\mathrm{Re}f(z_{0})$. Guardando graficamente l'andamento delle curve possibili attraverso questi quadranti posso farmi una buona idea di quale sia la curva migliore.
Usando lo stesso ragionamento posso escludere il punto $-i$ (in questo esempio).

Dopo tutti questi ragionamenti, finiamo finalmente lo sviluppo.
$$
	(z-i)=\rho e^{ i 3\pi/4 }\implies z=e^{ i \pi/2 }(1+\rho e^{ i \pi/4 })
$$
$$
	\begin{aligned}
	z-\frac{1}{z}&=e^{ i\pi/2 }(1+\rho e^{ i \pi/4 })-e^{ -i \pi/2 } \frac{1}{1+\rho e^{ +i \pi/4 }}\\
	&=i(1+\rho e^{ i\pi/4 }+1-\rho e^{ +i \pi/4 }+\rho^2e^{ i\pi/2 }-\rho^3e^{ +i 3\pi/4 }+\dots)=\\
	&=2i-\rho^2-i\rho^3 e^{ i 3\pi/4 }+\dots
	\end{aligned}
$$
$$
	I(t)=\int^\delta_{-\delta} e^{ i 3\pi/4 }d\rho \,e^{ it } e^{ -t/2 \, \rho^2}e^{ t(\dots) }e^{ i\pi/2 \, (-\nu-1)}(1+\rho e^{ i\pi/4 })^{-\nu-1}
$$
Mi interessa solo il primo ordine (fai i calcoli completi a csa):
$$
	I(t)\sim e^{ i\pi/4 } e^{ i\pi/2 \; \nu}e^{ it } \sqrt{ \frac{2\pi}{t} }
$$
Impostazione di un altro esercizio (finisci a casa):
$$
	\Gamma(\nu)=\int^\infty_{0} dx \, e^{ -x } x^{\nu-1}
$$
Facciamo lo sviluppo per $\nu\to i\infty$. $\nu=it+\varepsilon$:
$$
	=\int^\infty_{0} dx \, e^{ -x } x^{\varepsilon-1}x^{it}
$$
Cambio variabile: $x=it\, dz\to dx=it\, dz$.
$$
	\Gamma(\nu)=\int_{0}^{-i\infty} itdz\, e^{ -itz } (itz)^{\varepsilon-1} (itz)^{it}=(it)^{it+\varepsilon} \int_{0}^{-i\infty} dz\, e^{ it(-z+\log z) }z^{\varepsilon-1}
$$
Ora posso studiare la funzione a esponente e cercarne i punti stazionari.
$$
	f(z)=i(-z+\log z)
$$
$$
	f'(z)=i\left( -1+\frac{1}{z} \right), \quad f'(z)=0\to z=1
$$
FINISCI A CASA







