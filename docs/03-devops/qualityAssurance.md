---
title: Quality Assurance
layout: default
parent: DevOps
nav_order: 4
has_children: false
---

# Quality Assurance

Una buona pratica della Build Automation e in generale del DevOps è l'utilizzo di tools per la validazione della qualità del codice prodotto. 
Per i microservizi basati su Kotlin: 

+ **Static Code Analysis**: [*Detekt*](https://github.com/detekt/detekt), [*Cpd*](https://pmd.github.io/pmd/pmd_userdocs_cpd.html) 
+ **Style Checking**: [*Ktlint*](https://github.com/pinterest/ktlint)

Per i microservizi basati su Java: 

+ **Static Code Analysis**: [*PMD*](https://pmd.github.io/), [*Cpd*](https://pmd.github.io/pmd/pmd_userdocs_cpd.html) , [*SpotBugs*](https://spotbugs.github.io/)
+ **Style Checking**: [*CheckStyle*](https://checkstyle.org/)

Per agevolare la configurazione di entrambi gli stack si è fatto uso di due plugin *Gradle*, rispettivamente [`gradle-kotlin-qa`](https://github.com/DanySK/gradle-kotlin-qa) e [`gradle-java-qa`](https://github.com/DanySK/gradle-java-qa).
L'esecuzione di questi controlli avviene anche prima di ciascun commit effettuato tramite l'*hook pre-commit* descritto precedentemente.

Al fine di supportare ulteriormente il processo di Quality Assurance tramite ad esempio l'analisi e il rilevamento di code smell, problemi di sicurezza, debito tecnico e duplicazione di codice si è fatto uso dei servizi cloud-based [*SonarCloud*](https://www.sonarsource.com/products/sonarcloud/) e [*GitGuardian*](https://www.gitguardian.com/).
