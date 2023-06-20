---
title: Analisi e Design del Business Domain
layout: default
parent: Descrizione del processo adottato
nav_order: 1
has_children: false
---

# Analisi e Design del Business Domain

Il campo del dominio sanitario presenta numerose sfaccettature che possono rendere estremamente complesso comprendere appieno questo ambito, soprattutto per coloro che non sono addetti ai lavori e non hanno familiarità con il linguaggio tecnico e le pratiche specifiche di questo settore.  A fronte di ciò si è reso necessario intraprendere un percorso di Knowledge Crunching, al fine di colmare il gap della lack of knowledge  e, ancora più importante, della lack of awareness. 

Considerando che il DDD ha l'obiettivo di ottenere una conoscenza condivisa del dominio, adottando un approccio che si avvicinasse alla realtà, è necessario stabilire un unico punto nel quale la conoscenza converge ed evolve in modo organizzato ed accessibile da tutti, anche dagli esperti di dominio in maniera semplice. A tal fine si è scelto di utilizzare [Confluence](https://www.atlassian.com/it/software/confluence), un software commerciale nel quale è stato  documentato sia l'analisi del problem space che la progettazione del solution space. 

La scelta di questo strumento è stata incentivata dalla possibilità di integrazione con strumenti di comunicazione come [Slack](https://slack.com/intl/it-it). Infatti, considerando che il processo di Knowledge Crunching necessita di più meeting, è necessario prevedere uno strumento che gestisca la comunicazione, assicurando cooperazione e collaborazione. 

Il sito di progetto è visitabile al seguente link:https://giacomoaccursi.atlassian.net/l/cp/vAxD2YKh 

Seguendo le best-practice del knowledge crunching abbiamo cercato, insieme all'esperto del dominio (il professore del corso), di comprendere il dominio del problema. Al termine di questo primo meeting è stata prodotta una mind-map che riassumesse i requisiti coarse-grained del sistema e che mettesse in evidenza i concetti chiave del dominio. Questo primo incontro ha inoltre permesso l'identificazione degli stakeholder coinvolti e gli esperti di dominio da consultare nelle fasi successive. A seguito di ciò, al fine di delineare il comportamento del sistema, è stato effettuato un ulteriore meeting che ha condotto alla redazione dei diagrammi dei casi d'uso. 
Partendo da essi abbiamo raffinato iterativamente la conoscenza di alcuni processi ponendo domande mirate al committente, aumentando la collaborazione e diminuendo l'ambiguità con l'ausilio di strumenti di sketching come il Domain Storytelling.
Gli ultimi dubbi rimasti e i dettagli prettamente tecnici sono stati chiariti effettuando un'intervista che ha coinvolto gli sviluppatori, l'esperto di dominio e un esperto tecnico dell'ospedale. 

Una volta ottenuta una soddisfacente conoscenza del dominio, al fine di gestire la complessità e lo spazio del problema, sono stati individuati i relativi sottodomini che lo compongono, classificandoli in una delle tre tipologie tipiche del DDD. Questo ci ha aiutato a suddividere il problema in modo che fosse di più facile gestione. 
Inoltre, per alcuni sottodomini è stata eseguita un'analisi più approfondita, accompagnata da una predizione della loro futura evoluzione, tramite l'ausilio di Core Domain Charts. 

Durante i vari meeting svolti, e per tutta la durata del progetto, si è cercato di individuare un linguaggio preciso e consistente eliminando qualsiasi forma di ambiguità, andando a creare di fatto quello che viene definito Ubiquitous Language. Nello specifico è stata creata una tabella dove ad ogni termine è associata una breve descrizione e i sottodomini d'interesse.

Nell'ultima fase di analisi del dominio del problema si è provveduto, per ogni sottodominio, alla formalizzazione dei requisiti secondo la suddivisione tradizionale (business, utente, funzionali, non funzionali e di implementazione). 