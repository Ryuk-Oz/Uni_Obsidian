
**Prerequisiti:** I seguenti modi per rappresentare la funzione Gamma: 
- [[Continuazione analitica "spezzando" l'integrale della Gamma]]
- [[Continuazione di Gamma usando la Beta]]
- [[Formula di duplicazione della Gamma]]

Definiamo la funzione Digamma nel seguente modo:
$$
	\psi(z)=\frac{d\ln \Gamma(z)}{dz}=\frac{\Gamma'(z)}{\Gamma(z)}
$$
La funzione Digamma ha una serie di proprietà interessanti che seguono direttamente da quelle della funzione Gamma.

1. La funzione $\Gamma(z)$ non ha zeri, dunque $\psi$ è singolare solo dove è singolare $\Gamma'(z)$, cioè dove è singolare $\Gamma(z)$.
   Consideriamo allora $z_{n}=-n\, n\in \mathbb{N}$
$$
	\Gamma(z)\underset{z\to z_{n}}{\sim} \frac{(-1)^n}{n!} \frac{1}{z+n}+\Omega(z)\qquad \Omega(z) \text{ regolare in } z_{n}
   $$
   Dunque:
$$
\begin{aligned}
\psi(z)&\underset{z\to z_{n}}{\sim}\left( \frac{(-1)^{n+1}}{n!} \frac{1}{(z+n)^2}+\Omega'(z) \right)\left( \frac{(-1)^n}{n!} \frac{1}{z+n}+\Omega(z) \right)^{-1} \\
&=\left( -\frac{1}{z+n}+(-1)^n n! (z+n) \Omega'(z) \right)\left(1+(-1)^nn!(z+n)\Omega(z)\right)^{-1}\\
&\underset{z\to z_{n}}{\sim}\left( -\frac{1}{z+n} + (-1)^n n!(z+n)\Omega'(z) \right)(1-(-1)^nn!(z+n)\Omega(z)+O(z+n))\\
&=-\frac{1}{z+n}+\hat{\Omega}(z) \qquad \hat{\Omega} \text{ regolare in } z=-n
\end{aligned}
   $$
   da qui si vede che $z=-n$ sono poli semplici per la $\psi(z)$
2. Un'altra proprietà emerge da $\Gamma(z)=z\Gamma(z)$.
   $$
	\psi(z+1)=\frac{\Gamma'(z+1)}{\Gamma(z+1)}=\frac{d}{dz}(z\Gamma(z)) \frac{1}{z\Gamma(z)}=\frac{1}{z}+\frac{\Gamma'(z)}{\Gamma(Z)}=\frac{1}{z}+\psi(z)
   $$
3. Un'ulteriore proprietà emerge da $\Gamma(z)\Gamma(1-z)=\frac{\pi}{\sin \pi z}$. Derivandola otteniamo:
$$
	\begin{aligned}
	\Gamma'(z)\Gamma(1-z)-\Gamma(z)\Gamma'(1-z)&=\pi^2(-1) \frac{\cos \pi z}{\sin^2\pi z}\\
	\to \frac{\Gamma'(z)}{\Gamma(z)}-\frac{\Gamma'(1-z)}{\Gamma(1-z)}&=-\pi^2 \frac{\cos \pi z}{\sin^2\pi z} \frac{\sin \pi z}{\pi}=-\frac{\pi (\cos \pi z)}{\sin \pi z}
	\end{aligned}
   $$
   Dunque otteniamo che per la funzione Bigamma vale:
   $$
	\psi(z)-\psi(1-z)=-\pi \text{cotan}(\pi z)
   $$
4. Infine derivando $2^{2z-1}\Gamma(z)\Gamma\left( z+\frac{1}{2} \right)=\sqrt{ \pi }\Gamma(2z)$ troviamo:
$$
	2\log(2) \, 2^{2z-1} \Gamma(z)\Gamma\left( z+\frac{1}{2} \right)+2^{2z-1}\Gamma'(z)\Gamma\left( z+\frac{1}{2} \right)+2^{2z-1}\Gamma(z)\Gamma'\left( z+\frac{1}{2} \right)=\sqrt{ \pi }\,2\Gamma'(2z)
   $$
   Dividendo tutto per $2^{2z-1}\Gamma(z)\Gamma\left( z+\frac{1}{2} \right)=\sqrt{ \pi }\Gamma(2z)$ otteniamo:
$$
	2\log 2 + \psi(z)+\psi\left( z+\frac{1}{2} \right)=2\psi(2z)
   $$


**Lezione associata:** [[5. Funzione Digamma]]