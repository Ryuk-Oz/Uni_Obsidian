**Prerequisiti:** [[Funzioni Generatrici]], [[Processi di ramificazione]]

Nonostante la forma delle funzioni generatrici possa diventare progressivamente sempre più complessa, il loro utilizzo ci permette di ricavare molto facilmente informazioni sulla probabilità di estinzione di un processo di ramificazione, cioè la probabilità che dopo molte generazioni non ci siano più discendenti.
Il motivo è che questo calcolo si può ricondurre a $G_{n}(0)$ per $n$ grandi e non è dunque necessario ricavare la forma esplicita di $G_{n}(s)$.
Chiamiamo la probabità di estinzione dopo $n$ generazioni $e_{n}=P_{0}^{(n)}=G_{n}(0)$, allora:
$$
	e_{1}=G_{1}(0)=G_{0}, \, e_{2}=G_{2}(0)=G(G(0))=G(e_{1}), \, e_{n}=G_{n}(0)=\dots=G(e_{n-1})
$$
Facciamo alcune osservazioni su $G(s)$ che ci permettono di scoprire di più su $e_{n}$.
Notiamo che $G(1)=1$, $G'(s)\geq 0$, $G''(s) P_{2}\geq 0$ e $G'(1)=E(k)$, dunque $G(s)$ è una funzione concava, monotona, non decrescente.
Studiamo il caso in cui $G'(1)\leq 1$ in maniera grafica. Iterando graficamente la regola $e_{n+1}=G(e_{n})$ osserviamo che $e_{n}$ tende a $1$, dunque l'estinzione è certa.
![[Pasted image 20261004161557.png]]

Considero ora il caso $G'(1)>1$ e procedo analogamente. $G(s)$ interseca necessariamente la bisettrice in un punto $s^*$, il valore di $e_{n}$ tende a questo $s^*$, detto punto fisso e l'estinzione non è più certa.
![[Pasted image 20261004161806.png]]

Abbiamo visto che quando $E(k)<1$ l'estinzione è certa. Nei modelli epidemiologici di tipo SIR (suscettibile, infettato, recovery), $<k> =R$ indica il numero medio di infetti per individuo ed è un parametro essenziale nello studio della probabilità di estinzione della malattia.
**Attenzione!** Avere $R>1$ non significa che la malattia non si possa estinguere, significa solo che l'estinzione non è certa.

**ESEMPIO**: "processo di ramificazione" familiare
Ogni individuo può avere $0$ o $1$ figlio. Cioè:
$$
	P_{0},\,P_{1},\,P_{k}=0 \,\forall k\geq_{2}
$$
$$
	P_{0}+P_{1}=1 \quad G(s)=\sum S^kP_{k}=P_{0}+sP_{1}\to \text{ retta}$$
Abbiamo che $G'(1)=P_{1}$. Se la probabilità di nascita di un figlio è minore del $100\%$, allora l'estinzione è certa. Questo risultato è estremamente intuitivo e potevamo ricavarlo anche senza questo formalismo. Di fatto il processo non era neanche un processo di ramificazione.

Forniamo in fine un esmpio carino preso sempre dallo studio di infezioni virali, per quanto non sia strettamente correlato ai processi di ramificazione.