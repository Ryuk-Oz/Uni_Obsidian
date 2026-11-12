
Esiste un limite al progresso di Hardware e Software? Ci sono problemi che non potranno mai essere risolti da un calcolatore? Sì.

Nella prima parte ci occupiamo di capire cosa non può essere calcolato, sia in principio, da un punto di vista teorico, sia cosa non può essere calcolato da un punto di vista pratico, di performance.

Possiamo distinguere i problemi in alcune macrocategorie:
- problemi trattabili, computabili sia in teoria che in pratica (ad esempio, la via più corta su una mappa)
- problemi non trattabili, computabili in teoria ma non (ancora) in pratica(ad esempio, problema del commesso viaggiatore: "Given a list of cities and the distances between each pair, what is the **shortest possible route** that visits each city **exactly once** and returns to the starting city?")
- problemi non computabili, problemi che non potranno mai essere risolti da alcun computer (ad esempio, trovare tutti i bug di un computer.)

Per studiare questi risultati, usiamo un framework non tra i più formali, ma abbastanza semplice, python, in particolare solo programmi SISO (string in, string out).

**Cos'è un computer program?**

Turing dimostra che una definizione precisa non è strettamente necessario.
Diversi programmi, scritti in diversi linguaggi, su diverse macchine, hanno tutti le stesse capacità. Per questo motivo possiamo efficacemente limitarci all'uso di programmi SISO.
In particolare usiamo stringe ASCII (che include anche il simbolo per lo spazio e la newline).
Per esempi di programmi SISO e non, vedere le slide.

Definiamo $P(I)=S$ l'output del nostro programma $P$ per un input $I$.
$P(I)$ non è definito quando:
- $P$ non termina
- non restituisce una stringa ASCII
- ci restituisce un'exception
L'output può venire definito in modo ben più formale, vedi per curiosità.

Chiamiamo programmi *decisionali* tutti i programmi che restituiscono solo "sì" o "no" come output, sulla base dell'accettazione o meno dell'input.

Due programmi con lo stesso output si dicono equivalenti. Esistono infiniti programmi tra loro equivalenti (l'esempio tipico sono gli algoritmi di ordinamento, sorter). Algoritmi equivalenti possono avere tempi di computazioni molto diversi (ad esempio bubble sort *VS* merge sort).

Nel nostro caso diciamo che $P_{1}$ e $P_{2}$ sono equivalenmti se $P_{1}(I)=P_{2}(I),\; \forall I$.

Perchè ci accontentiamo dei programmi SISO? Sono facilmente generalizzabili a programmi di qualunque tipo.

### Esempi di programmi impossibili

Per mostrare esempi di programmi impossibili utilizzeremo dimostrazioni per contraddizioni.

Ho un'affermazione $S$ che vorrei dimostrare falsa. A questo punto devo cercare un'affemazione $C$ che segue sempre da $S$. Se sono in grado di trovare un'affermazione $T$ che so essere vera e che contraddice $C$, allora so che $S$ dev'essere falsa. (L'esempio classico sono le tavole di verità).

Programmi possono analizzare dati, ma posso analizzare anche altri programmi, oppure se stesso.
Ad esempio, posso applicare un programma che conta il numero di righe in un testo ad un altro programma, ovviamente può anche contare il proprio numero di righe.
Questo viene scoperto nel 1936 da Turing. I programmi più potenti e con capacità di calcolo complessi sono proprio quelli in grado di autoanalizzarsi (**self-reflection**).
La self-reflection è proprio il motivo per cui esistono problemi non computabili.
Possiamo vederlo come un' "estensione" del teorema di incompletezza di Goedel.

Introduciamo 3 programmi decisionali che ci torneranno utili.
![[Pasted image 20261111162221.png]]

Vediamo cosa succede quando si analizzano a vicenda.
![[Pasted image 20261111162328.png]]

(containsGAGA è un programma che restituisce "yes" se la stringa in input contiene la stringa "GAGA).

A questo punto definiamo un nuovo programma "yesOnString", che riceve in input un programma e un input:
![[Pasted image 20261111162506.png]]
Partendo da questo, possiamo costruire un programma yesOnSelf:
![[Pasted image 20261111163741.png]]
Proviamo a dargli in pasto i programmi di prima:
![[Pasted image 20261111163042.png]]

Se yesOnSelf restituisce "yes" su se stesso, allora sarà sempre "yes".
Se restituisce "no", allora sarà sempre "no". Sia "yes" che "no" sono risposte corrette!
Partendo da yesOnSelf, possiamo costruirè anche notyesOnSelf:
![[Pasted image 20261111163355.png]]
Cosa succede dandogli in pasto i programmi di prima? E dandogli in pasto se stesso?
![[Pasted image 20261111163455.png]]
Sia "yes" che "no" portano a contraddizioni, dunque l'esistenza stessa di notyesOnSelf è paradossale, allora non possiamo costruire notyesOnSelf!

Per questo motivo non posso costruire neanche yesOnString!

Si può dimostrare la stessa cosa in modo più breve, in 1 solo step anzichè tre, tramite un programma di questo tipo:
![[Pasted image 20261111164753.png]]
Che come prima genera una contraddizione quando applicato a se stesso.
Ma l'utilizzo di 3 passaggi, è più chiara e sembra meno "mistica", senza lasciarci l'idea che ci sia qualcosa di sbagliato nella dimostrazione.
Ulteriormente la dimostrazione in 3 step fornisce un approccio riciclabile per dimostrare la non esistenza di altri programmi.

Con lo stesso ragionamento si dimostra che è impossibile scrivere un programma che ci dice se un altro programma crasherà o meno. Un programma di questo tipo sarebbe ovviamente molto più utile di yesOnString.
Un programma di questo tipo non è computabile in generale ma è comunque possibile scrivere un programma di questo tipo che funziona per una grande classe di programmi.

### Problemi computazionali

Un problema computazionale descrive cosa vogliamo computare/risolvere, un programma risolve il problema computazionale.
Un programma è solo una delle possibili soluzioni a un problema.
L'istanza di un problema si dice essere "negativa" se se gli unici elementi dell'insieme delle sue soluzioni sono "no".
Si dice "positiva" in caso contrario.

Alcuni tipi importanti di problemi sono:
- search problems
- optimization problems
- treshhold problems
- function problems
- decision problems: tutte le soluzioni sono "yes" o "no".

I problemi decisionali sono particolarmente utili in theoretical computer science, seppur poco utili da un punto di vista applicativo.

Solitamente è molto facile passare da un problema decisionale ad un problema generale senza perderne l' "essence".

![[Pasted image 20261111170408.png]]

Nel caso in cui $F$ sia un problema decisionale, non diciamo più che $P$ calcola o risolve $F$, bensì diciamo che $P$ decide $F$.
Decidibile e indecidibile hanno lo stesso significato di calcolabile e non calcolabile, ma applicato a problemi decisionali.

