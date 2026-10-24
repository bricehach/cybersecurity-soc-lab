# Google dorking et recherche OSINT

## Méthodes, limites, vérification et pratique responsable

**Support de cours avancé pour une deuxième année en cybersécurité**  
Édition pédagogique — 24 octobre 2026

Ce cours apprend à transformer une question en requêtes de recherche précises, à interpréter les résultats sans leur accorder une confiance excessive et à documenter des constats vérifiables. Google est le fil conducteur. Les autres moteurs, services de recherche et outils spécialisés sont présentés comme des extensions, avec leurs apports et leurs limites.

Les exemples de recherche portent sur des domaines de démonstration ou des ressources publiques sans données sensibles. Les exercices ne demandent ni accès à un compte tiers, ni collecte de secrets, ni test intrusif.

# Repères pour utiliser le cours

Le support s’adresse à des étudiants qui connaissent la navigation Web, les domaines, les URL et les notions de base en cybersécurité. Il ne suppose pas de pratique préalable de l’OSINT. Le cours progresse des opérateurs Google documentés vers une méthode de recherche complète, puis vers les limites qui imposent d’utiliser d’autres sources ou des outils spécialisés.

## Objectifs pédagogiques

- Formuler une question de recherche avec un périmètre, une période et un objectif explicites.

- Construire une requête Google en combinant termes, expressions exactes, exclusions, domaines, dates et types de fichiers.

- Distinguer une fonctionnalité documentée par Google d’une syntaxe populaire dont le comportement peut varier.

- Vérifier une information avec la page source, des sources indépendantes et des éléments de contexte.

- Expliquer pourquoi un résultat absent ne prouve pas l’absence d’une information, et pourquoi un résultat trouvé ne prouve pas sa véracité.

- Reconnaître les situations où Google ne suffit pas et choisir une famille de sources ou d’outils adaptée.

- Appliquer des règles de minimisation, de traçabilité, de prudence et de protection des personnes.

## Parcours conseillé

| **Séquence**                            | **Durée indicative** | **Résultat attendu**                                       |
|-----------------------------------------|----------------------|------------------------------------------------------------|
| 1\. Cadre et modèle de recherche        | 1 h 30               | Définir une question et un périmètre.                      |
| 2\. Opérateurs Google documentés        | 2 h                  | Écrire et expliquer des requêtes simples.                  |
| 3\. Requêtes combinées et reformulation | 2 h                  | Réduire le bruit sans éliminer les résultats utiles.       |
| 4\. Vérification et preuve              | 2 h                  | Évaluer une page, recouper et consigner.                   |
| 5\. Domaines d’application et limites   | 1 h 30               | Choisir les sources adaptées à la question.                |
| 6\. Ateliers pratiques                  | 4 à 6 h              | Résoudre des scénarios et rendre un dossier reproductible. |
| 7\. Restitution et évaluation           | 1 h                  | Justifier la méthode, les limites et les conclusions.      |

Le cours peut être enseigné sur environ 14 à 16 heures, ou réparti en séances plus courtes. La durée dépend du temps consacré aux recherches pratiques, aux échanges et à la correction. Les exercices et corrigés sont inclus dans ce support.

## Plan du support

- 1\. Comprendre le dorking et l’OSINT

- 2\. La recherche Google et ses limites

- 3\. Les opérateurs Google documentés

- 4\. Les syntaxes courantes à traiter avec prudence

- 5\. Construire une recherche reproductible

- 6\. Vérifier et documenter les résultats

- 7\. Domaines d’application au-delà de l’OSINT

- 8\. Quand Google ne suffit plus

- 9\. Cadre juridique, éthique et sécurité

- 10\. Ateliers pratiques

- 11\. Corrigés et grille d’évaluation

- 12\. Fiches de référence et sources

# 1. Comprendre le dorking et l’OSINT

## 1.1 Ce que signifie Google dorking

Le terme « Google dorking » désigne l’emploi de requêtes structurées et d’opérateurs de recherche pour cibler les pages et documents déjà accessibles au moteur. On trouve aussi les expressions « Google hacking » et « Google search operators ». Le terme « dork » est parfois associé à des recherches de sécurité offensives ; dans ce cours, il désigne une technique de recherche, pas une autorisation d’accéder à un système ou à des informations privées.

Un moteur de recherche ne parcourt pas Internet en temps réel à chaque requête. Il explore certaines pages, en conserve des représentations dans un index, puis classe et présente une partie des résultats en fonction de nombreux signaux. Une requête affinée agit sur ce que le moteur tente de retrouver dans son index ; elle n’ouvre pas un accès privilégié à un serveur.

## 1.2 Dorking et OSINT

L’OSINT, ou renseignement d’origine sources ouvertes, est une démarche de collecte et d’analyse d’informations obtenues à partir de sources ouvertes. La recherche dans Google peut contribuer à la découverte de sources, mais elle n’est qu’une étape. Une enquête OSINT exige une question légitime, un périmètre, une stratégie de collecte, une évaluation des sources, une corroboration et une restitution des incertitudes.

| **Élément** | **Question de travail**                                                        |
|-------------|--------------------------------------------------------------------------------|
| Question    | Quelle décision ou compréhension la recherche doit-elle éclairer ?             |
| Périmètre   | Qui ou quoi est dans le champ ? Quelles limites géographiques et temporelles ? |
| Sources     | Quels sites, documents, bases ou archives peuvent répondre ?                   |
| Collecte    | Quelles requêtes ou méthodes permettront de trouver ces sources ?              |
| Analyse     | Que montrent réellement les éléments recueillis ? Que ne montrent-ils pas ?    |
| Restitution | Comment permettre à quelqu’un d’autre de vérifier le cheminement ?             |

