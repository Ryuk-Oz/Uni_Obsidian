
**Utile:** [[Algebra del momento angolare]]

L'algebra dei momenti angolari ha a che fare con il gruppo $SU(2)$ e $SO(3)$, cioè ha a che fare con le rotazioni.
Per tale motivo ha senso usare le coordinate polari sferiche.
Come convenzione scegliamo: $\varphi$ angolo azimutale, $\theta$ angolo zenitale.
$$
	\begin{cases}
	x = r\sin \theta \cos \varphi \\
	y=r\sin \theta \sin \varphi \\
	z=r\cos \theta
	\end{cases}
$$
Con $\theta \in[0,\pi]$, $\varphi \in[0,2\pi)$.
Dobbiamo calcolare la matrice Jacobiana della trasformazione:
$$
	\begin{cases}
	r=\sqrt{ x^2+y^2+z^2 } \\
	\varphi=\arctan \frac{x}{y} \\
	\theta=\arcsin \frac{z}{r}
	\end{cases}
$$
Anzichè usare le derivate ragioniamo con i differenziali:
$$
	\begin{cases}
	r^2=x^2+y^2+z^2 \implies r dr =xdx+ydy+zdz \\
	d\varphi = -\frac{y}{x^2+y^2}dx+\frac{x}{x^2+y^2}dy \\
	\cos \theta=\frac{z}{r}\implies-\sin \theta d\theta= -\frac{z}{r^3}(xdx+ydy+zdz)+\frac{dz}{r}
	\end{cases}
$$
dunque:
$$
	J=\begin{pmatrix}
	\frac{ \partial r }{ \partial x } = \sin \theta \cos \varphi & \frac{ \partial r }{ \partial y } = \sin \theta \sin \varphi & \frac{ \partial r }{ \partial z } =\cos \theta \\
	 \frac{ \partial \varphi }{ \partial x } =-\frac{\sin \varphi}{r\sin \theta} & \frac{ \partial \varphi }{ \partial y }= \frac{\cos \varphi}{r\sin \theta} & \frac{ \partial \varphi }{ \partial z } =0 \\
	 \frac{ \partial \theta }{ \partial x } =\frac{\cos \theta \cos \varphi}{r} & \frac{ \partial \theta }{ \partial y } =\frac{\cos \theta \sin \varphi}{r} & \frac{ \partial \theta }{ \partial z } =-\frac{\sin \theta}{r} 
	\end{pmatrix}
$$
Ora possiamo scrivere le componenti di $\vec{L}$ in coordinate sferiche.
$$
	\begin{aligned}
	L_{z}&=-i\hbar\left( x \frac{ \partial  }{ \partial y } -y\frac{ \partial  }{ \partial x }  \right)=\\
	&=-i\hbar\left[ x\left( \frac{ \partial r }{ \partial y } \frac{ \partial  }{ \partial r } +\frac{ \partial \varphi }{ \partial y } \frac{ \partial  }{ \partial \varphi } +\frac{ \partial \theta }{ \partial y } \frac{ \partial  }{ \partial y }  \right)-y\left( \frac{ \partial r }{ \partial x } \frac{ \partial  }{ \partial r } +\frac{ \partial \varphi }{ \partial x } \frac{ \partial  }{ \partial \varphi } +\frac{ \partial \theta }{ \partial x }\frac{ \partial  }{ \partial \theta }   \right) \right]\\
	&=-i\hbar\left[ r\sin \theta \cos \varphi\left( \cancel{\sin \theta \sin \varphi \frac{ \partial  }{ \partial r }} +\cancel{\frac{\cos \theta \sin \varphi}{r}\frac{ \partial  }{ \partial \theta }} +\frac{\cos \varphi}{r\sin \theta} \frac{ \partial  }{ \partial \varphi } \right) \\
	-r\sin \theta \sin \varphi \left( \cancel{\sin \theta \cos \varphi \frac{ \partial  }{ \partial r }} +\cancel{\frac{\cos \theta \cos \varphi}{r}\frac{ \partial  }{ \partial \theta }} -\frac{\sin \varphi}{r\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right)\right]=\\
	&=-i\hbar \frac{ \partial  }{ \partial \varphi } 
	\end{aligned}
$$
**OSS:** $L_{z}$ assomiglia all'operatore impulso
Posso calcolare anche $L_{x}$ e $L_{y}$:
$$
	L_{x}=i\hbar \left[ \sin \varphi \frac{ \partial  }{ \partial \theta } +\frac{\cos \varphi \cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right]
$$
$$
	L_{y}=-i\hbar\left[ \cos \varphi \frac{ \partial  }{ \partial \theta } -\frac{\sin \varphi \cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \varphi }  \right]
$$
Ma a noi non interessano questi, ci interessano piuttosto $L_{\pm}$.
$$
	L_{\pm}\equiv L_{x}\pm iL_{y}=\pm \hbar e^{ \pm i\varphi }\left[ \frac{ \partial  }{ \partial \theta } \pm i \frac{\cos \theta}{\sin \theta}\frac{ \partial  }{ \partial \varphi }  \right]
$$
Gli operatori $L_{i}$ (e quindi $L^2$) NON dipendono da $r$, allora sono autoaggiunti sullo spazio vettoriale delle funzioni monodrome a quadrato sommabili sulla SFERA $S^2$, cioè $L^2(S^2)$.
Agiscono cioè su $f(\theta,\varphi)$ tali che:
- $f(\theta,\varphi)=f(\theta,\varphi+2\pi),\; \forall \theta$, cioè è $f$ è periodica
- $f(0,\varphi)=f_{0},\; \forall \varphi$ e $f(\pi,\varphi)=f_{\pi},\; \forall \varphi$. Il valore nei poli è uguale arrivando da qualunque direzione.

Sulla base di queste considerazioni è anche vero che:
$$
	L_{-}=L^{\dagger}_{+}
$$
A questo punto ci manca $L^2$. Calcolandolo (applicando più volte $L_{x,y,z}$ ad una funzione di prova $f(\theta,\varphi)$) otteniamo:
$$
	L^2=-\hbar^2\left[ \frac{ \partial^2  }{ \partial \theta^2 } +\frac{\cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \theta } +\frac{1}{\sin^2\theta} \frac{ \partial^2  }{ \partial \varphi^2 }  \right]
$$
Alternativamente possiamo riscriverlo come:
$$
	L^2=-\hbar^2\left[ \frac{1}{\sin \varphi} \frac{ \partial  }{ \partial \theta } \left( \sin \theta \frac{ \partial  }{ \partial \theta }  \right) +\frac{1}{\sin^2\theta} \frac{ \partial  }{ \partial \varphi^2 } \right]
$$
Riassumendo, gli operatori che si servono sono:
$$
	\begin{cases}
		L^2=-\hbar^2\left[ \frac{ \partial^2  }{ \partial \theta^2 } +\frac{\cos \theta}{\sin \theta} \frac{ \partial  }{ \partial \theta } +\frac{1}{\sin^2\theta} \frac{ \partial^2  }{ \partial \varphi^2 }  \right] \\
		L_{\pm}=\pm \hbar e^{ \pm i\varphi }\left[ \frac{ \partial  }{ \partial \theta } \pm i \frac{\cos \theta}{\sin \theta}\frac{ \partial  }{ \partial \varphi }  \right] \\
		L_{z}=-i\hbar \frac{ \partial  }{ \partial \varphi } 
	\end{cases}
$$

**Lezione Associata:** [[8. Momento angolare in meccanica quantistica]]
