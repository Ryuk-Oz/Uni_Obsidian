
Il metodo di Laplace si può facilmente generalizzare per funzioni che non hanno il massimo in uno dei due estremi di integrazione, ma il massimo assoluto cade tra gli estremi. In questo caso dovremo richiedere l'annullamento della derivata e questo avrà delle conseguenze sullo sviluppo.

Occupiamoci di questo caso.
$$
	I(t) = \int^b_{a} e^{ t f(x) } g(x) \, dx ; \qquad t\to \infty, t\in D
$$
**Teorema**:
- Hp: $\exists x_{0} \in [a,b] \, / \, x_{0}$ massimo relativo e assoluto per $f(x)$, cioè: $f'(x_{0})=0$ e 
  $\forall\varepsilon >0 \; \exists A, A<f(x_{0})\; / \; f(x)<A \, \forall x \not\in I_{\varepsilon}(x_{0})$.
  $f$ e $g$ regolari in $[a,b]$
- Th:
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty \\
	&t \in D
	\end{aligned}}{\sim} \sqrt{ 2\pi } g(x_{0}) e^{ tf(x_{0}) } \frac{1}{\sqrt{ |g''(x_{0})| }} t^{-1/2} \left( 1+O\left( \frac{1}{t} \right) \right)
$$
Dimostrazione:
$f$ e $g$ regolari, allora posso svilupparle con taylor.
$$
	f(x) \sim f(x_{0})+\frac{1}{2} f''(x_{0})(x-x_{0})^2+\sum^\infty_{n=3} f_{n}(x-x_{0})^n
$$
$$
	g(x)\sim g(x_{0})+g'(x_{0})(x-x_{0})+\dots=\sum_{l=0}^\infty g_{l} (x-x_{0})^l
$$
Dunque:
$$
	I(t)=\int^b_{a} dx\, e^{ tf(x_{0}) } e^{ (t/2) f''(x_{0})(x-x_{0})^2 } e^{ t \sum^\infty_{n=3} f_{n} (x-x_{0})^n } \sum^\infty_{l=0} g_{l}(x-x_{0})^l
$$
Chiamiamo:
$$
	H(x,t) = e^{ t \sum^\infty_{n=3} f_{n} (x-x_{0})^n } \sum^\infty_{l=0} g_{l}(x-x_{0})^l
$$
A questo punto cambiando variabile, $x-x_{0}=w$ otteniamo:
$$
	I(t) = e^{ tf(x_{0}) } \int^{b-x_{0}}_{a-x_{0}} dw \, e^{ -(t/2)f''(x_{0})w^2 } \underbrace{H(x,t)}_{g_{0}+\sum^\infty_{l=1} h_{l}(t)w^l}
$$
Ho un integrale contenente un fattore gaussiano.

Vorremmo mandare gli estremi di integrazione a infinito.
Facciamo un passo indietro e riconduciamoci al caso che già sappiamo studiare.
$$
	\begin{aligned}
	\int^\infty_{c} e^{ -t(y^2+c^2-c^2) } dy&=e^{ -tc^2 }\int^\infty_{c} e^{ -t(y^2-c^2) } dy\\
	&=\frac{e^{ -tc^2 }}{2} \int^\infty_{0} dx \frac{1}{\sqrt{ x^2-c^2 }} e^{ -tx }=O(e^{ -tc^2 })
	\end{aligned}
$$
Posso fare lo stesso ragionamento anche per l'intervallo $(-\infty,-c)$ (o lo vedo semplicemente sfruttando la parità).

La stessa cosa vale anche per una funzione $g(y)$ trasformabile con Laplace:
$$
	\int^\infty_{c} g(y)e^{ -t(y^2+c^2-c^2) } dy=\frac{e^{ -tc^2 }}{2}\underbrace{\int^\infty_{0} dx \frac{g(\sqrt{ x^2-c^2 })}{\sqrt{ x^2-c^2 }}e^{ -tx }}_{\text{è limitata perchè è una TL}} = O(e^{ -tc^2 })
$$
Dunque posso trascurare le cose anche per $I(t)$.
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty\\
	&t \in D
	\end{aligned}}{\sim} e^{ tf(x_{0}) }\int^\infty_{-\infty} e^{ -t/2\; |f''(x_{0})|w^2 }(g_{0}+\cancel{h_{1}(t)w}+h_{2}(t)w^2+\dots)
$$
Posso svolgere singolarmente i vari termini.
L'intervallo è simmetrico, quindi le POTENZE DISPARI NON CONTRIBUISCONO.
Calcoliamo gli altri termini:
$$
	\begin{aligned}
	&\int^\infty_{-\infty} e^{ -tAw^2 } dw = \sqrt{ \frac{\pi}{tA} }\\
	&\int^\infty_{-\infty} e^{ -tAw^2 } w^2 dw = -\frac{d}{d(tA)} \sqrt{ \frac{\pi}{tA} }=+\frac{1}{2} \frac{\sqrt{ \pi }}{(tA)^{3/2}} =+\frac{1}{2} \sqrt{ \frac{\pi}{tA} } \frac{1}{tA}\\
	& \int^\infty_{-\infty} e^{ -tAw^2 } w^{2n} dw = (-1)^n \frac{d^n}{d(tA)^n}(-1)^n \frac{1}{2} \frac{3}{2} \frac{5}{2}\dots \frac{2n-1}{2} \sqrt{ \frac{\pi}{tA} } \frac{1}{(tA)^n}=\frac{(2n-1)!!}{2^n} \sqrt{ \frac{\pi}{tA} } \frac{1}{(tA)^n}
	\end{aligned}
$$
Il termine dominante è chiaramente il primo. 
$$
	I(t) \underset{\begin{aligned}
	&t\to \infty\\
	&t\in D
	\end{aligned}}{\sim} e^{ tf(x_{0}) }\int^\infty_{-\infty} e^{ -t/2\; |f''(x_{0})|w^2 }(g_{0}+\cancel{h_{1}(t)w}+h_{2}(t)w^2+\dots) \sim g_{0} e^{ tf(x_{0}) } \sqrt{ \frac{2\pi}{t|f''(x_{0})|} }
$$


**Proveniente da:** [[Metodo di Laplace per lo studio asintotico di integrali (in campo reale)]]