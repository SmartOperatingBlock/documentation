---
title: Implementazione
layout: default
has_children: false
nav_order: 5
---
# Implementazione

Considerando l'obbiettivo della relazione, in questa sezione verranno presentati i principali linguaggi e le principali tecnologie utilizzate senza entrare nei dettagli implementativi. 

## Physical Layer

La *Centralina di zona* è stata sviluppata utilizzando il linguaggio *C++* sfruttando il framework *Wiring* mentre il *Gateway di blocco* è stato sviluppato utilizzando [*Node-RED*](https://nodered.org/). 

## Digital Twins Layer 

Per la modellazione dei *Digital Twins* si è sfruttato il linguaggio *Digital Twins Definition Language* (DTDL) mentre per lo sviluppo della *Azure Function* si è utilizzato *C#*.

## Application Layer 

Considerando che ogni microservizio, seguendo i principi dello stile architetturale, può essere implementato utilizzando lo stack tecnologico più adeguato, si è fatto uso del linguaggio *Java* per il microservizio *Automation Management* e di *Kotlin* per i restanti. 
Le principali librerie e framework utilizzati sono stati: 

+ **Kafka Clients**, per l'interazione con l'event broker
+ **Ktor**, per la realizzazione delle API REST
+ **Kmongo**, per l'interazione con MongoDB
+ **JaCaMo**, per lo sviluppo del sistema multi-agente presente nel microservizio *Automation Management*
+ **Vert.X**, per lo sviluppo del microservizio *API Gateway*
+ **RxKotlin**, per agevolare la gestione e il mapping del flusso degli eventi nel microservizio *Digital Twins Event Gateway*
