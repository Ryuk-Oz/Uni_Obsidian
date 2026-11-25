
riprendendo la lezione precedente:
$$
		\chi_{nl}(\rho)=N_{nl} \rho^{l+1} e^{ -\rho/2 } L_{n-l-1}^{2l+1}(\rho)
$$
con i polinomi di Laguerre generati da:
$$
		F_{\beta}(x,z)= \frac{1}{(1-z)^{\beta+1}} e^{ -zx/(1-z) }\equiv \sum_{p=0}^\infty L_{p}^{\beta}(x) z^{p}
$$
I polinomi di Laguerre sono ortonogonali con funzione peso $e^{-x}x^{\beta}$.
$$
	\int^\infty_{0}dx\; e^{ -x } x^{\beta} L^{\beta}_{p}(x)L^{\beta}_{p'}(x)=k^\beta_{p}\delta_{pp'}
$$
MA dentro a $\chi_{nl}$ ho il $\beta$ di $x^\beta$ diverso da quello che compare nei polinomi.
Però con la relazione di ricorrenza posso sempre ricondurmi al caso giusto.
Risolvendo l'integrale troviamo:
$$
	k^{\beta}_{p}= \frac{\Gamma(\beta+p+1)}{p'}
$$
E troviamo come costante di normalizzazione:
$$
	N_{nl}=\sqrt{ \frac{\alpha_{n}(n-l-1)!}{2n(n+l)!} }
$$
con:
$$
	\alpha_{n}\equiv 2 \frac{\sqrt{ -2\mu E }}{\hbar}
$$
ricordando:
$$
	E_{n}=\frac{\mu Z^2e^4}{2\hbar^2} \frac{1}{n^2}
$$
dunque:
$$
	\alpha_{n}\equiv \frac{2\mu Ze^2}{\hbar^2} \frac{1}{n}
$$
a questo punto ricordiamo anche la definizione del raggio di Bohr:
$$
	a_{0}= \frac{\hbar^2}{\mu e^2}
$$
e alla fine si ha:
$$
	\alpha_{n}= \frac{2Z}{a_{0}} \frac{1}{n}
$$

Unendo a queste $\chi_{nl}$ anche la parte derivante dalle armoniche sferiche otteniamo:
$$
	\begin{aligned}
	&\psi_{nlm}(r,\theta,\varphi)= \underbrace{\frac{1}{r}\chi_{nl}(\alpha_{n}r)}_{\equiv \varphi(r)} Y_{l}^m (\theta,\varphi) =\\
	&=\frac{2}{n^2} \left( \frac{Z}{a_{0}} \right)^{3/2} \sqrt{ \frac{(n-l-1)!}{(n+l)!} }\left( \frac{2Z}{a_{0}} \frac{r}{n} \right)^{l} e^{ -Zr/(na_{0}) } L^{2l+1}_{n-l-1} \left( \frac{2Zr}{na_{0}} \right)Y^m_{l}(\theta,\varphi)
	\end{aligned}
$$
e abbiamo $[\psi]=L^{-3/2}$ come atteso.
Disegnando questa densità di probabilità ritroviamo gli orbitali.
Queste funzioni d'onda sono correttamentr normalizzate.
$$
	(\psi_{nlm},\psi_{n'l'm'})\equiv \int^\infty_{0} dr\, r^2 \int^1_{-1} d\cos \theta \, \int^{2\pi}_{0} d\varphi\; \psi^*_{nlm}(\vec{r})\psi_{n'l'm'}(\vec{r})=\delta_{nn'}\delta_{ll'}\delta_{mm'}
$$
A questo punto il primo livello energetico è unico:
$$
	\psi_{1,0,0} (\vec{r})= \frac{1}{\sqrt{ \pi }}\left( \frac{Z}{a_{0}} \right)^{3/2} e^{ -Zr/a_{0} }
$$
**OSS:**
$$
	Y^m_{l}(\theta,\varphi)\propto e^{ im\varphi }\implies |Y^m_{l}(\theta,\varphi)|^2=\rho(\theta)
$$
cioè il modulo quadro ha simmetria cilindrica attorno all'asse di quantizzazione da me scelto.
Ulteriormente:
$$
	\begin{aligned}
	\rho_{nlm}(\vec{r})d^3r&\equiv |\psi_{nlm}(\vec{r})|^2 d^3r =\\
	&=|\psi_{nlm}(\vec{r})|^2 r^2 dr \; d(\cos\theta)\; d\varphi=\\
	&=|\chi_{nl}(r)|^2dr |Y^m_{l}(\theta,\varphi)|^2 \cdot {2}\pi\, d(\cos \theta)=\\
	&=\rho_{nl}(r)dr\; \cdot2\pi \rho^m_{l}(\theta)\;d(\cos \theta)
	\end{aligned}
$$
cioè posso fattorizzare la densità di probabilità.

Proviamo a farlo nell'esempio di prima.
$$
	\rho_{1,0} (r)= \frac{1}{\pi} \left( \frac{Z}{a_{0}} \right)^{3/2} r^2 e^{ -(2Z/a_{0})\cdot r }
$$
e vediamo che $r_{max}= \frac{a_{0}}{Z}$.


### Trasformazioni, simmetrie e leggi di conservazione

#### Proprietà di trasformazione dei campi CLASSICI

Consideriamo un campo scalare in $\mathbb{R}^3$:
$$
	\varphi=\varphi(x,y,z)
$$
Scalare perchè ha una sola componente, ad esempio la temperatura.
Facciamo una qualsiasi trasformazione di coordinate.
$$
	\vec{x} \longrightarrow \vec{x}'(\vec{x})
$$
cioè:
$$
	\begin{cases}
	x'=x'(x,y,z) \\
	y'=y'(x,y,z) \\
	z'=z'(x,y,z)
	\end{cases}
$$
Come si trasforma $\varphi$?
$$
	\varphi \longrightarrow \varphi':\varphi'(x',y',z')=\varphi(x,y,z)
$$
Basti pensare alla temperatura misurata in un punto con 2 sistemi di coordinate diverse. Il valore misurato deve rimanere invariato ma cambiano le variabili, dunque deve cambiare anche la funzione che mi dà la temperatura.

Come posso caratterizzare $\varphi'$?
Dobbiamo calcolare $\varphi$ e $\varphi'$ con gli stessi argomenti.

Partiamo dallo studio in $d=1$.
Faccio una trasformazione di coordinate generica $x'=f(x)$.
$$
	\implies \varphi'(x')=\varphi'(f(x))=\varphi(x)
$$
Dunque:
$$
	\varphi'(x)=\varphi(f^{-1}(x))
$$
Occupiamoci del caso in assoluto più semplice, traslazioni in $d=1$.
Definiamo:
$$
	f_{a}(x)=x+a \implies f_{a}^{-1}(x)=x-a
$$
a questo punto:
$$
	\varphi'(x+a)=\varphi(x) \quad \text{e} \quad \varphi'(x)=\varphi(x-a)
$$
Prendiamo $a$ infinitesimo abbiamo:
$$
	\implies \varphi(x-a)=\varphi(x)-a\, \frac{d\varphi}{dx}+O(a^2)
$$
Per $a$ finito trovo invece:
$$
	\varphi'(x)=\varphi(x-a)=\left[ \sum^\infty_{n=0} \, \frac{1}{n!} (-a)^n\, \frac{d^n}{dx^n} \right] \varphi(x)\equiv e^{ -a \frac{d}{dx} } \varphi(x)
$$
e abbiamo trovato il cosiddetto operatore di traslazione:
$$
	T(a)= \exp\left[ -a \frac{d}{dx} \right]
$$
Possiamo dire che la derivata sia il generatore dell'operatore di traslazione.

**OSS:** abbiamo implicitamente richiesto che $\varphi$ sia $C^{\infty}$ ma lo facciamo sempre quindi sticazzi.

Posso chiedermi di che tipo sia l'operatore di $T(a)$? Per fare dei ragionamenti più fini sul tipo di operatore, è necessario che il campo $\varphi(x)$ appartenga ad uno spazio NORMATO (cioè è definito un prodotto scalare), ad esempio $L^2(\mathbb{R})$.
In particolare, in $L^2(\mathbb{R})$ con il solito prodotto scalare:
$$
	\left( \frac{d}{dx} \right)^{\dagger} =-\frac{d}{dx}\implies [T(a)]^{\dagger} =[T(a)]^{-1}
$$
cioè l'operatore di traslazione è antihermitiano.
Questo non ci stupisce, infatti abbiamo già visto che:
$$
	(T(a))^{-1}=T(-a)=T^{\dagger}(a)
$$

Ora, ha anche senso chiederci di quanto cambia la funzione:
$$
	\delta \varphi(x)\equiv \varphi'(x)-\varphi(x)=-a \frac{d\varphi}{dx}
$$

Spostiamoci in $\mathbb{R}^3$ e studiamo le rotazioni (attorno all'asse z).
![[Pasted image 20261124095918.png|700]]
$$
	\varphi_{p}\to \varphi'_{p} = \varphi_{p}-\varphi
$$
Posso rappresentare questa trasformazione tramite una matrice.
$$
	\begin{pmatrix}
	x' \\
	y' \\
	z' 
	\end{pmatrix}=\begin{pmatrix}
	\cos \varphi & \sin \varphi & 0 \\
	-\sin \varphi & \cos \varphi & 0 \\
	0 & 0 & 1
	\end{pmatrix}\begin{pmatrix}
	x \\
	y \\
	z
	\end{pmatrix}\equiv R_{z}(\varphi)(\vec{x})
$$
Similmente a quanto fatto prima, cerchiamo la matrice inversa:
$$
	R^{-1}_{z}(\varphi)=R_{z}(-\varphi)=R_{z}^T(\varphi)
$$
Cioè le rotazioni sono rappresentate da matrici ortogonali, cioè sono unitarie e reali.
Cosa succede quando facciamo variazioni infinitesime di $\varphi$?
$$
	R_{z}(\varphi)=\begin{pmatrix}
	1 & \varphi & 0 \\
	-\varphi & 1 & 0 \\
	0 & 0 & 1
	\end{pmatrix}=\mathbb{1}_{3\times 3}+\begin{pmatrix}
	0 & \varphi & 0 \\
	-\varphi & 0 & 0 \\
	0 & 0 & 0
	\end{pmatrix}=\mathbb{1}+\varphi \, r_{z}
$$
dove $r_{z}$ sono le rotazioni in 2 dimensioni.
$$
	r_{z}=\begin{pmatrix}
	0 & 1 & 0 \\
	-1 & 0 & 0 \\
	0 & 0 & 0
	\end{pmatrix}
$$
che sono antisimmetrica.
Ci troviamo nella stessa situazione di prima (antihermitiano $\to$ antisimmetrico)!
A questo punto torniamo alla domanda iniziale, com'è fatto $\Phi'$?(sono passato alla maiuscola per evitare confusione nella notazione)
Mi aspetto che una rotazione attorno all'asse $z$ sia interpretabile come una traslazione di $\varphi$.
$$
	\mathcal{R}_{z}(\delta \varphi)\Phi(r,\theta,\varphi)=\Phi'(r,\theta,\varphi)=\Phi(r,\theta,\varphi-\delta \varphi)
$$
Studiamolo attraverso un esempio.
$$
\begin{aligned}
	\Phi(x,y,z)&=xyze^{ -r^2 }=(x'\cos \delta \varphi-y'\sin \delta \varphi)(x'\sin \delta \varphi+y'\cos \delta \varphi)z' e^{ -r'^2 }= \\
&=[(x'^2-y'^2)\sin \delta \varphi \cos \delta \varphi+x'y'(\cos^2\delta \varphi-\sin^2\delta \varphi)]z' e^{ -r'^2 }=\\
&=\left[ \frac{x'^2-y'^2}{2} \sin(2\delta \varphi) + x'y' \cos(2\delta \varphi)\right] z' e^{ -r'^2 }\equiv \Phi'(x',y',z')
\end{aligned}
$$
Dunque:
$$
	\Phi'(x,y,z)=\left[ \frac{x^2-y^2}{2} \sin(2\delta \varphi)+xy\cos(2\delta \varphi) \right] z e^{ -r^2 }