## 1.3 La différence entre recherche, constat et conclusion

Un résultat Google est un indice de découverte, pas une conclusion. La page source peut être obsolète, tronquée, mal attribuée, copiée depuis une autre source ou affichée à cause d’un terme secondaire. Le travail consiste à ouvrir la source, vérifier son contexte, rechercher une confirmation indépendante et distinguer les faits observés des interprétations.

> Requête trouvée → résultat candidat → page source vérifiée → recoupement → constat qualifié

# 2. La recherche Google et ses limites

## 2.1 Comment lire une recherche

Google peut interpréter une requête de façon souple. Il peut tenir compte des synonymes, de la langue, de la localisation, de la fraîcheur, de la popularité et d’autres signaux. Deux étudiants qui saisissent une requête similaire peuvent donc voir des classements ou des résultats différents selon leurs paramètres, leur région, le moment et l’évolution de l’index. Une requête complexe ne constitue pas une spécification formelle qui garantit un ensemble exhaustif.

## 2.2 Indexation, exploration et accès

- Une page peut être absente de l’index parce qu’elle n’a pas été découverte, parce que l’exploration ou l’indexation a été empêchée, parce qu’elle est nouvelle, derrière une authentification, ou parce que le moteur l’a jugée peu utile.

- Une page retirée du site peut rester visible temporairement dans des résultats ou des copies. À l’inverse, un contenu public peut ne jamais apparaître dans Google.

- Les documents indexés ne couvrent pas tous les formats, toutes les pages, toutes les langues ni tous les sites.

- La commande site: aide à limiter la recherche à un site ou à un préfixe d’URL, mais le nombre affiché n’est pas un inventaire fiable du contenu indexé.

- Google peut réécrire, ignorer ou interpréter différemment une partie des termes ou opérateurs. Les filtres de recherche et leurs libellés changent selon les requêtes et les interfaces.

Pour contrôler l’indexation d’un site que l’on possède ou administre, Google recommande des outils propriétaires tels que Search Console et l’inspection d’URL. Une recherche publique avec site: n’est pas un substitut à ces outils.

## 2.3 Pourquoi les résultats changent

| **Facteur**                  | **Effet possible**                                   | **Précaution**                                                          |
|------------------------------|------------------------------------------------------|-------------------------------------------------------------------------|
| Région et langue             | Résultats locaux ou linguistiques différents.        | Consigner la langue, le pays et les filtres utilisés.                   |
| Date et évolution de l’index | Une URL apparaît, disparaît ou change de position.   | Noter la date de consultation.                                          |
| Personnalisation et contexte | Classement ou suggestions variables.                 | Répéter la recherche dans un contexte distinct si c’est important.      |
| Reformulation automatique    | Synonymes ou termes associés élargissent la requête. | Lire les détails du résultat et reformuler avec des termes alternatifs. |
| Paramètres et filtres        | Les outils visibles ne sont pas constants.           | Décrire les filtres appliqués dans le journal de recherche.             |

## 2.4 Ce que le moteur ne prouve pas

- Un résultat ne prouve pas que la page est exacte, légitime ou actuelle.

- L’absence de résultat ne prouve pas qu’un document ou un événement n’existe pas.

- Le nombre approximatif de résultats n’est ni un comptage d’inventaire ni une mesure statistique.

- Une page publique n’est pas automatiquement libre de réutilisation ni exempte de données personnelles.

- Une URL indexée ne donne pas, à elle seule, le droit d’accéder à un espace restreint, de contourner une protection ou de réutiliser son contenu.

# 3. Les opérateurs Google documentés

À la date de préparation de ce cours, l’aide de Google documente notamment les guillemets pour une expression exacte, site:, le signe moins, before:, after: et filetype:. Google Search Central documente aussi imagesize: et src: pour Google Images. Vérifier la documentation officielle avant de réutiliser un opérateur dans un support publié : les fonctionnalités évoluent.

| **Syntaxe**               | **Usage documenté**                                                               | **Exemple sûr**                         | **Attention**                                                                                                    |
|---------------------------|-----------------------------------------------------------------------------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------|
| "expression"              | Chercher une correspondance exacte d’une expression.                              | "rapport annuel" "exemple"              | L’expression peut être absente de l’extrait, ou le moteur peut afficher des correspondances pertinentes proches. |
| site:                     | Limiter aux résultats d’un domaine, d’une URL ou d’un préfixe.                    | site:example.com cybersécurité          | Ne pas ajouter d’espace après les deux-points. Ce n’est pas un inventaire exhaustif.                             |
| -terme                    | Exclure un terme des résultats.                                                   | jaguar vitesse -voiture                 | Le signe moins doit précéder le terme sans espace.                                                               |
| before:date               | Cibler les documents que Google considère mis à jour avant une date.              | cybersécurité before:2025-01-01         | La date affichée ou interprétée peut ne pas correspondre à la date de première publication.                      |
| after:date                | Cibler les documents que Google considère mis à jour après une date.              | cybersécurité after:2025-01-01          | Même réserve sur les dates ; vérifier la page source.                                                            |
| filetype:ext              | Limiter à un type de fichier ou une extension reconnue.                           | site:example.com filetype:pdf rapport   | Le type peut provenir de l’en-tête HTTP ou de l’extension. L’indexation dépend du format et du contenu.          |
| imagesize:largeurxhauteur | Chercher des pages contenant une image de dimensions précises dans Google Images. | imagesize:1200x800 paysage              | Fonctionne dans Google Images.                                                                                   |
| src:URL-image             | Chercher des pages référençant une URL d’image précise dans Google Images.        | src:https://example.com/images/logo.png | Fonctionne dans Google Images ; l’exemple ne garantit aucun résultat.                                            |

