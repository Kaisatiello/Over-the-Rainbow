# Over the Rainbow
Il ponte quantistico tra immaginazione e realtà
# Abstract
Attualmente, la comunicazione tra la mente del regista e la concretizzazione dell'opera artistica finale è compromessa dai limiti computazionali dei software impiegati. Il progetto presentato si pone l'obiettivo di essere un ponte tra la realtà concreta e l'immaginifico, utilizzando il "Singularity Machine Learning - Classification".
# Building the quantum bridge
Attualmente, la comunicazione tra la mente del regista e la concretizzazione dell'opera artistica finale è compromessa dai limiti computazionali dei software impiegati. Tali limitazioni influenzano i tempi di rendering e di simulazione, nonché le tecniche applicabili, con conseguente riduzione del realismo o della fattibilità delle idee creative. Le recenti innovazioni tecnologiche rappresentano un mezzo per stimolare la creatività e favorirne la realizzazione, anziché sostituirla. In tale ambito, come emerso anche nell'introduzione delle challenge di oggi, si rende indispensabile un'ottimizzazione dei processi relativi agli effetti digitali. Il progetto presentato si pone l'obiettivo di essere un ponte tra la realtà concreta e l'immaginifico, utilizzando il "Singularity Machine Learning - Classification".

## Tools overview
Nell'ambito della programmazione quantistica, Qiskit (Quantum Information Science Kit) è uno dei framework maggiormente utilizzato [1]. Sviluppato da IBM, ha il vantaggio di essere open-source e, attraverso un'ampia varietà di librerie in Python, permette di creare, simulare ed eseguire algoritmi quantistici sia su simulatori classici, sia su computer quantistici reali, messi a disposizione da IBM tramite cloud.
Per accelerare l'applicazione del quantum computing a problemi concreti, IBM ha introdotto le Qiskit Functions: servizi astratti e specializzati pensati per semplificare l'utilizzo di algoritmi quantistici avanzati, riducendo la necessità di una profonda expertise nella programmazione dei circuiti. La funzione proposta, "Singularity Machine Learning - Classification" è stata integrata come una Qiskit Functions, all'interno del catalogo di servizi della piattaforma IBM Quantum, per la quale è accessibile una guida all'utilizzo [2]. 
Tale funzione permette di affrontare problemi di classificazione binaria in modi che, teoricamente, i classificatori classici faticano a gestire con la stessa rapidità o accuratezza, soprattutto su set di dati ad alta dimensionalità tipici della computer grafica.
"Singularity Machine Learning - Classification" implementa un classificatore ibrido quantistico-classico (o Quantum-Enhanced Ensemble Classifier), un approccio particolarmente vantaggioso e praticabile nell'attuale era NISQ (Noisy Intermediate-Scale Quantum) con l'obiettivo di ottenere un vantaggio quantistico combinando la potenza di calcolo classica con quella quantistica. L'algoritmo addestra classicamente un ensembl di classificatori sui dati etichettati, sfruttando metodi classici come boosting, bagging e stacking. Successivamente, utilizza algoritmi quantistici, come il QAOA (Quantum Approximate Optimization Algorithm) eseguito su una QPU (Unità di Elaborazione Quantistica) IBM, per ottimizzare l'ensemble. Questo processo mira a massimizzare la diversità e la generalizzazione del modello finale. A differenza di molte altre soluzioni di apprendimento automatico quantistico, la funzione è progettata per gestire dataset su larga scala (milioni di esempi e features). Il suo principale vantaggio è che la dimensione del problema non è limitata dal numero di qubit della QPU; il numero di qubit influenza solo la dimensione dell'ensemble che può essere ottimizzato. 
Nell'applicazione per i processi degli effetti digitali, l'obiettivo è usare la classificazione quantistica per categorizzare o etichettare automaticamente asset, elementi di scena o dati per velocizzare il pipeline degli effetti digitali. 

## Exemple Tasks
Immaginiamo dunque un'applicazione partica dell'algoritmo. I problemi di classificazione binaria si collocano perfettamente all'interno dell'ottimizzazione dei processi per gli effetti visivi (VFX) cinematografici, in quanto gran parte delle decisioni cruciali in un pipeline di produzione complessa possono essere ricondotte a scelte sì/no o A/B. Nei VFX, un problema di classificazione binaria consiste nel prendere un input complesso (un frame, un asset, un set di dati di simulazione) e assegnarlo a una di due categorie definite. Questo è vitale per automatizzare il controllo qualità (QC) e l'allocazione delle risorse. Proponiamo tre problemi possibili, di cui poi ne verrà analizzato nel dettaglio uno. 

