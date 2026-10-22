
**Prerequisiti:** [[Definizione della Beta di Eulero]] [[Continuazione di Gamma usando la Beta]]

Sfruttando la definizione di $\Gamma$ tramite $B$ possiamo trovare una formula per $\Gamma(2z)$.
$$
	B(z,z)=\frac{\Gamma(z)\Gamma(z)}{\Gamma(2z)}=\int^1_{0} dt\, t^{z-1} (1-t)^{z-1}
$$
Cambio variabile: $t=\frac{1+x}{2}$ e $1-t=\frac{1-x}{2}$:
$$
	B(z,z)=\frac{1}{2}\int^1_{-1} dx\, \underbrace{(1-x^2)^{z-1} \,2^{-2z+2}}_{\text{funzione pari}}=2^{-2z+2}\int^1_{0} dx\, (1-x^2)^{z-1}
$$
Torniamo alla definizione base della funzione $B$ e usiamo il seguente cambio di variabile:
$$
	t=x^2 \quad dt=2xdx
$$
$$
	B(u,z)=\int^1_{0} dt\, t^{k-1} (1-t)^{z-1} =\int^1_{0} 2xdx\, x^{2u-2} (1-x^2)^{z-1}=2\int^1_{0} dx\, x^{2u-1} (1-x^2)^{z-1}
$$
Calcoliamola per $u=\frac{1}{2}$:
$$
	B\left( \frac{1}{2},z \right)=2\int^1_{0} dx \, (1-x^2)^{z-1}
$$
A questo punto posso sostituire tutto nella definizione con la $\Gamma$.
$$
	\frac{\Gamma(z)\Gamma(z)}{\Gamma(2z)}=2^{-2z+1}B\left( \frac{1}{2},z \right)=2^{-2z+1}\, \frac{\Gamma\left( \frac{1}{2} \right)\Gamma(z)}{\Gamma\left( z+\frac{1}{2} \right)}=2^{-2z+1} \frac{\sqrt{ \pi }\Gamma(z)}{\Gamma\left( z+\frac{1}{2} \right)}
$$
Dunque:
$$
	\Gamma(2z)=2^{2z-1} \frac{\Gamma(z)\Gamma\left( z+\frac{1}{2} \right)}{\sqrt{ \pi }}
$$

**Lezione associata:** [[4.Funzione Gamma di Eulero]]