$$
A questo punto posso scrivere la differenza tra i 2:
$$
	\delta \Phi(x,y,z)\equiv \Phi'(x,y,z)-\Phi(x,y,z)
$$
Per trasformazioni infinitesime, ho che $\sin(2\delta \varphi)\sim 2\delta \varphi$ e $\cos(2\delta \varphi)\sim 1$.
Dunque:
$$
	\Phi'(x,y,z)=[(x^2-y^2)\delta \varphi+xy]ze^{ -r^2 }
$$
E:
$$
	\delta \Phi(x,y,z)=\frac{\delta \phi (x^2-y^2)}{xy} \Phi(x,y,z)
$$
Ci aspettiamo che la trasformazione dipenda dalla derivata di $\varphi$ (perchè sto traslando l'angolo), cioè:
$$
	\frac{ \partial  }{ \partial \varphi }=x \frac{ \partial  }{ \partial y }-y \frac{ \partial  }{ \partial x }   
$$
Applicando questa derivata a $\Phi(x,y,z)$ troviamo:
$$
	\left( x \frac{ \partial  }{ \partial y }-y \frac{ \partial  }{ \partial x }    \right) \Phi(x,y,z)= \frac{x^2-y^2}{xy}\Phi(x,y,z)
$$
dunque:
$$
	\delta \Phi(x,y,z)\propto \frac{ \partial  }{ \partial \varphi } \Phi(x,y,z)
$$
che è esattamente la stessa situazione che avevamo trovato nel caso delle traslazioni.







