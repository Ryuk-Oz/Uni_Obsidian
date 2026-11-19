
**Essenziale:** [[Autovalori dell'energia tramite gli operatori gradino]]

Partiamo dalla seguente osservazione:
$$
	\begin{aligned}
	\bra{k} \mathcal{H}a^{\dagger}\ket{l}& =\varepsilon_{k} \bra{k} a^{\dagger}\ket{l}\\
	  &=\bra{k} \mathcal{H}a^{\dagger}+a^{\dagger}\ket{l} =(\varepsilon_{l}+1) \bra{k} a^{\dagger}\ket{l} 
	\end{aligned}
$$
Dunque:
$$
	(\varepsilon_{k}-(\varepsilon_{l}+1))\bra{k} a^{\dagger}\ket{l} =0
$$
Dunque $\bra{k}a^{\dagger}\ket{l}=0$ tranne se $\varepsilon_{k}=\varepsilon_{l+1}\implies k=l+1$.
Analogamente per $a$ si trova che $\bra{k}a\ket{l}=0$ a meno che $k=l-1$. Cioè:
$$
		\bra{k} a \ket{l}  = \lambda_{l} \delta_{k,l-1}
$$
Con $\lambda_{l}$ autovalore di $a$ per lo stato $\ket{l}$.
Per definizione di autoaggiunta vale:
$$
	\bra{l+1} a^{\dagger} \ket{l} = \bra{l} a \ket{l+1} ^*
$$
Dunque:
$$
	 \bra{l} a^{\dagger} \ket{k} =\bra{k} a \ket{l} ^* = \lambda_{l}^* \delta_{k,l-1}
$$
Applichiamo questo a quanto discusso fin'ora:
$$
	\varepsilon_{n}=\left( n+\frac{1}{2} \right)= \bra{n} \mathcal{H} \ket{n}  = \bra{n} a^{\dagger}a \ket{n} +\frac{1}{2}
$$
E:
$$
	\bra{n} a^{\dagger}a \ket{n} = n = \sum_{k} \bra{n} a^{\dagger} \ket{k}  \bra{k} a \ket{n} = \bra{n} a^{\dagger} \ket{n-1} \bra{n-1} a \ket{n}  = |\lambda_{n}|^2 \implies \lambda_{n} = \sqrt{ n }
$$
Da queste osservazioni arriviamo agilmente a:
$$
	\begin{cases}
	a\ket{n} =\sqrt{ n }\ket{n-1} \\
	a^{\dagger}\ket{n}=\sqrt{ n+1 }\ket{n+1}   
	\end{cases}
$$
**OSS**: gli autostati dell'Hamiltoniana NON sono autostati per gli operatori gradino.
Adesso siamo in grado di srivere la matrice che rappresenta l'operatore $a$.
$$
	a=\begin{pmatrix}
	0 & \sqrt{ 1 }  & 0 & \cdot & \cdot & \cdot \\
	0 & 0 & \sqrt{ 2 } & \cdot & \cdot & \cdot \\
	0 & 0 & 0 & \sqrt{ 3 }  &  \cdot & \cdot \\
	\cdot & \cdot & \cdot & \cdot & \cdot & \cdot \\
	\cdot \\

	\end{pmatrix}
$$
$$
	a^{\dagger}=\begin{pmatrix}
	0 & 0 & 0 & 0 & \cdot & \cdot \\
	\sqrt{ 1 } & 0 & 0 & 0  & \cdot  & \cdot\\
	0 & \sqrt{ 2 } & 0 & 0  & \cdot & \cdot\\
	0 & 0 & \sqrt{ 3 } & \cdot & \cdot & \cdot
	\end{pmatrix}
$$
Ora posso trovare la matrice che rappresenta $\mathcal{H}$ (è la matrice diagonale con elementi $\varepsilon_{n}$) e quelle che rappresentano $p$ e $x$:
$$
	\begin{cases}
	p=\sqrt{ \frac{m\hbar \omega}{2} } (a+a^{\dagger}) \\
	x= -i\sqrt{ \frac{\hbar}{2m\omega} }(a^{\dagger}-a)
	\end{cases}
$$
Entrambe hanno diagonale nulla (somma di due matrici con diagonale nulla), dunque:
$$
	\bra{n} p\ket{n} =\bra{n} x \ket{n} =0
$$
Che sono i valori medi di posizione e impulso che avevamo già trovato.
Posso fare la stessa cosa anche coi valori medi di $p^2$ e $x^2$.
$$
	p^2 = \frac{m\hbar \omega}{2} (a^2+(a^{\dagger})^2+2a^{\dagger}a+1)=\frac{m\hbar \omega}{2} (2n+1)=m\hbar \omega \left( n+\frac{1}{2} \right)
$$


**Lezione associata:** [[7. Oscillatore armonico quantistico (con la teoria degli operatori)]]