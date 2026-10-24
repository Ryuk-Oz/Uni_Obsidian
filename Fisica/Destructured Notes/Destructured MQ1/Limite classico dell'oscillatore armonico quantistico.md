
Lo studio del limite classico dell'oscillatore armonico quantistico è molto più complesso rispetto a quello della buca infinita poichè non possiamo più fare affidamento sul solo intuito.
Occupiamoci per prima cosa del calcolo della densità di probabilità nel regime classico cioè nel limite $n \to \infty$.
Per ogni sistema in moto periodico vale:
$$
	dP_{\text{class}}=\rho_{\text{cl}}(x)dx =\frac{dt(x)}{T/2}
$$
ricaviamo $dt(x)$ dall'equazione del moto:
- **Caso della buca infinita**:
  $x=vt = \frac{p}{m}t\implies t(x)=\frac{x}{v}$. La lunghezza della buca è $L=a\implies \frac{T}{2}=\frac{a}{v}$.
  Mettiamo tutto insieme per ottenere: $\frac{dt(x)}{T/2}=\frac{dx}{v} \frac{v}{a}=\frac{dx}{a}$.
  Dunque la densità di probabilità classica è $\rho_{\text{cl}}(x)=\frac{1}{a}$ costante e normalizzata, la stessa che abbiamo ottenuto facendo ragionamenti di natura intuitiva.
- **Caso dell'oscillatore armonico**:
  $x(t)=A\cos(\omega t+\varphi)\implies t(x)=\frac{1}{\omega}\left[ \text{arcos}\left( \frac{x}{A} \right)-\varphi \right]$. 
$$
	dt=\frac{1}{\omega} \frac{1}{\sqrt{ A^2-x^2 }}dx
  $$
$$
	\int^{T/2}_{0} dt= \frac{T}{2} = \frac{1}{\omega}\int^A_{-A} \frac{dx}{\sqrt{ A^2 -x^2}}=\frac{\pi}{\omega}
  $$
  E otteniamo:
$$
	\rho_{\text{cl}}(x)=\frac{1}{\pi} \frac{1}{\sqrt{ A^2 -x^2}}
  $$
Studiamo come questa differisce dal caso quantistico. partiamo dallo studio delle ampiezze:
$$
	E_{\text{cl}}=\frac{1}{2}m\omega^2A^2_{\text{cl}}
$$
Estendiamo questa relazione al caso quantistico per studiare come variano le ampiezze:
$$
	A_{n}=\sqrt{ \frac{2E_{n}}{m\omega^2} }=\sqrt{ \frac{(2n+1)\hbar}{m\omega} }\underset{n\to \infty}{\simeq} \frac{\sqrt{ 2n }}{\alpha}
$$

A questo punto facciamo uso del seguente teorema:
    Gli zeri dei polinomi di Hermite sono tutti reali , e , per grandi $n$ sono tutti confinati nell'intervallo: $-\sqrt{ 2n }\lesssim \xi \lesssim \sqrt{ 2n }$
$\implies$ per $n$ grandi $\rho_{n}(x)$ oscilla nella regione classicamente permessa e decade esponenzialmente al di fuori di essa.

![[Pasted image 20261024121401.png]]

**Lezione associata:** [[4.Oscillatore armonico quantistico]]