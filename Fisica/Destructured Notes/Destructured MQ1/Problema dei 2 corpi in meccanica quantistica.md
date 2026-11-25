
Consideriamo 2 particelle di masse $m_{1}$ e $m_{2}$ interagenti con un potenziale $V(\vec{r}_{1}-\vec{r}_{2})$, $\vec{r}_{1}-\vec{r}_{2}$ rappresenta l'invarianza per traslazione.
Classicamente abbiamo un'Hamiltoniana:
$$
	H=\frac{|\vec{p}_{1}|^2}{2m_{1}}+\frac{|\vec{p}_{2}|^2}{2m_{2}}+V(\vec{r}_{1}-\vec{r}_{2})
$$
Quantisticamente $H\to \hat{H}$, cerco $\psi(\vec{r}_{1},\vec{r}_{2})$.
Scelgo come nuove coordinate:
$$
	\begin{cases}
	\vec{r}\equiv \vec{r}_{1}-\vec{r}_{2} & \text{posizione relativa} \\
	\vec{R}= \frac{m_{1}\vec{r}_{1}+m_{2}\vec{r}_{2}}{m_{1}+m_{2}} & \text{posizione del centro di massa}
	\end{cases}
$$
riscrivo temporaneamente $\hat{H}$ con le vecchie coordinate.
$$
	\left[ -\frac{\hbar^2}{2m_{1}} \Delta_{1}-\frac{\hbar^2}{2m_{2}} \Delta_{2}+V(\vec{r}_{1}-\vec{r}_{2}) \right]\psi(\vec{r}_{1},\vec{r}_{2})=E_{tot}\psi(\vec{r}_{1},\vec{r}_{2})
$$
Cambiamo coordinate.
$$
	\frac{ \partial  }{ \partial x_{1} }=\frac{ \partial x }{ \partial x_{1} } \frac{ \partial  }{ \partial x } +\frac{ \partial X }{ \partial x_{1} } \frac{ \partial  }{ \partial X } =\frac{ \partial  }{ \partial x } +\frac{m_{1}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial X } 
$$
e:
$$
	\frac{ \partial  }{ \partial x_{2} } =-\frac{ \partial  }{ \partial x } + \frac{m_{2}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial X } 
$$
...MA... nel laplaciano sono presenti le derivate seconde:
$$
\begin{aligned}
	\frac{ \partial ^2 }{ \partial x_{1}^2 } &=\left( \frac{ \partial  }{ \partial x } +\frac{m_{1}}{m_{1}+m_{2}} \frac{ \partial  }{ \partial X }  \right)^2\\
	&=\frac{ \partial^2  }{ \partial x^2 } +\frac{2m_{1}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial x } \frac{ \partial  }{ \partial X } +\left( \frac{m_{1}}{m_{1}+m_{2}} \right)^2 \frac{ \partial^2  }{ \partial X^2 } 
\end{aligned}
$$
e:
$$
	\frac{ \partial^2  }{ \partial x_{2}^2 }= \frac{ \partial^2  }{ \partial x^2 } -\frac{2m_{2}}{m_{1}+m_{2}}\frac{ \partial  }{ \partial x } \frac{ \partial  }{ \partial X } +\left( \frac{m_{2}}{m_{1}+m_{2}} \right)^2 \frac{ \partial^2  }{ \partial X^2 } 
$$
dunque:
$$
	\begin{aligned}
	&-\frac{\hbar^2}{2m_{1}}\Delta_{1}-\frac{\hbar^2}{2m_{2}}\Delta_{2} =\\
	=& -\frac{\hbar^2}{2m_{1}}\left( \Delta_{r}+\frac{m_{1}^2}{(m_{1}+m_{2})^2}\Delta _{R}+ \cancel{\frac{2m_{1}}{m_{1}+m_{2}} \vec{\nabla }_{r} \cdot \vec{\nabla}_{R}} \right)-\\
	&-\frac{\hbar^2}{2m_{2}}\left( \Delta_{r}+\frac{m_{2}^2}{(m_{1}+m_{2})^2}\Delta _{R}+ \cancel{\frac{2m_{2}}{m_{1}+m_{2}} \vec{\nabla }_{r} \cdot \vec{\nabla}_{R}} \right)\\
	=&-\frac{\hbar^2}{2} \left( \frac{1}{m_{1}}+\frac{1}{m_{2}} \right)\Delta_{r}-\frac{\hbar^2}{2(m_{2}+m_{1})}\Delta_{R}=-\frac{\hbar^2}{2\mu}\Delta_{r}-\frac{\hbar^2}{2M}\Delta_{R}
	\end{aligned}
$$
con $\mu= \frac{m_{1}m_{2}}{m_{1}+m_{2}}$, massa ridotta e $M=m_{1}+m_{2}$ massa totale.
Abbiamo riscitto l'edS in una forma semplice che è direttamente separabile.
$$
	\left[ -\frac{\hbar^2}{2\mu}\Delta_{r}-\frac{\hbar^2}{2M}\Delta_{R}+V(\vec{r}) \right]\psi(\vec{r},\vec{R})=E_{tot}\psi(\vec{r},\vec{R})
$$
Supponiamo che $\psi(\vec{r},\vec{R})$ sia fattorizzabile:
$$
	\psi(\vec{r},\vec{R})=\psi_{1}(\vec{r})\psi_{2}(\vec{R})
$$
a questo punto possiamo ottenere le 2 equazioni:
$$
	\begin{aligned}
	&\left( -\frac{\hbar^2}{2\mu}\Delta_{r}+V(\vec{r}) \right)\psi_{1}(\vec{r})=E_{1}\psi_{1}(\vec{r})\\
	&\left( -\frac{\hbar^2}{2M} \Delta_{R} \right)\psi_{2}(\vec{R})=E_{2}\psi_{2}(\vec{R})
	\end{aligned}
$$
con $E_{tot}=E_{1}+E_{2}$.
$\psi_{1}$ descrive la dinamica più interessante, quella del moto relativo tra i 2 corpi, mentre $\psi_{2}$ descrive il moto libero del baricentro del sistema.

**Lezione Associata:** [[9. Atomo di Idrogeno]]