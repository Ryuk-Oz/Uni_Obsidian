
Studiamo la probabilità di un evento sapendo che ne è avvenuto un altro, cioè la probabilità di un evento condizionata dall'avvenire di un altro evento.
$$
	P(A|B)\equiv \frac{P(A\cap B)}{P(B)}
$$
$=$ probabilità che avvenga $A$ sapendo che è avvenuto $B$.

Se gli eventi sono indipendenti abbiamo che $P(A\cap B)=P(A)P(B)$ dunque:
$$
	P(A|B)=\frac{P(A)P(B)}{P(B)}=P(A)
$$
Cioè se A e B sono indipendenti allora la probabilità che esca A non cambia sapendo che è uscito B.

### Formula di Bayes
$$
	P(B|A)=P(A|B) \frac{P(B)}{P(A)} \,\left( = \frac{P(A\cap B)}{P(B)} \frac{P(B)}{P(A)} \equiv P(B|A) \right)
$$
La dimostrazione (banale) è quella illustrata tra le parentesi.

**Lezione Associata:** [[2.Probabilità condizionata]]