## 3.1 Espaces et ponctuation

L’opérateur et sa valeur sont attachés : site:example.com fonctionne comme filtre, alors que site: example.com n’est pas la même formulation. Les exemples fournis ici sont des modèles de syntaxe, pas des promesses de résultats. Les noms de domaines example.com et example.org sont réservés aux exemples de documentation.

> site:example.com filetype:pdf "rapport annuel"

Lecture : chercher une expression exacte dans les résultats PDF associés au domaine de démonstration. Pour une vraie recherche, remplacer le domaine et les mots par des valeurs adaptées au mandat, puis ouvrir chaque résultat pertinent.

## 3.2 Filtres de l’interface et opérateurs

Les menus de Google permettent aussi de choisir certaines catégories ou périodes. Un filtre d’interface peut être plus simple qu’un opérateur et se révéler plus robuste pour une recherche ponctuelle. Les filtres ne sont pas toujours affichés de la même manière. Dans une démarche reproductible, noter leur nom, la période choisie, la langue et la date de la recherche.

# 4. Les syntaxes courantes à traiter avec prudence

De nombreux guides en ligne enseignent des syntaxes supplémentaires comme intitle:, inurl:, intext:, inanchor:, allintitle:, allinurl:, OR, parenthèses, astérisque ou AROUND(n). Leur présence dans des tutoriels ne signifie pas qu’elles sont garanties par Google. Certaines peuvent fonctionner pour certaines requêtes ou périodes, changer de comportement, être ignorées ou ne plus être disponibles.

| **Syntaxe souvent citée** | **Interprétation généralement recherchée**         | **Statut pédagogique**                                                                                    |
|---------------------------|----------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| intitle:terme             | Chercher un terme dans le titre.                   | Non listé dans la page d’aide Google consultée ; tester et consigner.                                     |
| inurl:terme               | Chercher un terme dans l’URL.                      | Non listé dans l’aide consultée ; ne pas promettre de couverture.                                         |
| intext:terme              | Cibler le texte de la page.                        | Comportement variable ; les termes ordinaires suffisent souvent.                                          |
| OR                        | Proposer une alternative entre termes.             | Peut être interprété selon la requête ; tester chaque branche séparément.                                 |
| AROUND(n)                 | Chercher deux termes à proximité l’un de l’autre.  | Syntaxe souvent documentée par des tiers ; non garantie par l’aide consultée.                             |
| \*                        | Joker dans une expression ou remplacement de mots. | Interprétation dépendante du contexte ; tester avec des phrases témoins.                                  |
| cache:                    | Accéder à une copie mise en cache par Google.      | Opérateur retiré de la documentation et ne fonctionnant plus selon Google Search Central, septembre 2026. |

## 4.1 Procédure de test d’une syntaxe non documentée

> **1.** Formuler une requête de base avec des termes ordinaires.
>
> **2.** Ajouter un seul opérateur non documenté.
>
> **3.** Comparer le nombre et la nature des résultats avec la requête de base.
>
> **4.** Ouvrir plusieurs pages pour vérifier si l’opérateur semble réellement filtrer le champ visé.
>
> **5.** Répéter avec une autre formulation et, si possible, un autre moteur.
>
> **6.** Consigner la date, le moteur, la requête exacte et l’observation.

Une syntaxe non documentée peut rester utile comme raccourci exploratoire, à condition de la traiter comme une hypothèse. Elle ne doit pas devenir une dépendance d’un protocole critique sans validation indépendante.

# 5. Construire une recherche reproductible

## 5.1 Commencer par une question

Une bonne recherche commence par une question claire, pas par une longue requête. Une question trop large produit du bruit ; une question trop étroite peut masquer des éléments pertinents. Définir l’entité ou le sujet, la période, le lieu, le type d’information recherché et le résultat attendu.

| **Question floue**                                    | **Question de travail mieux délimitée**                                                                                             |
|-------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Quelles informations existe-t-il sur une entreprise ? | Quels rapports publics de durabilité l’organisation publie-t-elle depuis 2023 sur son domaine officiel ?                            |
| Que s’est-il passé dans cette attaque ?               | Quelles déclarations publiques et chronologies publiées par des sources identifiées décrivent l’incident X entre les dates A et B ? |
| Que trouve-t-on sur le Wi-Fi ?                        | Quels guides de sécurité des réseaux Wi-Fi sont publiés par des organismes de normalisation ou des autorités publiques ?            |

## 5.2 Transformer la question en concepts

Décomposer la question en blocs de termes : sujet principal, synonymes, nom officiel, acronymes, variantes linguistiques, contexte et type de source. Les termes doivent être testés séparément avant d’être combinés. Cette étape réduit le risque d’exclure une bonne source simplement parce qu’elle emploie un vocabulaire différent.

> Sujet + variante + contexte + domaine ou type de document + période

Exemple pédagogique : chercher des recommandations officielles sur la journalisation des événements Windows.

> windows event logging security guidance
>
> site:cisa.gov Windows logging guidance
>
> site:learn.microsoft.com Windows event logging security
>
> "event logging" windows security filetype:pdf

