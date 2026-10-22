
Introduciamo una nuova funzione speciale, la funzione $B$ di Eulero.
La funzione $B$ di eulero è una funzione a due parametri $z,u$ così definita:
$$
	B(z,u)=\int^1_{0} dt\, t^{z-1} (1-z)^{u-1}
$$
Analitica per $\mathrm{Re}(z),\mathrm{Re}(u)>0$
La funzione $B$ è simmetrica nelle due variabili. Per vederlo è sufficiente fare un semplice cambio di variabili: $t'=1-t$.
$$
	B(z,u)=-\int^0_{1} dt' \, t'^{\,u-1} (1-t')^{z-1} =B(u,z)
$$
Un'altra rappresentazione utile della $B$ si può ottenre con il seguente cambio di variabili:
$$
	t=\sin^2\theta \quad_{1}-t=\cos^2(\theta) \quad dt=2\sin \theta \cos \theta d\theta
$$
allora:
$$
	B(z,u)=2\int_{0}^{\pi/2} d\theta\, (\sin \theta)^{2z-1} (\cos \theta)^{2u-1}
$$


**Lezione associata:** [[4.Funzione Gamma di Eulero]]