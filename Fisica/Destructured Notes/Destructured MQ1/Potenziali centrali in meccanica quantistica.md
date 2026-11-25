
**Essenziale:** [[Autofunzioni del momento angolare, armoniche sferiche]]

Nel caso di potenziali centrali sappiamo che le coordinate sferiche sono la scelta più comoda, ma abbiamo un problema, la presenza del laplaciano nell'eds. 
Riscriviamo quindi il laplaciano in coordinate sferiche.
Lo studio del laplaciano equivale allo studio di $|\vec{p}|^2$.
$$
	|\vec{p}|^2=\left| \frac{\vec{r}\cdot \vec{p}}{{r}}\right|^2+\left| \frac{\vec{r}\wedge \vec{p}}{r}\right|^2=p_{r}^2+\frac{|\vec{L}|^2}{r^2}
$$
Problema:
$$
	p_{r}\equiv \frac{\vec{r}\cdot \vec{p}}{r}
$$
non è Hermitiano nè, tantomeno, autoaggiunto!
$$
	\frac{\vec{r}\cdot \vec{p}}{r}=-i\hbar \frac{\vec{r}\cdot \vec{\nabla}}{r}=-i\hbar\left( \frac{x}{r}\frac{ \partial  }{ \partial x } +\frac{y}{r}\frac{ \partial  }{ \partial y } +\frac{z}{r}\frac{ \partial  }{ \partial z }  \right)=-i\hbar \frac{ \partial  }{ \partial r } 
$$
e $\frac{ \partial  }{ \partial r }$ non è Hermitiano quando usiamo la corretta misura di integrazione per le coordinate sferiche ($r^2 dr$).

Definisco un operatore autoaggiunto. Come?
Sfrutto il fatto che $(xp_{x})^{\dagger}=p_{x}x$.
$$
	p_{r}\equiv \frac{1}{2}\left( \frac{\vec{r}}{r}\cdot \vec{p}+\vec{p}\cdot \frac{\vec{r}}{r} \right)=-\frac{i\hbar}{2}\left( \frac{\vec{r}}{r}\cdot \vec{\nabla}+\vec{\nabla}\cdot \frac{\vec{r}}{r} \right)
$$
Voglio riscriverlo in maniera più furba, tale che agisca sempre a destra.
$$
\begin{aligned}

	\vec{\nabla}\cdot\left( \frac{\vec{r}}{r}f \right)&=\frac{\vec{r}}{r}\cdot \vec{\nabla f}+\frac{f}{r} \vec{\nabla}\cdot \vec{r}+\vec{r}f\nabla\left( \frac{1}{r} \right)=\\
	&=\frac{\vec{r}}{r} \cdot \vec{\nabla}f+\frac{3}{r}f-\frac{1}{r}f=\frac{\vec{r}}{r}\cdot \vec{\nabla}f+\frac{2}{r}f
\end{aligned}
$$
e ottengo:
$$
	p_{r}=-i\hbar \left( \frac{ \partial  }{ \partial r } +\frac{1}{r} \right)
$$
$$
	p_{r}^2=-\hbar^2\left( \frac{ \partial  }{ \partial r } +\frac{1}{r} \right)^2=-\hbar^2 \frac{1}{r^2}\frac{ \partial  }{ \partial r } \left( r^2 \frac{ \partial  }{ \partial r }  \right)=-\hbar^2 \left( \frac{ \partial^2  }{ \partial r^2 } +\frac{2}{r}\frac{ \partial  }{ \partial r }  \right)
$$
A questo punto è lecito chiedersi, $p_{r}^2$ è autoaggiunto o solo Hermitiano? Devo fare delle restrizioni sul dominio?

Immagino di avere $\psi(r)\sim \frac{1}{r}$ per $r\to{0}$, $\overset{?}{\in}L^2(\mathbb{R}^3)$
$$
	\int_{0}^\infty dr \, r^2 |\psi(r)|^2
$$
è sempre integrabile in $0$, già $\psi(r)\sim \frac{1}{r^2}$ non lo è.
Se vi applico $p^2_{r}$ invece? Se $\psi(r)\sim \frac{1}{r}$, allora $p^2_{r}\psi(r)\sim \frac{1}{r^3} \not\in L^2 (\mathbb{R}^3)$.
Dunque $\psi(r)$ non è nel dominio di $p^2_{r}$.

ricordando che $|\vec{p}|^2\to-\hbar^2 \Delta$:
$$
	\Delta = \frac{1}{r^2} \frac{ \partial  }{ \partial r } r^2 \frac{ \partial  }{ \partial r } -\frac{|\vec{L}|^2}{\hbar^2 r^2}
$$
Ora possiamo sostituire tutto nell'edS e risolvere per separazione di variabili.
$$
	\left( \frac{p_{r}^2}{2\mu}+\frac{|\vec{L}|^2}{2\mu r^2}+V(r)-E\right)\psi(\vec{r})=0
$$
fattorizzo la soluzione:
$$
	\psi(\vec{r})=\psi(r)Y(\theta,\varphi)
$$
e ottengo:
$$
	Y(\theta,\varphi)\left[ \frac{p^2_{r}}{2\mu}+V(r)-E \right]\psi(r)+\frac{\psi(r)}{2\mu r^2}|\vec{L}|^2 Y(\theta,\varphi)=0
$$
$$
	\frac{1}{\psi(r)}\left[ \left( \frac{p_{r}^2}{2\mu} \psi(r) \right)+V(r)-E \right]2\mu r^2=-\frac{1}{Y(\theta,\varphi)}|\vec{L}|^2Y(\theta,\varphi)=-\lambda
$$
e ottengo 2 equazioni:
$$
	|\vec{L}|^2Y(\theta,\varphi)=\lambda Y(\theta,\varphi)
$$
$$
	\left( \frac{p_{r}^2}{2\mu}+V(r)-E \right)\psi(r)=-\frac{\lambda}{2\mu r^2}\psi(r)
$$
La prima equazione ci dice che $Y(\theta,\varphi)$ è una qualsiasi armonica sferica, $Y^m_{l}(\theta,\varphi)$ e $\lambda=\hbar^2 l(l+1)$. 
Sostituiamo $\lambda$ nella seconda equazione:
$$
	-\frac{\hbar^2}{2\mu}\left( \frac{d^2}{dr^2}+\frac{2}{r} \frac{d}{dr} \right)\psi(r)+\left( V(r)+ \frac{\hbar l(l+1)}{2\mu r^2} \right)\psi(r)=E\psi(r)
$$
Equazione Radiale di Shrödinger.

**Lezione Associata:** [[9. Atomo di Idrogeno]]