On commence large, puis on ajoute un filtre à la fois. Les domaines institutionnels illustrent une stratégie de source ; leur présence ne signifie pas qu’ils sont les seules sources pertinentes.

## 5.3 Progression en entonnoir

> **1.** Recherche large par concepts pour découvrir le vocabulaire et les principales sources.
>
> **2.** Recherche ciblée par domaine pour vérifier les publications d’une organisation précise.
>
> **3.** Recherche documentaire avec filetype: lorsque le type de document compte.
>
> **4.** Recherche temporelle avec after: et before: si la période est définie.
>
> **5.** Exclusion d’un sens parasite avec le signe moins, après avoir constaté le bruit.
>
> **6.** Recoupement par une nouvelle formulation et une source indépendante.

## 5.4 Exemples de formulation

| **Objectif**                     | **Formulation de départ**                                             | **Raison de la formulation**                                    |
|----------------------------------|-----------------------------------------------------------------------|-----------------------------------------------------------------|
| Trouver une politique publique   | site:example.org "politique de sécurité"                              | Domaine limité et expression exacte.                            |
| Trouver un rapport au format PDF | site:example.org filetype:pdf rapport sécurité                        | Domaine, type de fichier et mots-clés.                          |
| Comparer deux termes             | "responsible disclosure" OR "coordinated vulnerability disclosure"    | Alternative exploratoire ; tester les deux branches séparément. |
| Limiter dans le temps            | site:example.org incident response after:2024-01-01 before:2026-01-01 | Période bornée, dates à confirmer sur les pages source.         |
| Éviter un sens parasite          | jaguar vitesse -voiture                                               | Exclusion d’un sens constaté comme non pertinent.               |

La ligne OR est volontairement marquée comme une syntaxe à vérifier : la page d’aide Google consultée ne la liste pas parmi les opérateurs populaires qu’elle documente. Une méthode plus robuste consiste à exécuter deux requêtes, puis à comparer les résultats.

# 6. Vérifier et documenter les résultats

## 6.1 Vérification à plusieurs niveaux

> **1.** Résultat : le titre, l’URL, l’extrait et la date présentés par le moteur sont-ils cohérents avec la question ?
>
> **2.** Page : le contenu est-il réellement présent sur la page ouverte ? Le document correspond-il à l’extrait ?
>
> **3.** Provenance : qui publie la page ? L’auteur, l’organisation et le rôle sont-ils identifiables ?
>
> **4.** Contexte : quelle est la date de publication ou de mise à jour ? Le contenu est-il cité, repris ou contesté ailleurs ?
>
> **5.** Corroboration : une source indépendante confirme-t-elle le fait principal ? La source secondaire renvoie-t-elle à l’original ?
>
> **6.** Limites : qu’est-ce que cette preuve ne permet pas de conclure ?

## 6.2 Évaluer la source sans score magique

Une grille peut aider à poser les bonnes questions, mais un total chiffré ne transforme pas une source faible en source fiable. Évaluer séparément l’autorité, la proximité avec l’événement, la fraîcheur, la transparence méthodologique et la corroboration. Une source officielle peut être la meilleure source pour connaître sa propre annonce, sans être indépendante lorsqu’elle décrit sa performance ou sa responsabilité.

| **Critère**             | **Questions à poser**                                                                         |
|-------------------------|-----------------------------------------------------------------------------------------------|
| Identité                | Qui publie ? La personne ou l’organisation est-elle identifiable ?                            |
| Compétence et proximité | L’auteur observe-t-il directement le fait ou le rapporte-t-il ?                               |
| Date                    | Quand la page a-t-elle été publiée et mise à jour ?                                           |
| Méthode                 | La page montre-t-elle des documents, des données ou une méthode vérifiable ?                  |
| Intérêt                 | L’auteur a-t-il un intérêt, un rôle ou un biais à déclarer ?                                  |
| Indépendance            | La seconde source apporte-t-elle une confirmation indépendante ou répète-t-elle la première ? |
| Stabilité               | L’URL est-elle durable ? Existe-t-il une version archivée licite et contextualisée ?          |

## 6.3 Journal de recherche minimal

Pour rendre une recherche reproductible, consigner les requêtes qui ont réellement contribué à la découverte, les filtres utilisés, la date, la source et ce qui a été vérifié. Éviter de stocker des données personnelles inutiles ou des copies de documents sensibles.

| **Champ**            | **Contenu à noter**                                                |
|----------------------|--------------------------------------------------------------------|
| Identifiant          | Numéro court de l’élément, par exemple S-01.                       |
| Question             | Question à laquelle la recherche contribue.                        |
| Requête              | Texte exact, y compris les opérateurs et les guillemets.           |
| Moteur et contexte   | Google Web ou Images, langue, région et filtres visibles.          |
| Date de consultation | Date et heure avec fuseau si cela compte.                          |
| URL source           | Lien direct et titre de la page.                                   |
| Observation          | Ce que la page montre, sans interprétation excessive.              |
| Vérification         | Sources recoupées, éléments de contexte, contradiction éventuelle. |
| Limite               | Ce qui reste inconnu ou incertain.                                 |
| Décision             | Retenu, à confirmer, écarté ; justification courte.                |

# 7. Domaines d’application au-delà de l’OSINT

Les opérateurs de recherche sont des outils généraux. Le même raisonnement peut aider à trouver des documents publics, des publications académiques, des notices, des communiqués, des normes, des textes juridiques ou des ressources d’assistance. Le domaine d’application détermine les sources à privilégier et les précautions à prendre.

