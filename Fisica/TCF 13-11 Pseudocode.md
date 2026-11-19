
### Dimostrazione limite centrale

Implementa importazione di una funzione esterna (la mia PDF)
generate Trandom;

For 1000 volte
    prendi distribuzione di probabilità in input e genera eventi
    fill dell'istogramma
    calcola valore medio
    salva valore medio in un TVector

Filla un nuovo istogramma dal TVector
Fit istogramma con Gaussiana
Plot di questo grafico
Salva il grafico
Paragone tra media aritmetica medie  e valore medio della gaussiana
Propagazione errore per testare quanto la gaussiana diverga dalla distribuzione ottenuta


### Integrazione hit and miss

Definisci funzione (ricicla da limite centrale)

Prendi upper limit all'interno dell'intervallo scelto
Definisci la box
Genera eventi e dividili in 2 con if
calcola integrale
