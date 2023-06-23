---
title: Versioning
layout: default
parent: DevOps
nav_order: 7
has_children: false
---

# Versioning

Una buona pratica per poter essere in grado di distinguere tra i diversi stati di un software prodotto e per potersi riferire ad esso in modo chiaro è il *Software Versioning*. Esso è il processo che prevede l'assegnazione di un identificatore unico ad uno stato del software.

Per quanto riguarda il processo di versionamento è stato scelto di seguire la specifica [*Semantic Versioning*](https://semver.org/lang/it/). Secondo il Semantic Versioning una versione è composta da tre numeri: **Major**, **Minor** e **Patch**. Ogni modifica al codice sorgente determina l'aumento di uno di questi numeri in base all'importanza delle modifiche apportate.

Grazie all'utilizzo della specifica *Conventional Commit* descritta precedentemente è stato possibile utilizzare la semantica di quest'ultimi per comprendere quando effettuare una nuova release e l'importanza di essa. 
Abbiamo utilizzato il bot [*Semantic-release-bot*](https://github.com/semantic-release/semantic-release), che segue la specifica *Semantic Versioning*, per automatizzare il processo di rilascio del software e la generazione del changelog tramite l'analisi dei commit al fine di individuare il corretto incremento di versione.
Per il tipo di release da associare ad ogni commit è stata usata la configurazione [`semantic-release-preconfigured-conventional-commits`](https://github.com/DanySK/semantic-release-preconfigured-conventional-commits). Il bot viene attivato a fronte del push di un commit sul branch main e se, analizzando i commit, è necessario eseguire un nuovo rilascio, il bot si occupa di eseguire una nuova release su *Github Release*.
