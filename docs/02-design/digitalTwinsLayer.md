---
title: Digital Twins Layer
layout: default
parent: Design
nav_order: 2
has_children: false
---

# Digital Twins Layer

Come anticipato, il layer di *Digital Twins* ha l'obiettivo di avere a disposizione un'astrazione aggiornata del mondo reale attraverso un layer digitale su cui l'*Application layer* può agire.

La progettazione di questo layer è stata suddivisa in due parti. La prima prevede la modellazione dei *Digital Twins* in modo indipendente dalla particolare soluzione architetturale attraverso un meta-modello ispirato alla letteratura <a href="#1">[1]</a><a href="#2">[2]</a>. La seconda invece prevede la progettazione di una soluzione architetturale a supporto del layer.

Il design dei *Digital Twins* e delle relazioni presenti tra essi è illustrato in <a href="#digitalTwins">Figura 1</a>.

<div align="center">
<img id="digitalTwins" src="imgs/digitalTwins.jpg" alt="Digital Twins schema" width="80%">
</div>

Nel design dell'infrastruttura del layer si è scelto di sfruttare lo stack cloud offerto da *Microsoft Azure*.
L'obiettivo è offrire un ambiente in cui sia possibile modellare la realtà attraverso grafi di *Digital Twins* basati su modelli espliciti che permettano la rappresentazione granulare delle caratteristiche, proprietà e relazioni del mondo reale. Inoltre, è necessario essere in grado di poter iniettare i dati del mondo reale in modo tale da avere la rappresentazione virtuale sempre aggiornata tramite il processo di shadowing. Infine, gli aggiornamenti del grafo devono essere osservabili dall'esterno.
Lo stack *Azure* utilizzato e quindi l'architettura progettata è illustrata in <a href="#digitalTwinsArchitecture">Figura 2</a>.



<div align="center">
<img id="digitalTwinsArchitecture" src="imgs/digitalTwinsArchitecture.jpg" alt="Digital Twins Architecture schema" width="80%">
</div>



Essa è composta da quattro servizi principali:

- *Azure Digital Twins*: è un [servizio](https://azure.microsoft.com/it-it/products/digital-twins) *PaaS* che consente la creazione di grafi di *Digital Twins* basati su modelli scritti in *Digital Twins Definition Language* (DTDL). I modelli hanno un'espressività tale da permettere la modellazione di interi ambienti reali esprimendo tutte le proprietà e le relazioni in essere. Il grafo supporta l'aggiornamento di dati in real-time e quindi questo sarà il servizio richiamato dal Gateway di blocco al fine di eseguire lo shadowing. Inoltre, il servizio, come tutta la suite di Azure, è stato progettato con un'impronta event-driven. Questo fa si che tutti gli aggiornamenti del grafo si traducano in eventi che vengono distribuiti fuori dal servizio stesso pronti per essere raccolti ed elaborati.
- *Azure Event Grid*: gli eventi emessi dal servizio *Azure Digital Twins* vengono spediti ad un endpoint. Come endpoint è stato scelto *[Azure Event Grid](https://azure.microsoft.com/en-us/products/event-grid)*, il quale è un servizio di Pub Sub messaging altamente scalabile che permette di costruire pipeline di dati integrando diversi servizi. Gli eventi così vengono raccolti da questo servizio e vengono rispediti lungo la pipeline progettata.
- *Azure Function*: gli eventi raccolti vengono, prima di essere spediti, elaborati attraverso il servizio *[Azure Function](https://azure.microsoft.com/en-us/products/functions)*, il quale è una soluzione serverless *FaaS* che permette di specificare porzioni di codice con la possibilità di scaling automatico. Questo permette di specificare funzioni di mapping dei dati in modo agile all'interno di pipeline come quella descritta qui. Essa è necessaria per aumentare i dati degli eventi ed esprimerli  nel formato opportuno per il loro consumo.

- *Azure SignalR*: gli eventi, una volta pronti, vengono resi disponibili all'Application Layer dell'architettura grazie al servizio *[Azure SignalR](https://azure.microsoft.com/it-it/products/signalr-service)*, il quale permette il push di aggiornamenti in tempo reale in modo completamente scalabile.

Al fine di evitare che ogni microservizio dell'*Application layer* dovesse comunicare con *Azure SignalR* per poter osservare il *Digital Twins layer*, con una conseguente dipendenza tecnologica, si è optato per la creazione di un microservizio aggiuntivo che si occupa del consumo degli eventi da *Azure SignalR*. Il suo compito è quello di rimappare gli eventi nell'infrastruttura interna all'*Application Layer* in modo da eliminare qualsiasi tipo di dipendenza e favorire ulteriormente il loose-coupling. Questo microservizio è stato chiamato *Digital Twins event gateway*.



## Riferimenti

<a id="1">[1]</a> R Minerva, GM Lee, and N Crespi.
     Digital twin in the iot context: a survey on technical features, scenarios and architectural models. Proceedings of the IEEE, 2020.

<a id="2">[2]</a> Alessandro Ricci, Angelo Croatti, Stefano Mariani, Sara Montagna, and Marco Picone. 
     Web of digital twins. ACM Trans. Internet Technol., 22(4), nov 2022.
