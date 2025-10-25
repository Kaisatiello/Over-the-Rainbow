# Over the Rainbow
Il ponte quantistico tra immaginazione e realtà
# Abstract
Attualmente, la comunicazione tra la mente del regista e la concretizzazione dell'opera artistica finale è compromessa dai limiti computazionali dei software impiegati. Il progetto presentato si pone l'obiettivo di essere un ponte tra la realtà concreta e l'immaginifico, utilizzando il "Singularity Machine Learning - Classification".
# Building the quantum bridge
Attualmente, la comunicazione tra la mente del regista e la concretizzazione dell'opera artistica finale è compromessa dai limiti computazionali dei software impiegati. Tali limitazioni influenzano i tempi di rendering e di simulazione, nonché le tecniche applicabili, con conseguente riduzione del realismo o della fattibilità delle idee creative. Le recenti innovazioni tecnologiche rappresentano un mezzo per stimolare la creatività e favorirne la realizzazione, anziché sostituirla. In tale ambito, come emerso anche nell'introduzione delle challenge di oggi, si rende indispensabile un'ottimizzazione dei processi relativi agli effetti digitali. Il progetto presentato si pone l'obiettivo di essere un ponte tra la realtà concreta e l'immaginifico, utilizzando il "Singularity Machine Learning - Classification".

## Tools overview
Nell'ambito della programmazione quantistica,Qiskit (Quantum Information Science Kit) è uno dei framework maggiormente utilizzato [1]. Sviluppato da IBM, ha il vantaggio di essere open-source e, attraverso un'ampia varietà di librerie in Python, permette di creare, simulare ed eseguire algoritmi quantistici sia su simulatori classici, sia su computer quantistici reali, messi a disposizione da IBM tramite cloud.
Per accelerare l'applicazione del quantum computing a problemi concreti, IBM ha introdotto le Qiskit Functions: servizi astratti e specializzati pensati per semplificare l'utilizzo di algoritmi quantistici avanzati, riducendo la necessità di una profonda expertise nella programmazione dei circuiti. La funzione proposta, "Singularity Machine Learning - Classification" è stata integrata come una Qiskit Functions, all'interno del catalogo di servizi della piattaforma IBM Quantum, per la quale è accessibile una guida all'utilizzo [2]. Tale funzione implementa un classificatore ibrido quantistico-classico (o Quantum-Enhanced Ensemble Classifier), un approccio particolarmente vantaggioso e praticabile nell'attuale era NISQ (Noisy Intermediate-Scale Quantum) con l'obiettivo di ottenere un vantaggio quantistico combinando la potenza di calcolo classica con quella quantistica. L'algoritmo addestra classicamente un ensembl di classificatori sui dati etichettati, sfruttando metodi classici come boosting, bagging e stacking. Successivamente, utilizza algoritmi quantistici, come il QAOA (Quantum Approximate Optimization Algorithm) eseguito su una QPU (Unità di Elaborazione Quantistica) IBM, per ottimizzare l'ensemble. Questo processo mira a massimizzare la diversità e la generalizzazione del modello finale. A differenza di molte altre soluzioni di apprendimento automatico quantistico, la funzione è progettata per gestire dataset su larga scala (milioni di esempi e features). Il suo principale vantaggio è che la dimensione del problema non è limitata dal numero di qubit della QPU; il numero di qubit influenza solo la dimensione dell'ensemble che può essere ottimizzato. 
Nell'applicazione per i processi degli effetti digitali, l'obiettivo è usare la classificazione quantistica per categorizzare o etichettare automaticamente asset, elementi di scena o dati per velocizzare il pipeline degli effetti digitali.
## Exemple Tasks

Di seguito viene riportato in modo schematico le fasi del progetto. 

| Fase del progetto | Ruolo del Classificatore Singularity | *Vantaggio Quantistico*
| --- | --- |
| Tabellone di gioco, tabelloni delle navi spaziali, carte Motore, carte Eventi Quantistici, componenti quantistici, pedine delle navi spaziali, pedina del tasso di rilevazione | Stampa dei tre fogli del documento in formato A3 |
| 2 pedine navi spaziali | _Opzionale_  stampa 3D |
| 1 pedina del tasso rilevazione | _Opzionale_ stampa 3D |
| 1 dado Centarious (d6 binario) | Stampa 3D, riutilizzare (ad esempio si può usare una moneta) |
| 1 dado Entanglion (d8) | Stampa 3D, riutilizzare un vecchio dado |
| Regolamento | Stampa formato A4 del regolamento in formato provvosorio PDF |






 [1]**[https://quantumzeitgeist.com/an-in-depth-look-at-the-popularity-of-quantum-computing-languages-and-frameworks/]**
 [2]https://quantum.cloud.ibm.com/docs/en/guides/multiverse-computing-singularity





### Note della traduzione italiana
> Nota 1 : In lingua originale è disponibile una versione chiara del gioco per risparmiare inchiostro.
> Nota 2 : Attualmente il regolamento non è disponibile nel formato originale ma spero di aggiunderlo presto. 

## Step 3. Stampa
| Componente | Colore | Fill | Raft | Supporti | Consigli |
| --- | --- | --- | --- | --- | --- |
| Pedine navi spaziali | Una rossa, una blu | 50% | Si | Si | Puoi provare a stamparne una versione più grande per divertimento! 🚀 |
| Pedina del rate di rilevazione | Qualsiasi colore, sii creativo! 🙃 | 10% | Si | No | Il bianco è un colore preferibile|
| dado Centarious d6 | Viola | 100% | Si | No | Posiziona la parte con il numero "1" a faccia in giù sul letto della stampante |
| dado Entanglion d8 | Giallo | 100% | Si | No | Posiziona la parte con il numero "1" a faccia in giù sul letto della stampante |

> Se non hai a disposizione una stampante 3D, puoi compare questi dadi su Amazon, seguono link della versione in inglese, ([Centarious binary d6](http://a.co/0cW7fsG), [Entanglion d8](http://a.co/aNyVaz9)), o riutilizzare dei dadi appropriati da altri giochi.

### Regolamento
Al momento nella vesione orginale è disponibile solo un file pdf del regolamento, la parte seguente in inglese che non ho tradotto fa riferimento al regolamento orginale. We have included the full-color version of the rule book in the game assets. However, it is possible that we may update the rules based on community feedback. The authoritative source of Entanglion rules will be maintained in the [online rulebook](../game), and any errata or rule clarifcations will be documented on the [errata page](../game/Errata.md).

## Step 4. È il Momento di Giocare! 🚀
Congratulazioni per aver assmbleto la tua copia di Entanglion. Speriamo tu ti diverta giocandoci!

# Domande?
Mandare una domanda in inglese nell'apposita [sezione](../../../issues) se ci sono domande relative ai componenti della versione originale, se ci sono domande sulla versione italiana contattare Eleonora Ballarini tramite [LinkedIn](www.linkedin.com/in/eleonora-ballarini-50b4b6166).
