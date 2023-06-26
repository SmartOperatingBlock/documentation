---
title: Continuous Delivery
layout: default
parent: DevOps
nav_order: 6
has_children: false
---

# Continuous Delivery

Per tutti i microservizi sviluppati, come anticipato, viene costruita l'immagine Docker associata sfruttando il `Dockerfile` presente in ogni *repository*. Esse vengono caricate sul *Container Registry* di *GitHub* (*ghcr.io*) e vengono versionate mantenendo l'allineamento con le *release* effettuate su *GitHub Release*. Il tutto avviene in automatico sfruttando il *workflow* di *Continuous Integration* e le *GitHub Actions* sviluppate e descritte nel capitolo [*Continuous Integration*](https://smartoperatingblock.github.io/documentation/docs/03-devops/continuousIntegration.html).

Ciò ha permesso di eseguire il *deploy* in maniera agile sfruttando *Docker Compose*. In particolare, è stata creata una repository [`bootstrap`](https://github.com/SmartOperatingBlock/bootstrap) con tutto il necessario al fine di eseguire il *deploy* dell'*Application layer*. Questo approccio ha permesso, tramite l'utilizzo degli strumenti descritti precedentemente *Renovate* e *Mergify*, di aggiornare le versioni delle immagini dei container presenti all'interno dello script automaticamente senza la necessità di modifiche manuali.