| **Domaine**                      | **Exemple d’objectif**                                          | **Source à privilégier**                                 | **Limite fréquente**                                                  |
|----------------------------------|-----------------------------------------------------------------|----------------------------------------------------------|-----------------------------------------------------------------------|
| Recherche documentaire           | Trouver un rapport ou une note technique.                       | Éditeur ou organisme auteur.                             | Versions multiples et documents non indexés.                          |
| Veille technologique             | Suivre une évolution ou une publication.                        | Documentation produit, avis de sécurité, dépôt officiel. | Résultats retardés ou annonces reprises sans contexte.                |
| Recherche académique             | Trouver des articles et actes.                                  | Éditeur, dépôt institutionnel, index spécialisé.         | Google n’est pas une base bibliographique exhaustive.                 |
| Journalisme et vérification      | Localiser la première publication ou une déclaration.           | Source primaire, archives et témoignages attribués.      | L’extrait de moteur n’est pas une preuve complète.                    |
| Cybersécurité défensive          | Examiner l’exposition publique d’un domaine détenu ou autorisé. | Search Console, inventaire interne, équipe propriétaire. | Google ne voit qu’une partie de l’exposition.                         |
| Audit de contenu                 | Repérer des pages oubliées ou des versions publiques.           | Site sous mandat et responsables de contenu.             | Résultats indexés parfois obsolètes ou incomplets.                    |
| Administration et textes publics | Retrouver une publication officielle.                           | Portail institutionnel et texte consolidé.               | Une page de résultats peut pointer vers une ancienne version.         |
| Analyse de marché                | Comparer des annonces ou caractéristiques publiées.             | Pages des fournisseurs et documents datés.               | Les descriptions marketing ne sont pas des validations indépendantes. |

## 7.1 Cybersécurité défensive avec un mandat

Dans un audit d’exposition publique, le moteur peut aider à repérer du contenu public associé au périmètre confié, comme des pages de documentation, anciennes versions de pages ou fichiers publiés. La recherche doit rester passive, limitée au domaine autorisé et documentée. La découverte d’une information inattendue ne justifie pas de tenter une connexion, d’exploiter une faiblesse, de télécharger en masse des données personnelles ou de tester des identifiants.

Pour un domaine administré par l’organisation, compléter la recherche par l’inventaire interne, les journaux, la gestion de contenu, les configurations du serveur Web et les outils propriétaires de suivi d’indexation. Les résultats Google signalent parfois une piste ; ils ne remplacent pas une vérification auprès du propriétaire du système.

## 7.2 Exemples de formulation par domaine

Les formulations suivantes montrent comment adapter les mêmes opérateurs à des besoins différents. Elles utilisent des sujets publics et des domaines de démonstration. Les termes peuvent être remplacés, mais le périmètre et le but doivent rester légitimes.

| **Domaine**                  | **Requête modèle**                                        | **Commentaire pédagogique**                                                                             |
|------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| Documentation administrative | site:example.gov "formulaire de demande"                  | Domaine et expression exacte ; vérifier la version et l’autorité du portail.                            |
| Marchés publics              | site:example.gov filetype:pdf marché public cybersécurité | Piste vers des avis ou rapports ; consulter le portail officiel des marchés.                            |
| Recherche académique         | "network security" "systematic review" filetype:pdf       | Découverte initiale, à compléter par une base bibliographique spécialisée.                              |
| Normes et recommandations    | site:example.org "incident response" guideline            | Cibler une organisation qui publie des guides.                                                          |
| Veille produit               | site:docs.example.com release notes security              | Rechercher dans la documentation ; comparer avec les notes de version originales.                       |
| Fact-checking                | "citation exacte" source originale                        | Retrouver une formulation attribuée ; vérifier le contexte avant de la citer.                           |
| Histoire d’une annonce       | site:example.org announcement after:2024-01-01            | Les dates du moteur sont indicatives et doivent être vérifiées sur la page.                             |
| Audit de contenu autorisé    | site:mondomaine.example filetype:pdf                      | À utiliser uniquement pour un domaine appartenant au mandat ; transmettre les constats au propriétaire. |
| Tourisme et patrimoine       | site:example.museum collection "nom de l’objet"           | Recherche d’un catalogue public ; vérifier les droits de réutilisation des images.                      |
| Éducation et formation       | site:example.edu filetype:pdf syllabus cybersecurity      | Découvrir un programme public ; la disponibilité d’un PDF ne garantit pas qu’il soit à jour.            |

# 8. Quand Google ne suffit plus

La décision de passer à un autre moyen dépend de la question, du périmètre et du besoin de couverture. Ajouter des opérateurs à une recherche ne compense pas l’absence d’indexation, de structure, d’historique ou de données derrière authentification.

