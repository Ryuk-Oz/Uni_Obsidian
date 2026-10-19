
Come fatto da Young per la luce, possiamo studiare il comportamento ondulatorio degli elettroni tramite l'esperimento della doppia fenditura.
Per comprendere meglio i risultati di questo esperimento studiamo prima il caso di particelle puramente newtoniane e poi quello per onde  classiche.

##### Particelle Newtoniane

Per particelle Newtoniane, come i proiettili di un cannone, abbiamo la seguente situazione

![[Pasted image 20260927234438.png|700]]

Sullo schermo vado a misurare una densità di probabilità
$$
	\begin{aligned}
	P(z)&=\text{densità di probabilità che una particella arrivi in z} \\
	P(z)dz&=\text{probabilità che un proiettile arrivi tra } z \text{ e } dz
	\end{aligned}
$$
Osserviamo i seguenti fatti:
1. l'arrivo dei proiettili è **DISCRETO**, i proiettili arrivano interi e localizzati
2. I proiettili passano da una o dall'altra fenditura e $P_{tot}(z)=P_{1}(z)+P_{2}(z)$, probabilità che il proiettile sia passato in una delle 2 fenditure

#### Onde classiche

Per le onde classiche abbiamo invece quello che abbiamo studiato a OFT e Fisica 3.

![[Pasted image 20260928001454.png]]

Non misuro più una distribuzione di probabilità bensì un'intensità.
L'energia depositata tra $z$ e $dz$ è:
$$
	E(z) \propto I(z) \propto |A(z)|^2
$$
In questo caso possiamo fare le seguenti osservazioni:
1. l'energia depositata è una variabile **CONTINUA**
2. Non è vero che l'onda passa da una sola fenditura o dall'altra, dunque:   $$
   	I_{tot}(z) \neq I_{1}(z)+I_{2}(z)
   $$
bensì: 
$$
	I_{tot}(z)=I_{1}+I_{2}+2\sqrt{ I_{1}I_{2} }\cos(\delta)
$$
#### Esperimento fatto con gli elettroni, particelle quantistiche

Vediamo ora cosa succede nel caso di particelle quantistiche come gli $e^{-}$.
In questo caso abbiamo dei problemi causati dalle dimensioni dell'elettrone nella creazione di fenditure adatte (devono essere nanometriche), pertanto facciamo uso di reticoli cristallini.

![[Pasted image 20260928002846.png]]

Nel caso della particella quantistiche osserviamo qualcosa che sta a metà tra i 2 casi precedenti:
1. L'arrivo degli elettroni è un fenomeno **DISCRETO**, gli elettroni arrivano interi e localizzati, misuriamo dunque delle distribuzioni di probabilità
2. a differenza delle particelle Newtoniane, non è vero che $P_{tot}=P_{1}(z)+P_{2}(z)$, dunque non posso dire se gli elettroni sono passati in una o nell'altra fenditura. Tuttavia il risultato non è caotico, ma è "ordinato" com nel caso di onde classiche. Intuitivamente capiamo che è come se:
$$
	\begin{aligned}
	P(z)&=|\phi(z)^2| \\
	P_{tot}(z)&=|\phi_{1}(z)+\phi_{2}(z)|
	\end{aligned}
$$
con $\phi(z)$ che si comporta come un'onda.
Questo è indubbiamente molto controintuitivo rispetto al modo in cui siamo abituati a pensare, anzi, non siamo proprio in grado di capirlo.

Negli anni ci sono stati diversi tentativi di spiegazioni fallimentari, ad esempio:
1. gli elettroni sono delocalizzati, il che è falso in quanto non siamo mai riusciti a osservare una "frazione" di elettrone
2. il moto degli elettroni è molto più complesso rispetto a quello che pensiamo. Questo andrebbe a implicare la presenza di un campo di forze a noi ignoto che fa assumere all'elettrone esattamente il comportamento di un'onda. Questa argomentazione è così complessa da cadere sotto il rasoio di Ockham.
3. questo è un effetto colletivo del fascio. Questo è falso perchè ora siamo in grado di sparare un'elettrone solo alla volta, ogni quanto vogliamo, e osserviamo sempre lo stesso risultato.

A questo punto viene naturale chiederci cosa succeda all'elettrone durante il passaggio attraverso la fenditura.

![[Pasted image 20260928004118.png|538]]

Vado a mettermi molto vicino alla fenditura con una luce e studio la presenza dell'elettrone studiando come vengono deviati i fotoni per effetto Compton.
Quello che osserviamo è che se riesco a vedere il passaggio dell'$e^{-}$, allora quel singolo elettrone non contribuisce alla figura d'interferenza, cioè, per ogni elettrone che riesco a ossevrare alla fenditura, sullo schermo **vale** $P_{tot}=P_{1}+P_{2}$, come se fosse una particella classica.

Pensandoci meglio, non ci stupisce che il processo di misura vada a influenzare il risultato, infatti per riuscire a localizzare l'elettrone ho bisogno di lunghezze d'onda paragonabili a quelle dell'elettrone, $\lambda$ piccolo. A luci di questo tipo corrispondono però una frequenza e dunque un energia molto elevata, non ci stupisce dunque che vadano a influenzare il moto dell'elettrone in qualche modo.

In poche parole, non esistono esperimenti che mi permettino di vedere dove passa l'elettrone conservando la figura di interferenza.

Nel caso dei proiettili classici, la lunghezza d'onda è così bassa che le oscillazioni di $P_{T}(z)$ sono invisibili e se ne osserva la media su un numero di cicli elevatissimo.

Sarebbe possibile evitare il problema dell'influenza della misura in qualche modo?
Proviamo a fare due ipotesi ragionevoli e vediamo il motivo per cui non funzionano.
- fissiamo $\lambda$ ma diminuiamo l'intensità della luce. Questo non va bene in quanto si tratta di un ragionamento puramente classico, l'intensità misura il numero di fotoni, non l'energia che ciascuno trasporta.
- Diminuiamo la frequenza $\nu$ della luce. In questo caso il ragionamento non è più classico e funzionerebbe anche, se non fosse che così facendo vado a diminuire l'accuratezza della misura e il risultato smette di essere affidabile.
