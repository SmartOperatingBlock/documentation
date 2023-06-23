---
title: Build Automation
layout: default
parent: DevOps
nav_order: 2
has_children: false
---

# Build Automation

Per automatizzare le attività di compilazione del codice sorgente, la gestione delle dipendenze e la configurazione dell'ambiente di sviluppo dei microservizi basati su *Kotlin* e *Java* si è scelto di utilizzare [*Gradle*](https://gradle.org/), uno strumento potente e flessibile per l'automazione delle build e la gestione delle dipendenze con una sintassi dichiarativa.

Al fine di garantire il principio DRY e gestire in modo organizzato, centralizzato e chiaro le dipendenze presenti nei microservizi, si è scelto di utilizzare il *Gradle Version Catalog* in formato *TOML*.