| **Besoin**                              | **Moyen complémentaire**                                                           | **Ce qu’il apporte**                                      | **Ce qu’il ne garantit pas**                                                      |
|-----------------------------------------|------------------------------------------------------------------------------------|-----------------------------------------------------------|-----------------------------------------------------------------------------------|
| Comparer plusieurs index                | Autres moteurs généralistes, dont Bing, DuckDuckGo ou Brave Search.                | Couverture, classement et syntaxe différents.             | Aucun moteur ne couvre tout le Web.                                               |
| Recherche de publications scientifiques | Google Scholar et bases bibliographiques spécialisées.                             | Métadonnées et liens vers publications.                   | Accès au texte intégral et exhaustivité variables.                                |
| Historique d’une page publique          | Archives Web comme Internet Archive, si l’URL y est disponible.                    | Captures datées et versions antérieures.                  | Pas de capture complète ni d’horodatage universellement probant.                  |
| Recherche de code                       | Dépôts publics et plateformes de code avec leur recherche native.                  | Recherche sur le contenu et l’historique du dépôt.        | Ne pas rechercher ni réutiliser des secrets ; signaler selon les procédures.      |
| Inventaire d’actifs Internet            | Services de recherche d’infrastructure comme Shodan ou Censys, selon leurs règles. | Métadonnées d’exposition observées par leurs collecteurs. | Données datées, parfois inexactes ; ne remplacent pas la validation autorisée.    |
| Données officielles et textes           | Portails gouvernementaux, registres et bases légales.                              | Source primaire et statut documentaire.                   | La recherche et la réutilisation restent soumises aux règles propres à la source. |
| Réseaux sociaux publics                 | Recherche native de la plateforme et archives licites.                             | Contexte de publication et relations temporelles.         | Les réglages, suppressions et politiques de plateforme limitent la couverture.    |
| Vérification visuelle                   | Recherche inversée d’image et outils d’analyse de médias.                          | Pistes sur la réutilisation et le contexte d’une image.   | Une correspondance visuelle ne prouve pas l’authenticité ni le lieu.              |

## 8.1 Opérateurs d’autres moteurs

Les syntaxes ne sont pas portables automatiquement. DuckDuckGo publie par exemple une aide qui décrit les guillemets, le signe moins, filetype:, site:, intitle: et inurl:, tout en avertissant que certaines syntaxes avancées peuvent ne pas fonctionner correctement sur toutes les requêtes. Il faut donc consulter l’aide du moteur visé, tester les filtres et noter l’outil utilisé. Les opérateurs d’un moteur ne doivent pas être présentés comme des commandes universelles.

## 8.2 Décider de changer de méthode

> **1.** Le besoin est-il de découvrir, d’exhaustivement inventorier, de suivre dans le temps ou de vérifier un fait ?
>
> **2.** La source recherchée est-elle indexée par un moteur généraliste ?
>
> **3.** Une base spécialisée ou un portail primaire offre-t-il une recherche structurée ?
>
> **4.** La méthode envisagée est-elle passive et comprise dans le mandat ?
>
> **5.** Les conditions d’utilisation, la vie privée et la conservation des données sont-elles prises en compte ?
>
> **6.** Le résultat peut-il être vérifié par une seconde voie indépendante ?

# 9. Cadre juridique, éthique et sécurité

Ce cours n’est pas un avis juridique. Les étudiants doivent travailler selon le mandat, les règles de l’établissement et les lois applicables. En Belgique et dans l’Union européenne, une information accessible au public peut rester une donnée à caractère personnel. Sa collecte, son organisation, son croisement, sa conservation ou sa diffusion peuvent constituer un traitement de données soumis au RGPD.

## 9.1 Principes à appliquer en pratique

- Finalité : savoir pourquoi la recherche est menée et ne pas étendre la finalité sans justification.

- Nécessité et minimisation : ne recueillir que les éléments nécessaires à la question.

- Exactitude : vérifier les informations avant de les présenter comme des faits.

- Limitation de conservation : ne pas garder indéfiniment des notes ou données qui ne sont plus nécessaires.

- Confidentialité : protéger les notes, captures et documents recueillis, surtout s’ils contiennent des données personnelles.

- Proportionnalité : réduire l’intrusion et l’exposition des personnes au niveau nécessaire pour atteindre l’objectif légitime.

- Traçabilité : garder une piste de vérification, sans publier les données sensibles ni les détails qui faciliteraient un abus.

## 9.2 Données personnelles publiques

La Chambre Contentieuse de l’Autorité de protection des données belge a rappelé dans une décision de 2022 que le caractère public de données personnelles ne les fait pas perdre leur statut de données personnelles et que leur traitement reste soumis aux règles applicables, notamment à l’exigence d’une base juridique. Cette décision porte sur un cas concret ; elle ne remplace pas l’analyse juridique d’un autre projet. Elle constitue toutefois un rappel utile : « visible sur le Web » ne signifie pas « libre à collecter et republier sans limite ».

## 9.3 Règle d’arrêt

Si une recherche semble mener à des mots de passe, jetons d’accès, données médicales, données financières, documents personnels ou espaces qui paraissent privés, arrêter la consultation et la collecte. Ne pas tester, utiliser, partager ou archiver le contenu. Noter seulement le minimum nécessaire pour signaler le constat au responsable autorisé, selon la procédure de l’organisation.

## 9.4 Règles de classe

- Utiliser les domaines et jeux de données de démonstration fournis par l’enseignant.

- Ne pas viser une personne réelle, une entreprise réelle ou un système sans autorisation explicite.

- Ne pas chercher, télécharger, conserver ou divulguer des secrets ou des dossiers personnels.

- Ne pas automatiser des requêtes ni contourner les protections ou limites d’un service.

- Citer la source, la date et le contexte ; masquer les données personnelles inutiles dans les copies de travail.

- En cas de découverte sensible accidentelle, arrêter et prévenir l’enseignant.

# 10. Ateliers pratiques

Les ateliers privilégient le raisonnement et la reproductibilité. Les étudiants peuvent obtenir des résultats différents en raison de l’évolution de l’index ; l’évaluation porte donc sur la qualité de la formulation, la vérification et l’explication des limites, pas sur l’obtention d’une URL identique à celle d’un corrigé.

## Atelier 1 Comprendre l’effet des opérateurs

Durée : 25 minutes. Objectif : observer comment un filtre modifie une requête. Utiliser un sujet neutre choisi en classe, par exemple la documentation de sécurité d’un standard public.

