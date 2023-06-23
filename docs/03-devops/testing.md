---
title: Testing
layout: default
parent: DevOps
nav_order: 3
has_children: false
---

# Testing

Al fine di verificare il corretto funzionamento, grazie ai principi della *Clean Architecture* adottati è stato possibile testare ogni layer in modo indipendente attraverso l'impiego di *Unit-Test*. 
Per testare i microservizi sono stati utilizzati i seguenti framework: 

+ [*Kotest*](https://kotest.io/): framework di test per il codice scritto in *Kotlin*. In particolare si è scelto di utilizzare lo stile *StringSpec*, il quale fornisce una sintassi dichiarativa nella definizione dei test. 
+ [*Junit5*](https://junit.org/junit5/): framework di test per il codice scritto in *Java*. 

Inoltre riportiamo le principali librerie che hanno permesso di testare le tecnologie utilizzate nel layer infrastrutturale: 

+ [*Ktor-server-test-host*](https://ktor.io/docs/testing.html): libreria per testare le API scritte utilizzando il framework *Ktor*
+ [*Embed-mongo*](https://github.com/flapdoodle-oss/de.flapdoodle.embed.mongo): libreria per eseguire un'istanza in locale di *MongoDB* su cui effettuare Unit-Test

Inoltre, al fine di testare il rispetto dei vincoli, i principi e le regole della *Clean Architecture* è stata utilizzata la libreria [*ArchUnit*](https://www.archunit.org/) per la realizzazione di test sull'architettura del sistema.

Per quanto riguarda il calcolo e la generazione della *Code Coverage* è stato utilizzato il tool [*JaCoCo*](https://www.jacoco.org/jacoco/index.html).