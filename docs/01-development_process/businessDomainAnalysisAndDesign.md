---
title: Analisi e Design del Business Domain
layout: default
parent: Descrizione del processo adottato
nav_order: 1
has_children: false
---

# Analisi e Design del Business Domain

Il campo del dominio sanitario presenta numerose sfaccettature che possono rendere estremamente complesso comprendere appieno questo ambito, soprattutto per coloro che non sono addetti ai lavori e non hanno familiarità con il linguaggio tecnico e le pratiche specifiche di questo settore.  A fronte di ciò si è reso necessario intraprendere un percorso di Knowledge Crunching, al fine di colmare il gap della lack of knowledge  e, ancora più importante, della lack of awareness. 

Considerando che il DDD ha l'obiettivo di ottenere una conoscenza condivisa del dominio è necessario stabilire un unico punto nel quale la conoscenza converge ed evolve in modo organizzato ed accessibile da tutti, anche dagli esperti di dominio in maniera semplice. A tal fine, adottando un approccio che si avvicinasse alla realtà, si è scelto di utilizzare [Confluence](https://www.atlassian.com/it/software/confluence), un software commerciale nel quale è stato documentata sia l'analisi del *problem space* che la progettazione del *solution space*. 

La scelta di questo strumento è stata incentivata dalla possibilità di integrazione con strumenti di comunicazione come [Slack](https://slack.com/intl/it-it). Infatti, considerando che il processo di Knowledge Crunching necessita di più meeting, è necessario prevedere uno strumento che gestisca la comunicazione, assicurando cooperazione e collaborazione. 

Il sito di progetto è visitabile al seguente link: [https://giacomoaccursi.atlassian.net/l/cp/vAxD2YKh](https://giacomoaccursi.atlassian.net/l/cp/vAxD2YKh)

Seguendo le best-practice del Knowledge Crunching abbiamo cercato, insieme all'esperto del dominio (il professore del corso), di comprendere il dominio del problema. Abbiamo svolto un primo meeting con l'obiettivo di raccogliere i requisiti coarse-grained del sistema e la struttura del blocco operatorio. Durante il meeting è stato eseguito dello sketching tramite la creazione di una mind-map che riassumesse e mettesse in evidenza i concetti chiave del dominio, evitando così la perdita di informazioni. Questo primo incontro ha inoltre permesso l'identificazione degli stakeholder coinvolti e gli esperti di dominio da consultare nelle fasi successive. A seguito di ciò, al fine di delineare il comportamento del sistema, è stato effettuato un ulteriore meeting che ha condotto alla redazione dei diagrammi dei casi d'uso. 
Partendo da essi abbiamo organizzato un ulteriore meeting al fine di raffinare, in modo iterativo ed incrementale, la conoscenza di alcuni processi ponendo domande mirate al committente. Questo ha permesso, tramite l'ausilio di strumenti di sketching come il Domain Storytelling, di ottenere un aumento della collaborazione diminuendo al tempo stesso l'ambiguità.
Infine, gli ultimi dubbi rimasti e i dettagli prettamente tecnici sono stati chiariti effettuando un'intervista che ha coinvolto gli sviluppatori, l'esperto di dominio e un esperto tecnico dell'ospedale. 

Una volta ottenuta una soddisfacente conoscenza del dominio, al fine di gestire la complessità e lo spazio del problema, sono stati individuati i relativi sottodomini che lo compongono, classificandoli in una delle tre tipologie tipiche del DDD. Questo ci ha aiutato a suddividere il problema in modo che fosse di più facile gestione e manutenibile. 
Inoltre, per alcuni sottodomini è stata eseguita un'analisi più approfondita, accompagnata da una predizione della loro futura evoluzione, tramite l'ausilio di Core Domain Charts. 

Durante i vari meeting svolti, e per tutta la durata del progetto, si è cercato di individuare un linguaggio preciso e consistente eliminando qualsiasi forma di ambiguità, andando a creare di fatto quello che viene definito Ubiquitous Language. Nello specifico è stata creata una tabella dove ad ogni termine è associata una breve descrizione e i sottodomini d'interesse.

Nell'ultima fase di analisi del dominio del problema si è provveduto, per ogni sottodominio, alla formalizzazione dei requisiti secondo la suddivisione tradizionale (business, utente, funzionali, non funzionali e di implementazione). 

La suddivisione del problema in sottodomini ha permesso di comprendere quali siano le parti più importanti e in cui impiegare la maggior parte delle risorse. Quindi, dopo aver analizzato il problem space si è passati alla fase di analisi e progettazione del solution space partendo dalla progettazione dei Bounded Context che hanno permesso allo stesso tempo di iniziare il design dell'architettura del sistema stesso.

Nella progettazione dei Bounded Context abbiamo cercato di progettarli per rimpiazzo invece che per riuso, seguendo le best-practices del DDD. L'obiettivo di essi è la separazione dei modelli e dei loro vari significati, evitando così l'ambiguità e rispettando il Single Responsibility Principle (SRP). Inoltre, ogni Bounded Context è stato pensato per essere un servizio indipendente nella sua progettazione, implementazione e sopratutto nel suo versionamento ed evoluzione. Essi rappresentano non solo un boundary di modello, ma anche un boundary fisico e, cercando di simulare un contesto più reale possibile, abbiamo cercato di creare dei sotto-team (da una, fino al massimo di due persone) che si occuppassero di ogni singolo Bounded Context.

Come riportanto nel [sito di progetto](https://giacomoaccursi.atlassian.net/wiki/spaces/SOB/pages/3276818/Context+Map), l'analisi dettagliata svolta sui sottodomini ha portato ad una corrispondenza 1:1 tra i sottodomini e i Bounded Context, anche se i primi sono stati semplicemente individuati, mentre i secondi progettati.

Dopodichè, al fine di definire le relazioni presenti tra i diversi Bounded Context, è stata creata la relativa Context Map, sfruttando il software *Context Mapper*, che ha permesso di mettere in evidenza aspetti tecnici ed organizzativi.

Una volta definita la Context Map abbiamo formalizzato il modello del dominio di ogni sottodominio individuato sfruttando gli elementi del design tattico del DDD che ci hanno permesso di definire un meta-modello con cui poi mappare i concetti, individuati nel dominio, all'interno del codice, cercando di rispettare al tempo stesso l'Ubiquitous Language.

Dall'intervista svolta con l'esperto di dominio è emersa la necessità dello sviluppo di due tipologie di dashboard: l'*Operating Block Dashboard* e l'*Operating Room Dashboard*, perciò abbiamo organizzato un ulteriore meeting con l'obiettivo di definire i rispettivi mockup. Al fine di aumentare la collaborazione e la comprensione, si è scelto di sfruttare lo strumento *Figma* per produrre mockup *interattivi*.

Il processo di analisi e di design del Business Domain del problema ha permesso di ottenere una conoscenza che fosse funzionale al mantenimento del software nella sua evoluzione e quindi che permettesse ad esso di essere più versatile, flessibile e manutenibile. Ciò è diverso dalle analisi dei requisiti che abbiamo svolto nei progetti precedenti con l'obiettivo di raccogliere informazioni per la progettazione di un'unica versione del software.