> **1.** Lancer une recherche large avec deux ou trois termes.
>
> **2.** Ajouter des guillemets à une expression importante.
>
> **3.** Ajouter site: à un domaine institutionnel choisi par l’enseignant.
>
> **4.** Ajouter filetype:pdf, puis comparer avec l’interface de recherche avancée.
>
> **5.** Consigner ce qui a changé et ce que la comparaison ne permet pas de conclure.

## Atelier 2 Construire une requête de veille

Durée : 35 minutes. Scénario : préparer une veille sur la journalisation des événements Windows et les recommandations officielles, sans rechercher des vulnérabilités exploitables.

> "Windows event logging" security guidance
>
> site:learn.microsoft.com Windows event logging security
>
> site:cisa.gov Windows logging guidance filetype:pdf

Livrable : trois requêtes, une justification pour chacune, deux sources vérifiées, date de consultation et une limite. Les étudiants doivent expliquer pourquoi un résultat Microsoft et un résultat CISA ne sont pas nécessairement indépendants.

## Atelier 3 Tester une syntaxe non documentée

Durée : 30 minutes. Scénario : déterminer si intitle: semble filtrer les résultats pour une recherche pédagogique neutre. Aucun sujet personnel ou sensible.

> **1.** Lancer la requête de base sans opérateur.
>
> **2.** Ajouter intitle: devant un terme qui devrait figurer dans un titre.
>
> **3.** Comparer plusieurs titres et URL réellement ouverts.
>
> **4.** Répéter avec une reformulation ordinaire.
>
> **5.** Rédiger une conclusion prudente : observé, non observé, ou indéterminé.

## Atelier 4 Vérifier une affirmation

Durée : 45 minutes. L’enseignant fournit une affirmation publique neutre et datée, par exemple « la version X d’un standard a été publiée en année Y ». Les étudiants cherchent la source primaire, puis une confirmation indépendante.

Questions de restitution : quelle page fait l’annonce originale ? La date est-elle une date de publication ou de mise à jour ? La seconde source a-t-elle consulté l’original ou recopié un communiqué ? Quelle incertitude subsiste ?

## Atelier 5 Recherche d’un document public

Durée : 35 minutes. Scénario : trouver une politique de confidentialité ou un rapport de durabilité sur le site de démonstration attribué par l’enseignant. Si le domaine choisi ne publie pas de document correspondant, les étudiants doivent expliquer l’échec et ajuster les termes plutôt que cibler un autre domaine sans rapport.

> site:example.org filetype:pdf privacy policy
>
> site:example.org "privacy policy"

Le domaine example.org sert ici de modèle de syntaxe. L’enseignant peut remplacer cet exemple par une ressource explicitement sélectionnée, publique et appropriée au cours.

## Atelier 6 Corréler plusieurs sources sans profiler une personne

Durée : 45 minutes. Scénario : suivre l’évolution publique d’une norme ou d’un organisme, et non d’une personne. Construire une chronologie à partir de trois publications institutionnelles et noter si elles sont réellement indépendantes.

## Atelier 7 Audit défensif simulé

Durée : 60 minutes. Scénario : l’équipe de classe reçoit un domaine fictif et un mandat écrit limité à la découverte passive de pages et documents déjà publics. Les requêtes ne doivent pas viser des secrets, des mots de passe ou des données personnelles. Toute découverte inattendue déclenche la règle d’arrêt.

Livrable : périmètre, requêtes, deux constats de démonstration, sources, niveau de confiance, limites et recommandations de suivi par le propriétaire du domaine. Le résultat attendu est une note de méthode, pas une tentative d’accès.

## Atelier 8 Savoir s’arrêter et changer d’outil

Durée : 30 minutes. L’enseignant donne trois besoins : suivre une page dans le temps, trouver un article académique, vérifier l’inventaire d’un site dont l’étudiant est administrateur. Pour chacun, les étudiants décident si Google suffit, s’il faut consulter une source spécialisée, ou s’il faut utiliser un outil interne autorisé.

# 11. Corrigés et grille d’évaluation

## 11.1 Corrigé type de l’atelier 1

Les guillemets tendent à rendre la recherche plus précise autour de l’expression choisie. site: limite la recherche au domaine déclaré, mais ne montre pas forcément toutes les pages indexées de ce domaine. filetype:pdf réduit les résultats aux documents reconnus comme PDF ou associés à l’extension. Le filtre d’interface peut fournir un résultat similaire, mais les options visibles dépendent de la requête. Une différence de résultats est une observation, pas une preuve que l’un des mécanismes est exhaustif.

## 11.2 Corrigé type de l’atelier 2

La première requête explore l’expression anglaise. La deuxième cible une documentation Microsoft. La troisième cherche une recommandation CISA en PDF. Pour rendre le travail plus solide, les étudiants peuvent ensuite chercher séparément les variantes « event logging », « audit policy » ou « Windows logging ». Les deux sources sont institutionnelles mais elles ne sont pas nécessairement indépendantes : vérifier si l’une cite l’autre.

## 11.3 Corrigé type de l’atelier 3

La conclusion acceptable dépend de ce que l’étudiant a réellement observé à la date du test. Il doit écrire par exemple : « Dans les requêtes testées le 24/10/2026, plusieurs titres contenaient le terme ciblé ; cela ne démontre pas que Google garantit le filtre intitle: pour toutes les recherches. » Une conclusion incorrecte serait : « intitle: est toujours fiable car il a fonctionné une fois. »

