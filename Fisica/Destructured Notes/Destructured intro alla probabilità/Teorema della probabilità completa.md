
Il teorema della probabilità completa è una diretta conseguenza della formula di Bayes.

Consideriamo $\{ B_{i} \}^N_{i=1}$, partizione di $\Omega$.
$$
	\forall A \quad P(A)=\sum^N_{i=1}P(A|B_{i})P(B_{i})
$$
la dimostrazione è abbastanza chiara per via grafica, semplicemente vado a sommare la probabilità di $A\cap B_{i}$ fino a ottenere la probabilità di $A\cap \Omega \equiv A$:
![[Pasted image 20260930225935.png|439]]

Di seguito forniamo un esempio di applicazione di tale teorema.

**Test del Covid**

Studiamo la probabilità di essere malati a fronte di test positivo e quella di essere sani a fronte di test negativo, per farlo sfruttiamo la formula di Bayes.

In totale ho 2 stati per il test, positivo $T^+$ e negativo $T^-$ e due stati per il paziente, sano $S$ e malato $M$.
Idealmente vorrei che il test identificasse sempre chi è malato e chi sano, cioè:
$$
	P(T^+|M)=1 \qquad P(T^-|S)=1
$$
in realtà ho una sensibilità $P(T^+|M)=0.95$ e una sensibilità $P(T^-|S)=0.95$.
Abbiamo detto di voler calcolare $P(M|T^+)$ e $P(S|T^-)$. Per farlo possiamo sfruttare il teorema di Bayes, ma ci serve la probabilità che un cittadino sia malato a priori. Ipotizziamola nota e $P(M)=0.05$, dato plausibile per le fasi iniziali del contagio.
$$
	P(S|T^-)=P(T^-|S) \frac{P(S)}{P(T^-)} \quad \text{per il teorema di Bayes}
$$
ma non conosco ancora $P(T^-)$. Posso calcolarla usando il teorema della probabilità completa.
$$
	P(T^-)=P(T^-|S)P(S)+P(T^-|M)P(M)=0.95\cdot{0}.95+0.05\cdot 0.05=0.905
$$
dunque:
$$
	P(S|T^-)=0.95\cdot \frac{0.95}{0.905}\simeq 0.997 \implies \text{il test testa molto bene le persone sane}
$$
Facciamo lo stesso calcolo per $P(M|T^+)$. Avremo $P(T^+)=1-P(T^-)=0.095$.
$$
	P(M|T^+)=0.95\cdot \frac{0.05}{0.095}=0.5\implies \text{il test testa male le persone malate}
$$
Ne concludiamo che più la malattia è rara più sale la probabilità di falso positivo e più alta dev'essere la sensibilità.

**Lezione Associata:** [[2.Probabilità condizionata]]