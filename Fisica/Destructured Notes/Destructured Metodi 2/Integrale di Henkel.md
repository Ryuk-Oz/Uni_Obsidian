
Consideriamo il seguente integrale con argomento polidromo, dalla forma molto simile alla $\Gamma$.
$$
	I(z)=\int_{C_{H}}e^{ -t }t^{z-1} \, dt
$$
Scegliamo come cammino $C_{H}$ il cammino di Henkel, così costruito.
![[Pasted image 20261022211051.png]]

Integrando su questo cammino $I(z)$ è analitica $\forall z$, infatti il cammino passa attorno a $z=0$, punto che era problematico per $\Gamma$.

Occupiamoci di cercare una relazione tra l'integrale di Henkel e la $\Gamma$. Per farlo devo mettermi nella regione in cui esistono entrambi gli integrali, cioè $\mathrm{Re}(z)>0$.

Definiamo $I(z)$ per parti per ricondurlo a $\Gamma$:
$$
	\begin{aligned}
	I(z)&= \int^\varepsilon_{\infty} f_{+}(t)dt+ \int_{C_{\varepsilon}} f(t)dt+\int_{\varepsilon}^\infty f_{-}(t)dt =\\
	&=\int^\infty_{0} (f_{-}-f_{+})dt = \int^\infty_{0} (e^{ i 2\pi z } e^{ -t }t^{z-1}-e^{ -t }t^{z-1})dt=\\
	&=(e^{ i 2\pi z }-1)\int^\infty_{0} e^{ -t } t^{z-1} dt = (e^{ i 2 \pi z }-1)\Gamma(z)=\\
	&=e^{ i\pi z }(e^{ i\pi z }-e^{ -i\pi z })\Gamma(z)=2ie^{ i\pi z }\sin \pi z \Gamma(z)
	\end{aligned}
$$
Così facendo abbiamo ottenuto un ulteriore continuazione analitica di $\Gamma(z)$ valida in tutto il piano complesso:
___
$$
	\Gamma(z)=\frac{e^{ -i\pi z }}{2i\sin \pi z}I(z)
$$
___
Ricordando la [[Continuazione di Gamma usando la Beta]] troviamo:
$$
	\Gamma(z)=\frac{e^{ -i\pi z }}{2i\pi}\Gamma(z)\Gamma(1-z)I(z)
$$
Da cui:
$$
	\frac{1}{\Gamma(1-z)}=\frac{e^{ -i\pi z }}{2\pi i}I(z)
$$
A questo punto possiamo fare alcune osservazioni:
$$
\text{se }\,z=n\in \mathbb{Z}\implies I(n)=\oint_{0}dt\,e^{ -t }t^{n-1}
$$
I 2 tratti del cammino di Henkel che vanno a infinito sono uguali quando $z=n$ perchè la funzione diventa monodroma dunquer sto andando a integrare soltanto sul cerchio centrato in $z=0$.
Per $n>0$ l'argomento della funzione è regolare ovunque e $I(n)=0$ per il teorema di Cauchy.
Per $n=0$ calcolo l'integrale col teorema dei residui e ho $I(0)=2\pi i$.
Sempre usando il teorema dei residui trovo che per $n=-k$, $k>0$:
$$
	I(-k)=\frac{2\pi i}{k!} \frac{d^k}{dt^k}e^{ -t }|_{t=0}=\frac{2\pi i(-1)^k}{k!}
$$
Questo residuo si può facilmente calcolare anche per serie:
$$
	e^{ -t }t^{-n-1}=\sum^\infty_{k=0} \frac{(-1)^k}{k!} z^{k-n-1}=\dots \frac{(-1)^n}{n!} \frac{1}{t}
$$
Posso sfruttare questi risultati per studiare $\Gamma(z)$ intorno ai propri poli. Parto dallo sviluppo del seno:
$$
	\sin \pi z \underset{z\to-n}{\sim}0+\pi \cos \pi z|_{-n}(z+n)
$$
e lo uso per lo studio di $\Gamma(z)$:
$$
	\Gamma(z)\underset{z\to{0}}{\sim} \frac{2\pi i}{2\pi iz}=\frac{1}{z}
$$
$$
	\Gamma(z)\underset{z\to-n}{\sim} \frac{e^{ i 2\pi n }}{2i} \frac{(-1)^n}{n!}2\pi i \frac{1}{\pi \cos \pi n} \frac{1}{z+n}=\frac{(-1)^n}{n!} \frac{1}{z+n}
$$

**Lezione associata:** [[4.Funzione Gamma di Eulero]]