## 11.4 Corrigé type de l’atelier 4

La bonne démarche identifie une source primaire, vérifie la date sur la page elle-même, recherche une seconde source réellement distincte et signale les écarts de vocabulaire ou de calendrier. Il faut distinguer la date d’annonce, la date d’entrée en vigueur, la date de mise à jour et la date de publication d’un résumé secondaire.

## 11.5 Grille de notation proposée

| **Critère**                | **Points** | **Indicateur de réussite**                                            |
|----------------------------|------------|-----------------------------------------------------------------------|
| Question et périmètre      | 15         | Question précise, périmètre et période explicites.                    |
| Construction des requêtes  | 20         | Opérateurs justifiés, variantes utiles, syntaxe expliquée.            |
| Vérification des résultats | 25         | Pages ouvertes, source primaire repérée, recoupement indépendant.     |
| Limites et incertitudes    | 15         | Distingue absence de résultat, absence de preuve et conclusion.       |
| Cadre responsable          | 15         | Minimise les données, respecte le mandat et sait arrêter la collecte. |
| Traçabilité et restitution | 10         | Journal compréhensible et résultat reproductible.                     |

Une réponse qui expose ou conserve des données sensibles sans nécessité ne peut pas obtenir la validation de l’atelier, même si la requête est techniquement bien construite. La capacité à arrêter une recherche et à signaler proprement un risque fait partie des compétences évaluées.

# 12. Fiches de référence et sources

## 12.1 Fiche de construction de requête

> \[sujet et variantes\] \["expression utile"\] \[site:domaine\] \[filetype:pdf\] \[after:AAAA-MM-JJ before:AAAA-MM-JJ\] \[-terme parasite\]

N’utiliser que les éléments utiles. Enlever un filtre qui retire trop de résultats. Tester une nouvelle variante plutôt que d’empiler tous les opérateurs disponibles.

## 12.2 Fiche de vérification rapide

- Ai-je ouvert la page, et non seulement lu l’extrait du moteur ?

- La page source répond-elle directement à la question ?

- Qui est l’auteur et quelle est sa proximité avec les faits ?

- La date correspond-elle au fait que je cherche ?

- Existe-t-il une source indépendante ?

- Qu’est-ce que la recherche ne permet pas de conclure ?

- Ai-je une raison et une autorisation pour conserver ces informations ?

## 12.3 Glossaire

| **Terme**           | **Définition**                                                                                                                |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Index               | Base organisée de ressources qu’un moteur a découvertes et peut présenter en réponse à des requêtes.                          |
| Opérateur           | Commande ou syntaxe qui cherche à préciser une requête.                                                                       |
| OSINT               | Démarche de renseignement à partir de sources ouvertes, comprenant collecte, vérification et analyse.                         |
| Source primaire     | Source directement liée au fait étudié : publication originale, registre, document ou déclaration.                            |
| Corroboration       | Confirmation d’un élément par une autre source ou méthode.                                                                    |
| Dorking             | Usage de requêtes structurées pour cibler des contenus indexés.                                                               |
| Exposition publique | Information consultable sans authentification, ce qui ne signifie pas qu’elle peut être exploitée ou réutilisée sans limites. |
| Faux positif        | Résultat qui semble correspondre à la recherche mais ne confirme pas réellement l’hypothèse.                                  |
| Faux négatif        | Recherche qui ne renvoie pas un élément pourtant existant ou pertinent.                                                       |
| Reproductibilité    | Possibilité pour une autre personne de comprendre et répéter la méthode à partir des notes.                                   |

## 12.4 Sources officielles et références

Les pages d’aide et la documentation produit changent. Vérifier ces références avant chaque nouvelle édition du cours. Date de consultation de cette édition : 24 octobre 2026.

**Google Search Help, Affiner les recherches Google**

> https://support.google.com/websearch/answer/2466433?hl=fr-CA
>
> Guillemets, site:, exclusions, before:, after:, filetype: et filtres de recherche.

**Google Search Central, Présentation des opérateurs de recherche Google**

> https://developers.google.com/search/docs/monitor-debug/search-operators?hl=fr
>
> site:, filetype:, imagesize:, src: et limites d’indexation/récupération.

**Google Search Central, mises à jour de la documentation**

> https://developers.google.com/search/updates
>
> Suivre les changements ; la documentation consultée signale le retrait de cache: en septembre 2026.

**DuckDuckGo Help, syntaxe avancée**

> https://duckduckgo.com/duckduckgo-help-pages/results/syntax
>
> Exemple de syntaxe propre à un autre moteur et réserve de fonctionnement.

**Règlement (UE) 2016/679, texte français sur EUR-Lex**

> https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32016R0679
>
> Texte juridique primaire du RGPD ; consulter les articles et considérants pertinents.

**Autorité de protection des données belge, décision 13/2022**

> https://www.autoriteprotectiondonnees.be/publications/decision-quant-au-fond-n-13-2022.pdf
>
> Illustration d’une décision concrète sur des données publiquement accessibles et leur traitement.

**Google Search Console, inspection d’URL**

> https://support.google.com/webmasters/answer/9012289?hl=fr
>
> Outil propriétaire pour vérifier l’indexation d’une URL sur un site administré.

Fin du support. Les étudiants doivent être capables d’expliquer la requête utilisée, les pages qu’ils ont vérifiées, la solidité de leurs sources et les limites de leur conclusion. La maîtrise des opérateurs aide à chercher ; le jugement et la méthode déterminent ce que l’on peut raisonnablement affirmer.
