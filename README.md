# Cybersecurity SOC Lab

### Détection • Journalisation • Supervision • Triage • Réponse

Ce dépôt regroupe mes travaux de laboratoire autour des activités d'un **Security Operations Center (SOC)** : collecte des événements, télémétrie, détection, corrélation, qualification des alertes et premières étapes de réponse.

Il s'inscrit dans ma formation de **Conseiller en cybersécurité à l'IFAPME de Charleroi** et dans ma démarche générale : comprendre les systèmes et les réseaux avant de chercher à détecter ce qui s'y passe.

> **Un SOC ne se résume pas à un SIEM : il faut comprendre la source des événements, leur contexte et la logique de détection avant de conclure qu'une alerte représente un incident.**

---

## Objectif du dépôt

Ce laboratoire vise à montrer une progression pratique :

```text
Comprendre les sources de logs
        ↓
Collecter et centraliser les événements
        ↓
Améliorer la télémétrie
        ↓
Construire des règles de détection
        ↓
Corréler les événements
        ↓
Qualifier l'alerte
        ↓
Rechercher les faux positifs
        ↓
Escalader ou investiguer
        ↓
Documenter le résultat
```

L'objectif n'est pas de présenter une liste d'outils, mais de comprendre **ce que l'on observe, pourquoi on l'observe et comment transformer un événement technique en information exploitable**.

---

## Axes de travail

| Domaine | Outils / notions | Finalité |
|---|---|---|
| Journalisation | Windows Event Logs, EVTX | Comprendre les sources d'événements |
| Télémétrie | Sysmon | Enrichir la visibilité sur l'hôte |
| SIEM / XDR | Wazuh | Centraliser, rechercher et corréler |
| Détection | Sigma | Formaliser des règles portables |
| Protection endpoint | Microsoft Defender | Observer et contextualiser la sécurité poste |
| Réseau | Wireshark, Nmap | Ajouter le contexte réseau |
| Investigation | Hayabusa, Chainsaw, Velociraptor | Approfondir une alerte lorsque nécessaire |

---

## Structure

```text
cybersecurity-soc-lab/
│
├── soc-fundamentals/
├── logging-telemetry/
├── sysmon/
├── sigma/
├── wazuh/
├── defender/
├── detection-use-cases/
├── correlation-triage/
├── incident-workflow/
└── labs/
```

Chaque partie accueillera progressivement des notes, configurations, exercices et retours d'expérience issus de mes laboratoires.

---

## Méthode SOC

Pour chaque scénario, je souhaite conserver la même logique :

```text
Événement
   ↓
Source du log
   ↓
Contexte machine / utilisateur / réseau
   ↓
Règle ou mécanisme de détection
   ↓
Alerte
   ↓
Triage
   ↓
Vérification
   ↓
Faux positif / événement légitime / suspicion
   ↓
Escalade vers investigation si nécessaire
```

Cette méthode est volontairement simple : elle oblige à **revenir aux faits techniques** avant de tirer une conclusion.

---

## Ce que je veux démontrer

- comprendre la différence entre **événement, alerte et incident** ;
- identifier les sources de logs utiles ;
- lire et interpréter les Event ID Windows ;
- améliorer la visibilité avec Sysmon ;
- écrire et comprendre des règles Sigma ;
- utiliser Wazuh pour centraliser et analyser les événements ;
- corréler plusieurs indices plutôt que se fier à un seul signal ;
- documenter le raisonnement utilisé lors du triage ;
- savoir quand une alerte doit être transmise à une investigation DFIR.

---

## Positionnement

Ce dépôt représente la partie **détection et supervision** de mon portfolio.

Il se situe naturellement entre mes fondations système/réseau et mon laboratoire DFIR :

```text
Windows / Linux / Réseau
          ↓
      SOC / Détection
          ↓
     Triage d'alertes
          ↓
   Investigation DFIR
```

Le dépôt complémentaire dédié à l'investigation Windows est disponible ici :

[Windows DFIR Lab](https://github.com/bricehach/windows-dfir-lab)

---

## Cadre d'utilisation

Les contenus publiés ici sont orientés **formation, laboratoire, défense et compréhension des mécanismes de détection**. Les exemples sont documentés de manière à rester reproductibles et compréhensibles.

---

## Fil conducteur

**Collecter → observer → détecter → corréler → qualifier → vérifier → investiguer si nécessaire → documenter**