1. Controllo Qualità e Rilevamento di Anomalie (QC)
Un aspetto critico della produzione di effetti visivi è il controllo qualità (QC) dei frame renderizzati. Dato che gli errori, come glitch, flickering o noise indesiderato, sono spesso molto sottili e si manifestano su migliaia di frame, il rilevamento manuale è inefficiente. La classificazione binaria automatizza questo processo: il sistema analizza vettori di caratteristiche complesse estratti dai frame (ad esempio, misurando le variazioni di contrasto o il rumore spettrale) e decide se il fotogramma è "Accettabile" (Classe 0) o se presenta un'"Anomalia che richiede un rifacimento" (Classe 1).

2. Etichettatura Intelligente e Gestione degli Asset
L'organizzazione delle vaste librerie di asset 3D, texture e suoni può essere notevolmente velocizzata. Invece di taggare manualmente ogni elemento, la classificazione binaria può determinarne automaticamente la natura. Ad esempio, può classificare un modello come "Corpo Cinetico" (un oggetto che richiede una simulazione dinamica) rispetto a uno "Sfondo Statico", oppure differenziare rapidamente tra una "Texture basata su PBR" (pronta per i moderni renderer) e una "Texture Legacy" più datata.

3. Assegnazione Prioritaria delle Risorse di Rendering
Per ridurre i tempi e i costi di calcolo, è fondamentale allocare la potenza di rendering solo dove necessario. La classificazione binaria aiuta a prendere decisioni intelligenti a livello di pixel o regione: il sistema decide se una specifica area del frame è un'"Area Critica" (ad esempio, per dettagli che richiedono un ray tracing molto profondo o un denoising più aggressivo) o se è un'"Area a Bassa Priorità" che può essere calcolata più velocemente o con stime più semplici. Questo garantisce che le risorse vengano spese per massimizzare la qualità percepita.

## Problema specifico: Classificazione del Noise e degli Artefatti di Rendering
Individuiamo un passaggio cruciale nel VFX: il denoising e il controllo qualità (QC) post-produzione. Dopo il rendering a bassa risoluzione (pass) con meno samples per velocizzare la produzione, vengono applicati algoritmi di denoising. A volte, il denoiser introduce artefatti o non riesce a pulire il noise residuo in modo efficace.
Il problema sta quindi nel rilevare Frame-Level Artifact. 
Obiettivo di Classificazione: Determinare se un frame finale (o la sua differenza con la versione non denoised) è "Pulito e Accettabile" (Classe 0) o "Contaminato da Artefatti o Noise Residuo" (Classe 1).



Immaginando un'applicazione pratica, prendiamo una task di classificazione nei VFX, come la classificazione automatica del tipo di superficie per 10 categorie di texture.
Si crea dunque un dataset etichettato di feature vector che rappresentano i dati da classificare.
**Implementazione con Qiskit Function: Spiega come utilizzeresti l'azione create_fit_predict della funzione "Singularity Machine Learning - Classification" su Qiskit per addestrare il classificatore ibrido e fare previsioni sui dati degli effetti digitali.

Analisi del Risultato: Confronta teoricamente (o con un piccolo test se la licenza/API è disponibile per la challenge) i risultati ottenuti in termini di precisione/velocità rispetto a un classificatore classico standard (come un Random Forest o una SVM).** 

Di seguito vengono riportate in modo schematico le fasi del progetto. 

| **Fase del progetto** | **Ruolo del Classificatore Singularity** | **Vantaggio Quantistico**|
| --- | --- | --- |
| Rilevamento di Anomalie/Errori	 | Classificare i frame renderizzati per rilevare anomalie o glitch impercettibili ai metodi classici più semplici, ma che richiedono il re-rendering. | 	Maggiore sensibilità nella classificazione di feature sottili, garantendo la qualità del prodotto finale. |
| Asset Tagging Automatico|Classificare texture, modelli 3D o digital doubles (es. identificare "tipo di superficie: metallo opaco, tessuto a maglia, pelle") per la gestione della libreria di asset. | 	Velocità e/o precisione nell'elaborazione di feature vettoriali complesse derivate da asset ad alta risoluzione.  |
| Segmentazione del Rendering | Classificare i pixel o le regioni di un frame (su dati di rendering parziali) per identificare le aree critiche che richiedono più sampling o trattamenti specifici (es. aree di motion blur complesso, riflessi) |Potenziale per un'allocazione delle risorse di calcolo più efficiente durante il rendering, riducendo i tempi totali.|






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
