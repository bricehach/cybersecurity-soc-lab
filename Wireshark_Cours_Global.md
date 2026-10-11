# Wireshark — cours global de l’interface à l’analyse SOC/DFIR

**Version de travail : 0.6 — cours en construction**  
**Public :** étudiant IFAPME, SOC niveau 2, technicien ou analyste réseau en progression  
**Environnements visés :** Windows, Kali Linux et Parrot Security  
**Statut :** cours en construction ; version 0.6 validée pour publication comme document de travail

> Les explications commencent volontairement avec des mots simples. Les termes techniques sont ensuite définis précisément. L’objectif n’est pas de mémoriser des commandes sans les comprendre, mais de savoir poser une question, trouver les paquets utiles, les interpréter et expliquer les limites de la conclusion.

## Comment lire ce cours

Chaque notion difficile suivra autant que possible quatre niveaux :

1. **Image simple** : explication accessible à un enfant de 10 ans.
2. **Définition technique** : vocabulaire exact et fonctionnement.
3. **Lecture dans Wireshark** : où regarder et quoi comparer.
4. **Limites et erreurs fréquentes** : ce qu’une capture ne permet pas d’affirmer.

Les exemples devront être réalisés sur un réseau personnel, un laboratoire autorisé ou des fichiers PCAP prévus pour l’apprentissage. Une capture peut contenir des données personnelles, des identifiants ou des informations confidentielles : elle se traite comme une pièce sensible.

## Table des matières prévue

### Partie I — Comprendre avant de capturer

1. Wireshark : rôle, capacités et limites
2. Réseau, trames, paquets, segments et couches
3. Ethernet, adresses MAC, ARP et VLAN
4. IPv4, IPv6, ICMP et routage
5. TCP, UDP, ports et conversations
6. DNS, DHCP, TLS, HTTP(S), SMB, SSH et protocoles utiles au SOC
7. Ce que le chiffrement montre et ce qu’il masque

### Partie II — Installation et préparation

8. Installer Wireshark sous Windows et vérifier Npcap
9. Installer Wireshark sous Kali Linux
10. Installer Wireshark sous Parrot Security
11. Permissions, privilèges et capture sans exécuter toute l’interface en administrateur/root
12. Interfaces réseau, Wi-Fi, Ethernet, VPN, machines virtuelles et adaptateurs virtuels
13. Vérifier une installation, diagnostiquer l’absence d’interface ou de paquets
14. Préparer un laboratoire sûr et gérer les fichiers de capture

### Partie III — Tour complet de l’interface

15. Écran d’accueil, liste des interfaces et activité réseau
16. Menu File / Fichier : ouvrir, importer, exporter, enregistrer et fermer
17. Menu Edit / Édition : rechercher, copier, marquer, ignorer et références temporelles
18. Menu View / Affichage : panneaux, horodatages, résolution des noms et couleurs
19. Menu Go / Aller : navigation dans les paquets, flux et historique
20. Méthode pour se repérer dans les menus
21. Menu Capture : options, filtres, interfaces et enregistrement
22. Menu Analyze / Analyse : filtres, dissectors, Decode As, Follow et Expert Info
23. Menu Statistics / Statistiques : protocoles, conversations, endpoints et graphiques
24. Menu Telephony / Téléphonie : VoIP, RTP et protocoles spécialisés
25. Menu Wireless / Sans fil : WLAN et Bluetooth
26. Menu Tools / Outils : ACL, identifiants, MAC, TLS et Lua
27. Menu Help / Aide : guides, manuels, versions et composants
28. Bonnes pratiques pour utiliser les fonctions spécialisées
29. Barre d’outils principale
30. Barre de filtre d’affichage et filtres enregistrés
31. Panneaux : liste des paquets, détails, octets et diagramme
32. Barre d’état et compteurs
33. Menus contextuels des colonnes, paquets, détails, octets et diagramme
34. Préférences et réglages utiles
35. Profils de configuration

> Les libellés et sous-menus peuvent changer selon la version, le système, les plugins et les fonctionnalités compilées. Le cours donnera le nom anglais rencontré dans l’interface ainsi que sa traduction française lorsque celle-ci existe.

### Partie IV — Capturer proprement

36. Choisir la bonne interface et comprendre les modes de capture
37. Capture filter : filtrer avant l’enregistrement
38. Capture options : durée, taille, fichiers circulaires, commentaires et buffer
39. Point de capture : poste, serveur, port miroir, TAP, hyperviseur ou routeur
40. Wi-Fi : limites du mode moniteur, chiffrement et matériel requis
41. Captures sur plusieurs interfaces et synchronisation temporelle
42. Pourquoi une capture peut être incomplète ou trompeuse

### Partie V — Lire et filtrer

43. Display filter : filtrer l’affichage sans supprimer les données du fichier
44. Syntaxe des filtres d’affichage : champs, comparaisons, logique et présence
45. Filtres de capture et filtres d’affichage : différences essentielles
46. Rechercher du texte, des octets, des champs et des motifs
47. Colonnes, profils, couleurs, bookmarks et commentaires
48. Follow Stream : reconstruire une conversation et éviter les conclusions hâtives
49. Exporter des objets et extraire des éléments utiles avec précaution

### Partie VI — Analyse réseau et dépannage

50. Reconstituer une connexion TCP : SYN, SYN/ACK, ACK, données et fermeture
51. Retransmissions, pertes, latence, fenêtres et resets
52. Résoudre DNS et DHCP à partir des échanges observés
53. Diagnostiquer une connexion web et comprendre TLS
54. Comparer deux captures avant/après un changement
55. MTU, fragmentation, checksum offload et autres artefacts de capture
56. Lire une anomalie sans confondre symptôme, cause et preuve

### Partie VII — Wireshark pour le SOC et la DFIR

57. Méthode de triage d’un PCAP inconnu
58. Questions SOC : hôte, heure, destination, protocole, volume et périodicité
59. Repérer un scan, un beaconing possible, un transfert inhabituel ou une résolution DNS suspecte
60. Indicateurs réseau : IP, domaine, certificat, URI, User-Agent et empreintes disponibles
61. Corrélation avec journaux Windows, Sysmon, pare-feu, proxy, DNS et SIEM
62. Préserver la preuve, horodatage, intégrité, notes et reproductibilité
63. Faux positifs, visibilité partielle et limites d’attribution
64. PCAP malveillant : précautions d’ouverture et d’extraction

### Partie VIII — Fonctions avancées et automatisation

65. Profiles, preferences, name resolution et protocol dissectors
66. Decode As, protocol preferences et réassemblage
67. Expert Information : avertissements, erreurs et sévérité
68. Tshark : capturer, filtrer, exporter et automatiser en ligne de commande
69. Statistics et I/O Graphs pour mesurer les tendances
70. Formats de capture, conversion, fusion et découpage
71. Extensibilité, plugins, Lua et limites de maintenance
72. Performance, gros fichiers, ring buffers et captures longues

### Partie IX — Méthode, exercices et références

73. Méthode reproductible d’analyse en 10 étapes
74. Cas guidés : panne DNS, TCP qui échoue, lenteur web, DHCP incorrect
75. Cas SOC : scan de ports, DNS inhabituel, transfert volumineux, beaconing simulé
76. Modèle de compte rendu d’analyse PCAP
77. Glossaire, mémo de filtres, raccourcis et arbre de dépannage
78. Vérification des connaissances et corrigés séparés
79. Sources officielles, licence, version du cours et procédure de mise à jour

## 1. Wireshark : rôle, capacités et limites

### 1.1 L’image simple

Imagine une route où circulent des camionnettes. Chaque camionnette transporte une enveloppe. Wireshark est comme une caméra placée à un endroit précis de la route : il peut noter les camionnettes qui passent, leur direction, leur taille et certaines étiquettes visibles. Si l’enveloppe est fermée par un cadenas, la caméra ne peut pas lire son contenu, mais elle peut souvent voir qui communique, quand, avec quelle fréquence et quelle quantité de données.

Cette image a une limite : Wireshark ne voit que le trafic qui passe réellement devant son point d’observation. Une caméra sur une route ne voit pas automatiquement les véhicules qui circulent dans une autre rue.

### 1.2 Définition technique

Wireshark est un analyseur de protocoles réseau. Il peut notamment :

- capturer des trames depuis une interface réseau accessible ;
- ouvrir et décoder des fichiers de capture existants ;
- présenter les protocoles reconnus sous forme de champs ;
- filtrer les paquets visibles selon des critères ;
- rechercher des conversations et suivre certains flux ;
- produire des statistiques et exporter certaines données.

Wireshark n’est pas, à lui seul, un pare-feu, un système de détection complet, un scanner de vulnérabilités ni un outil magique qui explique automatiquement toute panne. Il aide l’analyste à observer et à formuler des hypothèses vérifiables.

### 1.3 Le trajet d’un paquet dans Wireshark

Lors d’une capture en direct, le chemin simplifié est le suivant :

1. Une application produit ou reçoit des données.
2. Le système d’exploitation les transforme en trafic réseau.
3. Une interface réseau transmet ou reçoit les trames.
4. Le mécanisme de capture du système remet une copie à Wireshark.
5. Wireshark décode les octets qu’il reconnaît et les affiche.

Wireshark observe généralement une copie du trafic ; il ne modifie pas les paquets simplement parce qu’il les affiche. Des fonctions comme l’injection ou la génération active de trafic relèvent d’autres outils ou de fonctions distinctes et ne font pas partie d’une analyse passive ordinaire.

### 1.4 Trois vues d’un même paquet

Un paquet sélectionné apparaît généralement dans trois zones :

- **Liste des paquets** : vue rapide, une ligne par paquet, avec des colonnes comme l’heure, la source, la destination, le protocole, la longueur et une information résumée.
- **Détails du paquet** : arbre des protocoles et des champs. On peut développer Ethernet, IP, TCP, DNS, HTTP, TLS ou d’autres protocoles détectés.
- **Octets du paquet** : représentation brute en hexadécimal et, lorsque c’est possible, en caractères lisibles.

Image simple : la liste est la couverture du livre, les détails sont les chapitres, et les octets sont les lettres réellement imprimées sur les pages.

### 1.5 Ce que Wireshark peut prouver — et ce qu’il ne prouve pas seul

Une capture peut montrer qu’à un point d’observation donné, des paquets ont été vus avec certaines adresses, certains champs et certains horaires. Elle peut aider à démontrer qu’une requête DNS a été émise, qu’une connexion TCP a commencé ou qu’un hôte a envoyé un volume de données.

Une capture seule ne prouve pas nécessairement :

- l’identité réelle de la personne derrière une adresse IP ;
- que l’absence d’un paquet signifie qu’il n’a jamais existé ;
- que l’hôte visible est l’origine ultime du trafic ;
- le contenu en clair d’une session correctement chiffrée ;
- que chaque avertissement d’expertise est une attaque ;
- la cause exacte d’une panne sans examiner le point de capture, la configuration et les autres journaux.

La règle professionnelle est de distinguer **observation**, **interprétation** et **hypothèse**. Exemple : « Wireshark montre trois retransmissions TCP » est une observation. « Le réseau est congestionné » est une hypothèse à vérifier avec d’autres données.

### 1.6 Les deux filtres à ne jamais confondre

Wireshark possède deux familles de filtres :

- Le **capture filter** agit avant ou pendant l’enregistrement : il décide quels paquets sont conservés dans la capture.
- Le **display filter** agit après la capture : il masque temporairement de l’affichage les paquets qui ne correspondent pas, sans les supprimer du fichier.

Image simple : le filtre de capture ressemble au videur qui décide qui peut entrer dans la salle ; le filtre d’affichage ressemble à un projecteur qui éclaire seulement certaines personnes déjà dans la salle.

C’est une distinction fondamentale. Un filtre de capture trop strict peut faire perdre des éléments utiles. Pour apprendre, il est souvent plus prudent de capturer avec un périmètre maîtrisé, puis de trier avec un filtre d’affichage.

### 1.7 Vocabulaire de départ

| Terme | Explication simple | Sens technique |
|---|---|---|
| Paquet | Un morceau d’un échange réseau | Unité de données affichée ou décodée par l’analyseur ; selon la couche, on parle aussi de trame, datagramme ou segment |
| Trame | L’enveloppe utilisée sur le réseau local | Unité de couche liaison, par exemple Ethernet ou IEEE 802.11 |
| Capture / PCAP | L’enregistrement des échanges observés | Fichier de paquets, souvent `.pcap` ou `.pcapng` |
| Interface | La porte réseau de la machine | Adaptateur Ethernet, Wi-Fi, VPN, loopback ou interface virtuelle |
| Protocole | Les règles d’une conversation | Format et comportement définis pour échanger des données |
| Flux | Une conversation suivie dans le temps | Paquets associés à une communication, souvent identifiée par les adresses, ports et protocole |
| Dissector | Le décodeur | Composant qui interprète les octets selon un protocole |

### 1.8 Première méthode d’analyse

Avant de cliquer partout, pose ces questions :

1. **Pourquoi est-ce que j’analyse cette capture ?** Dépannage, apprentissage, incident SOC ou validation d’un changement ?
2. **Où la capture a-t-elle été prise ?** Sur le poste client, le serveur, un port miroir, une VM ou un équipement réseau ?
3. **Quand a-t-elle été prise et quelle est sa durée ?** L’heure du poste et son fuseau sont-ils fiables ?
4. **La capture est-elle complète ?** Certains paquets ont-ils été perdus, filtrés ou capturés après le début de la communication ?
5. **Qu’est-ce que j’observe exactement ?** Séparer les faits visibles des explications possibles.
6. **Quelles données supplémentaires peuvent confirmer l’analyse ?** Journaux système, pare-feu, DNS, proxy, SIEM ou capture à un autre point.

Cette méthode évite la conclusion trop rapide : « j’ai vu un paquet bizarre, donc j’ai trouvé une attaque ».

## Pistes à ne pas oublier dans la version finale

- Distinguer les versions et traductions de l’interface, avec captures d’écran légendées lorsqu’elles seront disponibles.
- Ajouter une matrice « fonctionnalité / menu / utilité SOC / limite / exemple ».
- Créer un mémo séparé pour les filtres de capture et les filtres d’affichage, car leurs syntaxes diffèrent.
- Décrire les limites propres au Wi-Fi, aux commutateurs, aux VPN, aux hyperviseurs et aux captures côté hôte.
- Ajouter les bonnes pratiques de confidentialité et d’assainissement avant de publier un PCAP sur GitHub.
- Prévoir une vérification périodique des chemins d’installation, versions, noms de menus et champs de filtres à partir de la documentation officielle Wireshark.

## Sources de référence à maintenir

- Documentation officielle Wireshark : https://www.wireshark.org/docs/
- Guide utilisateur officiel : https://www.wireshark.org/docs/wsug_html_chunked/
- Référence des filtres d’affichage : https://www.wireshark.org/docs/dfref/
- Téléchargements officiels : https://www.wireshark.org/download.html


# Partie II — Installation et préparation

## 8. Installer Wireshark sous Windows

### 8.1 Avant l’installation

Télécharge l’installateur depuis le site officiel Wireshark. Évite les sites de téléchargement tiers : ils peuvent proposer une version ancienne, repaquetée ou non vérifiable. Le nom du fichier et les versions disponibles changent ; le cours ne fige donc pas un numéro de version. Vérifie l’éditeur/signature numérique de l’installateur avant de l’exécuter.

### 8.2 Étapes d’installation

1. Lance l’installateur officiel avec un compte autorisé à installer des logiciels.
2. Garde les composants principaux **Wireshark** et, sauf besoin contraire, **TShark**. TShark est la version en ligne de commande et sera étudiée plus loin.
3. Installe **Npcap** lorsque l’assistant le propose. Npcap fournit la capture des paquets en direct sous Windows. Sans ce composant, Wireshark peut toujours ouvrir des fichiers PCAP existants, mais la capture en direct peut ne pas fonctionner.
4. Les composants *extcap* sont des interfaces de capture externes. Ils ne sont pas nécessaires pour commencer ; certains ajoutent des sources spécialisées ou distantes.
5. Termine l’installation, puis redémarre si l’installateur ou Npcap le demande.

### 8.3 Vérifier que l’installation fonctionne

1. Ouvre Wireshark depuis le menu Démarrer.
2. Sur l’écran d’accueil, vérifie que les interfaces attendues apparaissent : Ethernet, Wi-Fi, loopback, VPN ou interfaces virtuelles selon la machine.
3. Observe l’activité affichée à côté d’une interface. Une ligne qui bouge indique qu’il y a probablement du trafic ; elle ne prouve pas à elle seule que la capture est correctement configurée.
4. Lance une capture courte sur une interface que tu contrôles, visite une page de test ou effectue une résolution DNS, puis arrête la capture.
5. Vérifie que des paquets apparaissent et que le fichier peut être enregistré puis rouvert.

### 8.4 Pannes classiques sous Windows

| Symptôme | Vérifications à faire |
|---|---|
| Aucune interface de capture | Vérifier l’installation et l’état de Npcap, redémarrer si nécessaire, relancer Wireshark, puis vérifier si l’interface est activée dans Windows |
| Interface visible, mais capture impossible | Vérifier les droits, le pilote Npcap et le message d’erreur exact ; tester une interface physique différente |
| Aucun paquet pendant la capture | Confirmer que la bonne interface a été choisie, générer un trafic identifiable, vérifier le filtre de capture et la topologie du réseau |
| Wi-Fi : trafic d’autres appareils absent | C’est généralement normal sur un réseau commuté ; la carte Wi-Fi en mode normal ne reçoit pas automatiquement le trafic unicast destiné aux autres appareils |
| VPN ou VM : trafic incomplet | Capturer sur l’interface logique ou virtuelle adaptée et comparer avec l’interface physique |

## 9. Installer Wireshark sous Kali Linux et Parrot Security

Kali et Parrot sont des distributions fondées sur Debian. La voie habituelle consiste à utiliser les dépôts de la distribution et APT, plutôt qu’à télécharger manuellement un paquet depuis un site tiers.

### 9.1 Installation

Dans un terminal :

```bash
sudo apt update
sudo apt install wireshark
```

L’assistant de paquet peut demander si les utilisateurs non privilégiés peuvent capturer des paquets. Cette question concerne la permission accordée au composant de capture, **pas** le droit de lire un fichier PCAP déjà enregistré.

### 9.2 Comprendre le choix de permission

Le mécanisme Debian documenté par le projet Wireshark distingue deux situations :

- **Réponse Non** : l’utilisateur ordinaire ne capture pas directement. On peut utiliser un mécanisme autorisé pour capturer, puis ouvrir le fichier avec Wireshark lancé normalement.
- **Réponse Oui** : la capture peut être autorisée aux membres du groupe système `wireshark`. L’utilisateur n’est pas nécessairement ajouté automatiquement à ce groupe.

Accorder la capture à un compte augmente ses capacités sur les interfaces réseau accessibles. Dans un ordinateur partagé ou professionnel, il faut suivre la politique de l’administrateur. Dans un laboratoire personnel, on peut choisir cette option en comprenant cette portée.

Si tu dois modifier ce choix après l’installation, le paquet Debian documente l’assistant `dpkg-reconfigure wireshark-common` et les étapes de groupe. Lis aussi la documentation installée par le paquet avant de changer les droits :

```bash
zcat /usr/share/doc/wireshark-common/README.Debian.gz | less
```

Si le fichier n’existe pas sous ce nom, liste le dossier `/usr/share/doc/wireshark-common/` : certains paquets installent le texte sans compression.

### 9.3 Ajouter un compte au groupe de capture — uniquement si le choix Oui a été configuré

Vérifie d’abord que le groupe existe :

```bash
getent group wireshark
```

Puis, si tu as décidé d’accorder cette permission à ton compte :

```bash
sudo usermod -aG wireshark "$USER"
```

Ferme la session Linux et reconnecte-toi, ou redémarre la machine. Une simple fermeture de la fenêtre Wireshark ne suffit pas à renouveler les groupes de la session. Vérifie ensuite :

```bash
id -nG
```

Le nom `wireshark` doit apparaître. Vérifie ensuite les interfaces visibles dans Wireshark et teste une courte capture autorisée.

> Ne lance pas durablement l’interface graphique entière avec `sudo wireshark`. La séparation des privilèges permet de réserver les droits élevés au mécanisme de capture et de garder l’analyse graphique sous un compte normal. N’utilise pas `chmod 777`, ne rends pas `dumpcap` accessible à tout le monde et ne modifie pas manuellement les capabilities sans une procédure contrôlée.

### 9.4 Vérifier la version et les composants

Dans le terminal :

```bash
wireshark --version
tshark --version
dumpcap -D
```

- `wireshark --version` confirme que la commande graphique est installée.
- `tshark --version` confirme la présence de l’outil en ligne de commande.
- `dumpcap -D` énumère les interfaces disponibles au mécanisme de capture. Si la commande signale un refus, le problème porte probablement sur les permissions ou le composant de capture.

Les numéros de version peuvent différer entre dépôts Kali, Parrot et le site officiel. Pour un cours reproductible, note dans ton compte rendu la distribution, sa version, la version de Wireshark et la date de vérification.

## 10. Choisir la bonne interface réseau

### 10.1 L’image simple

Une interface réseau est une porte. Un ordinateur peut avoir plusieurs portes : un câble Ethernet, une carte Wi-Fi, un tunnel VPN et des portes virtuelles créées par VMware ou VirtualBox. Si tu places l’enregistreur devant la mauvaise porte, tu verras peu de choses ou rien du tout.

### 10.2 Interfaces courantes

| Interface | Ce qu’elle peut montrer | Point de vigilance |
|---|---|---|
| Ethernet physique | Trafic envoyé et reçu par le poste sur le câble | En réseau commuté, ne donne pas automatiquement le trafic des autres postes |
| Wi-Fi physique | Trafic du poste associé au point d’accès | Le mode normal n’équivaut pas à une capture radio complète en mode moniteur |
| Loopback | Communications internes à la machine | Le nom et le comportement diffèrent selon le système |
| VPN | Trafic avant ou après encapsulation selon l’interface choisie | Comparer l’interface VPN à l’interface physique pour voir la différence |
| Adaptateur de VM | Trafic vu par une machine virtuelle ou un réseau virtuel | Le mode NAT, bridge ou host-only change ce qui est visible |
| Interface Bluetooth/USB spécialisée | Échanges spécifiques si le matériel, le pilote et le support sont présents | Peut nécessiter des composants supplémentaires et ne constitue pas une interface Ethernet classique |

### 10.3 Procédure pour choisir

1. Note l’objectif : analyser le trafic de ton poste, d’une VM ou d’un réseau de laboratoire.
2. Génère un trafic simple et reconnaissable, par exemple une résolution DNS contrôlée.
3. Regarde quelles interfaces montrent de l’activité au même moment.
4. Capture brièvement sur une interface candidate et vérifie les adresses source/destination attendues.
5. Si tu ne vois pas l’échange, change de point d’observation avant de conclure que le trafic n’existe pas.

## 11. Capturer dans une machine virtuelle

La carte virtuelle n’est pas un miroir magique de tout le réseau. Son comportement dépend du mode configuré dans l’hyperviseur :

- **NAT** : la VM partage généralement la sortie réseau de l’hôte ; la capture dans la VM voit surtout son propre trafic.
- **Bridged / accès par pont** : la VM apparaît davantage comme un équipement du réseau, mais le comportement de capture dépend du pilote, du Wi-Fi et de l’hyperviseur.
- **Host-only / réseau privé hôte** : la VM communique dans un segment isolé ou limité ; c’est pratique pour un laboratoire fermé.
- **Réseau interne** : seuls les équipements attachés à ce réseau virtuel peuvent communiquer entre eux.

Pour une analyse défensive, capture d’abord dans la VM qui génère ou reçoit le trafic. Pour observer plusieurs systèmes, configure explicitement un port miroir, un TAP, une interface virtuelle de surveillance ou une capture sur un équipement adapté. Vérifie toujours ce que le point choisi peut réellement voir.

## 12. Sécurité, confidentialité et gestion des PCAP

Un PCAP peut conserver des noms d’hôtes, des adresses internes, des cookies, des requêtes DNS, des métadonnées de connexion et parfois des données en clair. Avant de partager un fichier, demande-toi :

- Ai-je l’autorisation de capturer ce trafic ?
- Le fichier contient-il des identifiants, des données personnelles ou des informations d’entreprise ?
- Puis-je remplacer l’exemple par une capture synthétique ou un fichier public prévu pour l’apprentissage ?
- Si je dois partager un extrait, puis-je le réduire, l’anonymiser et vérifier le résultat ?
- Le dépôt GitHub sera-t-il public ? Ai-je inspecté l’intégralité du PCAP et son historique Git ?

Ne publie jamais une capture réelle de réseau professionnel ou familial sans autorisation et contrôle des données. Supprimer un fichier dans le dernier commit ne suffit pas nécessairement à l’effacer de l’historique du dépôt.

## 13. Liste de contrôle après installation

- [ ] Version de l’OS et date notées.
- [ ] Wireshark installé depuis une source officielle ou le dépôt de la distribution.
- [ ] Npcap vérifié sous Windows ; mécanisme `dumpcap` vérifié sous Linux.
- [ ] Capture lancée sans exécuter inutilement toute l’interface graphique en administrateur/root.
- [ ] Bonne interface identifiée par un test simple.
- [ ] Fichier de test enregistré, fermé et rouvert.
- [ ] Emplacement de stockage protégé et nom de fichier compréhensible.
- [ ] Aucun PCAP sensible destiné à un dépôt public.

## Références officielles pour cette partie

- Installation Windows et Npcap : https://www.wireshark.org/docs/wsug_html_chunked/ChBuildInstallWinInstall.html
- Installation Linux et permissions de capture : https://www.wireshark.org/docs/wsug_html_chunked/ChBuildInstallUnixInstallBins.html
- Note Debian sur `dumpcap` et le groupe `wireshark` : https://gitlab.com/wireshark/wireshark/-/blob/master/packaging/debian/README.Debian
- Prérequis de capture : https://www.wireshark.org/docs/wsug_html_chunked/ChCapPrerequisitesSection
- Documentation de gestion des interfaces : https://www.wireshark.org/docs/wsug_html_chunked/ChCapManageInterfacesSection.html

# Partie III — Prendre ses repères dans l’interface

## 15. Écran d’accueil et fenêtre principale

### 15.1 Écran d’accueil

Au démarrage, Wireshark peut proposer une liste d’interfaces réseau et des fichiers récemment ouverts. L’écran exact dépend de la version, du système et des options choisies. Les interfaces qui bougent sont celles sur lesquelles l’ordinateur observe probablement du trafic ; elles ne sont pas forcément celles qu’il faut capturer.

Avant de démarrer, réponds à trois questions :

- Est-ce que j’ouvre un fichier déjà enregistré ou que je capture en direct ?
- Quel équipement ou quelle interface dois-je observer ?
- Quelle question précise vais-je tenter de résoudre ?

### 15.2 Les zones de la fenêtre principale

| Zone | Image simple | Utilité technique |
|---|---|---|
| Menu principal | Les tiroirs des outils | Accès à toutes les commandes classées par fonction |
| Barre d’outils principale | Les boutons des actions courantes | Raccourcis visuels vers ouvrir, enregistrer, démarrer ou arrêter, selon l’état |
| Barre de filtre | Une loupe qui trie les lignes visibles | Saisir un filtre d’affichage ; ne supprime pas les paquets du fichier |
| Liste des paquets | La liste des enveloppes observées | Résume chaque trame/paquet avec numéro, temps, source, destination, protocole, longueur et résumé |
| Détails du paquet | L’enveloppe ouverte couche par couche | Présente les protocoles et leurs champs décodés |
| Octets du paquet | Le contenu sous forme de nombres hexadécimaux | Affiche les octets capturés ; la sélection d’un champ dans les détails met en évidence les octets correspondants |
| Diagramme de paquet | Un dessin explicatif, si disponible | Représentation visuelle des couches et champs du paquet sélectionné |
| Barre d’état | Le tableau de bord de l’analyse | Donne des informations sur le fichier, le filtre, la sélection ou l’état courant |

Quand tu sélectionnes une ligne dans la liste, les panneaux Détails et Octets changent pour montrer **ce paquet-là**. Un champ choisi dans Détails est souvent mis en évidence dans la vue Octets. Cette correspondance aide à apprendre comment un protocole range ses informations.

La disposition peut être modifiée et certains panneaux peuvent être masqués. Si un panneau « a disparu », vérifie d’abord **View / Affichage** avant de réinitialiser tes préférences.

## 16. Menu File / Fichier

Le menu **File** sert à ouvrir, assembler, enregistrer, exporter, imprimer et fermer des captures. Il travaille sur le fichier et son contenu ; il ne remplace pas l’analyse du réseau.

| Commande | À quoi elle sert | Exemple / précaution |
|---|---|---|
| **Open…** | Ouvrir une capture existante | Lire un `.pcap` ou `.pcapng` reçu pour analyse. L’ouverture n’implique pas que tu sois autorisé à partager ce fichier. |
| **Open Recent** | Sous-menu des fichiers ouverts récemment | Pratique pour reprendre une analyse. Attention à l’écran partagé : les chemins ou noms de fichiers peuvent révéler des informations. |
| **Merge…** | Fusionner une capture dans celle déjà ouverte | Utile pour comparer ou réunir plusieurs fichiers. Vérifier les horodatages et le type de fusion ; une fusion ne garantit pas l’ordre chronologique ni l’absence de doublons. |
| **Import from Hex Dump…** | Transformer un texte contenant une représentation hexadécimale en capture temporaire | Utile si un outil ou un rapport fournit les octets d’un paquet. Il faut que le texte contienne assez d’informations pour reconstruire une trame. |
| **Close** | Fermer la capture courante | Si des changements ne sont pas enregistrés, Wireshark peut demander quoi faire. Cela ne ferme pas forcément l’application. |
| **Save** | Enregistrer la capture courante | Une capture en direct doit généralement être arrêtée avant l’enregistrement par cette commande. Le fichier peut contenir les paquets visibles et les métadonnées prises en charge par le format. |
| **Save As…** | Enregistrer sous un autre nom ou emplacement | À utiliser pour créer une copie de travail et préserver l’original. Vérifier le format choisi et le chemin. |
| **File Set → List Files** | Afficher les fichiers d’un ensemble de captures découpées | Utile si une capture longue a été écrite en plusieurs fichiers. |
| **File Set → Next File** | Ouvrir le fichier suivant d’un ensemble | Désactivé si le fichier courant n’appartient pas à une série ou s’il est le dernier. |
| **File Set → Previous File** | Ouvrir le fichier précédent d’un ensemble | Permet de revenir dans la série. |
| **Export Specified Packets…** | Enregistrer une sélection de paquets dans un nouveau fichier | On peut exporter tous les paquets, ceux affichés, ceux marqués ou une plage. Attention : « affichés » dépend du filtre actif. |
| **Export Packet Dissections…** | Exporter le décodage lisible de paquets | Pratique pour un rapport texte, CSV ou XML selon les options. Le résultat est une représentation du décodage, pas nécessairement une capture réouvrable comme PCAP. |
| **Export Objects → [protocole]** | Extraire des objets reconstitués lorsque le protocole et la capture le permettent | La liste des protocoles disponibles varie. Les objets extraits peuvent être malveillants ou confidentiels ; ne pas les ouvrir directement sur un poste de travail. |
| **Print…** | Imprimer une sélection ou des détails | Utile pour un rapport ponctuel, mais une impression volumineuse est difficile à rechercher et peut exposer des données. |
| **Quit** | Fermer l’application | Si une capture ou des modifications ne sont pas enregistrées, Wireshark peut demander confirmation. |

### 16.1 Différence importante : enregistrer, exporter des paquets, exporter des objets

- **Save / Save As** : conserve une capture comme fichier d’analyse.
- **Export Specified Packets** : crée une capture plus petite contenant une sélection de paquets.
- **Export Packet Dissections** : crée un fichier de texte ou de données avec le décodage affiché.
- **Export Objects** : extrait un contenu applicatif reconstitué lorsqu’il est disponible.

Ces opérations ne sont pas interchangeables. Avant de transmettre un extrait, rouvre-le et vérifie ce qu’il contient. Exporter seulement les paquets visibles peut omettre des échanges masqués par le filtre.

## 17. Menu Edit / Édition

Le menu **Edit** contient des actions d’analyse et de personnalisation. Certaines modifications sont seulement temporaires dans la session ; d’autres, comme un commentaire dans un PCAPNG, peuvent être écrites dans le fichier.

### 17.1 Copier et rechercher

- **Copy / Copier** : sous-menu de copie du résumé, des détails ou des propriétés du paquet sélectionné selon le contexte. C’est utile pour un rapport, mais relis le texte copié : des adresses internes, domaines ou données sensibles peuvent être inclus.
- **Find Packet… / Rechercher un paquet…** (`Ctrl+F`) : ouvre une barre de recherche. Selon le mode choisi, recherche une chaîne, une séquence d’octets ou un filtre d’affichage. Une recherche textuelle ne remplace pas une recherche dans les champs protocolaires.
- **Find Next / Find Previous** (`Ctrl+N` / `Ctrl+B`) : passent au résultat suivant ou précédent selon les critères du dernier outil de recherche.

Image simple : le filtre d’affichage cache toutes les lignes sauf celles qui correspondent ; la recherche te fait sauter d’un résultat au suivant.

### 17.2 Marquer des paquets

- **Mark/Unmark Selected** (`Ctrl+M`) : marque ou démarque le paquet sélectionné.
- **Mark All Displayed Packets** (`Ctrl+Shift+M`) et **Unmark All Displayed Packets** : agissent sur les paquets visibles selon le filtre actif.
- **Next Mark / Previous Mark** : naviguent entre les paquets marqués.

Un marquage sert de signet visuel dans une grosse capture. Il peut aussi servir à choisir les paquets lors d’un export ou d’une impression. Les marques sont un état d’analyse ; elles ne changent pas les octets réseau. Selon le format et la version, elles ne sont pas nécessairement conservées après fermeture. Pour préserver une analyse, ajoute des commentaires pris en charge ou documente les numéros de paquets dans un compte rendu.

### 17.3 Ignorer des paquets

- **Ignore/Unignore Selected** (`Ctrl+D`) : demande à Wireshark de traiter le paquet sélectionné comme s’il n’était pas présent dans l’analyse courante.
- **Ignore All Displayed** et **Unignore All Displayed** : agissent sur la sélection actuellement affichée.

Un paquet ignoré n’est pas effacé du PCAP. Il peut être réaffiché en annulant l’ignorance. Mais une analyse faite avec des paquets ignorés peut donner une vue incomplète : note ce changement dans ton compte rendu et vérifie avant de conclure.

### 17.4 Références temporelles et changement d’heure

- **Set/Unset Time Reference** (`Ctrl+T`) : définit le paquet sélectionné comme origine relative pour afficher les temps suivants. C’est pratique pour mesurer le délai entre une requête et une réponse.
- **Unset All Time References** : supprime ces repères temporaires.
- **Next/Previous Time Reference** : navigue entre ces points.
- **Time Shift…** (`Ctrl+Shift+T`) : applique un décalage d’horodatage aux paquets concernés dans l’analyse. Cette fonction peut servir à corriger un décalage connu entre captures, mais elle peut fausser une chronologie si le décalage est supposé plutôt que mesuré. Travaille sur une copie et conserve les valeurs d’origine.

Une référence temporelle ne signifie pas que l’horloge de la machine était exacte. Pour corréler plusieurs sources, note le fuseau horaire, la synchronisation NTP éventuelle et les décalages connus.

### 17.5 Commentaires de paquets

- **Packet Comment…** : ajoute un commentaire à un paquet.
- **Delete All Packet Comments** : enlève les commentaires de tous les paquets.

Le support dépend du format du fichier : PCAPNG peut stocker des commentaires, tandis que le format PCAP classique ne prend pas en charge tous ces éléments. Un commentaire est utile pour expliquer une observation (« réponse DNS après la requête du paquet 42 »), pas pour remplacer la preuve ou le raisonnement.

### 17.6 Secrets de déchiffrement

- **Inject TLS Secrets** : intègre au fichier de capture des secrets TLS utilisés pour le déchiffrement, lorsque le format le permet.
- **Inject ESP Secrets** : intègre des secrets ESP utilisés pour analyser certains flux IPsec.
- **Discard All Secrets** : retire les secrets intégrés pris en charge.

Ces commandes sont sensibles. Un fichier avec secrets de déchiffrement peut permettre à une autre personne de lire des communications protégées enregistrées dans le PCAP. Ne partage pas ce fichier comme un PCAP ordinaire. Contrôle le format, le contenu, les autorisations et le canal de transmission.

### 17.7 Profils et préférences

- **Configuration Profiles…** (`Ctrl+Shift+A`) : gère des profils de configuration. Un profil peut séparer des colonnes, couleurs, filtres et préférences selon un usage, par exemple apprentissage, dépannage ou analyse SOC. Les profils ne changent pas le trafic capturé.
- **Preferences…** (`Ctrl+Shift+P`, raccourci différent sur macOS) : ouvre les réglages de Wireshark. On y trouve des catégories pour l’interface, la capture, les protocoles, les noms, les couleurs et d’autres comportements.

Conseil : crée un profil « SOC » ou « apprentissage » avant de modifier de nombreux réglages. Si le résultat devient confus, tu pourras revenir au profil initial sans réinstaller le programme.

## 18. Menu View / Affichage

Le menu **View** change la manière dont Wireshark présente les données. Il ne modifie normalement pas les octets de la capture. Certaines options peuvent toutefois déclencher une nouvelle résolution de noms ou un nouveau décodage, ce qui change les libellés ou l’interprétation affichés.

### 18.1 Afficher ou masquer les zones

Les options **Main Toolbar**, **Filter Toolbar**, **Wireless Toolbar**, **Statusbar**, **Packet List**, **Packet Details**, **Packet Bytes** et, si disponible, **Packet Diagram** affichent ou masquent les zones correspondantes.

Si la liste des paquets est masquée, la sélection du paquet peut devenir difficile ; si les détails sont masqués, tu ne vois plus l’arbre des protocoles. Pour revenir à une disposition pratique, réactive les trois panneaux principaux et la barre de filtre.

### 18.2 Sous-menu Time Display Format

Ce sous-menu contrôle l’affichage des horodatages, par exemple :

- **Date and Time of Day** : date et heure lisibles ;
- **Time of Day** : heure de la journée ;
- **Seconds Since Epoch** : secondes depuis le 1er janvier 1970 ;
- **Seconds Since First Captured Packet** : temps relatif au début de la capture ou à un repère temporel ;
- **Seconds Since Previous Captured Packet** : délai depuis le paquet précédent capturé ;
- **Seconds Since Previous Displayed Packet** : délai depuis le paquet précédent encore visible ;
- **Automatic / Seconds / …seconds** : précision d’affichage, par exemple seconde, milliseconde, microseconde ou nanoseconde selon le fichier et la version ;
- **Display Seconds with hours and minutes** : change la présentation des durées.

Attention à la différence entre « précédent capturé » et « précédent affiché » : un filtre peut cacher des paquets, donc ces deux intervalles peuvent être différents. Le choix de format ne change pas l’heure enregistrée ; il change sa représentation.

### 18.3 Sous-menu Name Resolution

Les options de résolution permettent d’afficher des noms à la place de certaines adresses :

- **Edit Resolved Name** : saisir manuellement un nom pour une adresse dans la capture courante ;
- **Enable for MAC Layer** : résoudre ou présenter certains identifiants de couche liaison sous une forme nommée ;
- **Enable for Network Layer** : traduire des adresses réseau, notamment IP, en noms lorsqu’une résolution est disponible ;
- **Enable for Transport Layer** : afficher des noms de services à la place de numéros de ports lorsque connus.

Les noms rendent parfois l’écran plus lisible, mais l’adresse numérique est souvent plus fiable pour l’analyse. Un nom résolu n’est pas automatiquement une preuve de l’identité d’une machine. Pour les rapports ou une analyse reproductible, conserve les valeurs brutes et note si la résolution était activée.

### 18.4 Zoom, développement et couleurs

- **Zoom In / Zoom Out / Normal Size** : agrandit ou réduit la police ; utile en présentation ou pour lire les champs.
- **Expand Subtrees / Collapse Subtrees** : développe ou ferme la branche sélectionnée dans le panneau Détails.
- **Expand All / Collapse All** : développe ou ferme les arborescences. Développer tous les paquets peut ralentir l’affichage et rendre l’analyse illisible.
- **Colorize Packet List** : active ou désactive les couleurs de lignes.
- **Colorize Conversation → Color 1–10** : applique temporairement une couleur à une conversation choisie.
- **Colorize Conversation → Reset coloring** : retire les couleurs temporaires de conversation.
- **Colorize Conversation → New Coloring Rule…** : crée une règle de couleur persistante fondée sur un filtre.
- **Coloring Rules…** : gère les règles qui colorent les paquets selon des expressions de filtre.

Les couleurs accélèrent le repérage, mais elles ne constituent pas un verdict de sécurité. Une ligne colorée selon une règle locale ne signifie pas que Wireshark a déclaré une attaque.

### 18.5 Colonnes, fenêtres, décodage et outils internes

- **Resize All Columns** : ajuste les largeurs des colonnes ; sur un très gros fichier, le calcul peut prendre du temps.
- **Internals → Conversation Hash Tables** : montre des associations internes utilisées pour identifier les conversations.
- **Internals → Dissector Tables** : présente les relations entre décodeurs de protocoles.
- **Internals → Supported Protocols** : liste les protocoles et champs reconnus par cette installation.
- **Show Packet in New Window** : ouvre les détails et les octets d’un paquet dans une fenêtre séparée, qui garde ce paquet même si tu sélectionnes une autre ligne dans la fenêtre principale.
- **Redissect Packets** : redécode les paquets. Utile après un changement de résolution ou d’informations de déchiffrement ; cela ne récupère pas des octets qui n’ont jamais été capturés.
- **Reload as File Format/Capture** : bascule entre l’affichage habituel des trames et une vue de structure de fichier lorsque le format le permet.
- **Reload** : recharge le fichier actuel depuis le disque. Si des modifications non enregistrées sont présentes, vérifie ce que Wireshark demande avant de continuer.

## 19. Menu Go / Aller

Le menu **Go** sert à se déplacer rapidement dans une capture. Il ne modifie pas les paquets.

| Commande | Utilité |
|---|---|
| **Go to Packet…** (`Ctrl+G`) | Saisir un numéro de paquet et y accéder. Le numéro est celui de la capture, pas nécessairement le rang d’affichage après filtre. |
| **Go to Linked Packet** | Aller au paquet correspondant à un champ lié, par exemple une requête et sa réponse, si Wireshark connaît ce lien. |
| **Next Packet / Previous Packet** (`Ctrl+↓` / `Ctrl+↑`) | Naviguer ligne par ligne dans la liste, même si une autre zone avait le focus. |
| **First Packet / Last Packet** (`Ctrl+Home` / `Ctrl+End`) | Aller au premier ou au dernier paquet de la capture. |
| **Next Packet In Conversation / Previous Packet In Conversation** (`Ctrl+.` / `Ctrl+,`) | Passer au paquet suivant ou précédent dans la conversation associée au paquet sélectionné. |
| **First Packet In Conversation / Last Packet In Conversation** | Aller au début ou à la fin de cette conversation. |
| **Next Packet in History / Previous Packet in History** (`Alt+→` / `Alt+←`) | Revenir dans l’historique de navigation, comme les boutons précédent/suivant d’un navigateur. |
| **Auto Scroll in Live Capture** | Fait défiler la liste pendant une capture en direct pour garder les nouveaux paquets visibles. Cela peut empêcher d’examiner une ligne ancienne sans que l’écran saute. |
| **Aggregation in Live Capture** | Regroupe l’affichage selon des champs choisis et ne montre que la trame la plus récente de chaque combinaison. C’est une vue résumée, pas une suppression des paquets de la capture. |

### 19.1 Numéro de paquet et filtre actif

Un filtre d’affichage peut masquer une grande partie des paquets, mais il ne renumérote pas les paquets d’origine. Ainsi, la première ligne visible après application d’un filtre peut porter un numéro élevé. Pour un rapport, cite le numéro de trame et le filtre utilisé afin qu’une autre personne puisse retrouver le même élément.

## 20. Méthode simple pour se repérer dans les menus

Quand tu ne sais pas où chercher une commande :

1. Détermine si ton action porte sur le **fichier**, l’**affichage**, la **navigation**, la **capture** ou l’**interprétation**.
2. Choisis le menu de cette famille : File, View, Go, Capture ou Analyze.
3. Vérifie si l’option est grisée. Une option grisée peut simplement nécessiter qu’un fichier soit ouvert, qu’un paquet soit sélectionné ou qu’une capture soit arrêtée.
4. Lis la barre d’état et observe le résultat après l’action.
5. Si l’action change le contenu, l’heure, les secrets ou les paquets exportés, travaille sur une copie et consigne ce que tu as fait.

Les menus décrits ici correspondent à la documentation utilisateur officielle consultée en octobre 2026. Les versions Windows, Kali et Parrot peuvent différer par la version installée, les composants compilés, la traduction et les extensions ; certains intitulés, raccourcis ou sous-menus peuvent donc varier.

## Références officielles pour cette partie

- Fenêtre principale : https://www.wireshark.org/docs/wsug_html_chunked/ChUseMainWindowSection.html
- Menu général : https://www.wireshark.org/docs/wsug_html_chunked/ChUseMenuSection.html
- File / Fichier : https://www.wireshark.org/docs/wsug_html_chunked/ChUseFileMenuSection.html
- Edit / Édition : https://www.wireshark.org/docs/wsug_html_chunked/ChUseEditMenuSection.html
- View / Affichage : https://www.wireshark.org/docs/wsug_html_chunked/ChUseViewMenuSection.html
- Go / Aller : https://www.wireshark.org/docs/wsug_html_chunked/ChUseGoMenuSection.html
- Horodatages : https://www.wireshark.org/docs/wsug_html_chunked/ChWorkTimeFormatsSection.html

# Partie III — Menus de capture et d’analyse

## 21. Menu Capture

Le menu **Capture** contrôle l’observation en direct. Il agit avant ou pendant la création du fichier. Une mauvaise interface ou un filtre de capture trop strict peut empêcher l’enregistrement d’éléments dont tu auras besoin plus tard.

### 21.1 Commandes principales

| Commande | Raccourci courant | Fonction |
|---|---:|---|
| **Options…** | `Ctrl+K` | Ouvre la configuration détaillée de la capture : interfaces, filtres, fichiers, limites, affichage en direct et autres options. |
| **Start** | `Ctrl+E` | Démarre la capture avec les derniers réglages utilisés. Vérifie l’interface et le filtre avant de cliquer. |
| **Stop** | `Ctrl+E` | Arrête la capture en cours. Arrêter proprement permet de finaliser le fichier et d’analyser les paquets reçus. |
| **Restart** | `Ctrl+R` | Arrête puis recommence avec les mêmes options. Les paquets de la première capture ne sont pas automatiquement ajoutés à la nouvelle : enregistre-les d’abord si tu veux les conserver. |
| **Capture Filters…** | — | Crée, modifie, nomme et enregistre des filtres de capture réutilisables. Leur syntaxe est celle de libpcap/BPF, distincte de celle des filtres d’affichage. |
| **Refresh Interfaces** | `F5` | Reconstruit la liste des interfaces. Utile après branchement d’un adaptateur, activation d’un VPN ou changement de configuration. |

### 21.2 Fenêtre Capture Options — onglet Input

La liste des interfaces peut présenter plusieurs colonnes et réglages :

- **Interface** : nom de l’interface ; son icône de configuration peut ouvrir les options propres au périphérique.
- **Traffic** : petit indicateur d’activité. Il sert à choisir une interface candidate, mais ne prouve pas qu’elle transporte le trafic recherché.
- **Link-layer Header** : type d’en-tête de couche liaison enregistré. Il dépend de l’interface et peut parfois être choisi.
- **Promiscuous** : demande à l’interface de remettre à l’analyseur les trames qu’elle voit, même si elles ne sont pas adressées à sa propre adresse MAC. Sur un commutateur, ce mode ne transforme pas une prise ordinaire en miroir de tous les ports.
- **Snaplen** : quantité maximale d’octets conservée par paquet. Une valeur réduite économise de l’espace, mais peut couper le contenu nécessaire à l’analyse. La valeur complète est généralement préférable au début, sauf contrainte de confidentialité ou de volume bien comprise.
- **Buffer** : mémoire tampon utilisée pendant la capture. Un buffer trop petit peut favoriser des pertes lorsque le débit est élevé ; augmenter la valeur ne corrige pas une mauvaise interface ou un poste surchargé.
- **Monitor Mode** : pour le Wi-Fi, demande une capture des en-têtes radio 802.11 lorsque matériel, pilote et système le permettent. L’activer peut couper la connexion Wi-Fi courante.
- **Capture Filter** : filtre appliqué avant l’enregistrement. Si le filtre exclut un paquet, il ne sera pas dans le fichier pour l’analyse ultérieure.
- **Capture filter for selected interfaces** : applique un même filtre à plusieurs interfaces sélectionnées.
- **Manage Interfaces** : gère les interfaces locales et, selon la configuration, des interfaces distantes ou des sources de capture particulières.
- **Compile Selected BPFs** : montre le filtre de capture traduit en instructions BPF. C’est un outil d’apprentissage et de diagnostic, pas une autre syntaxe à saisir.

### 21.3 Onglet Output et fichiers de capture

- **Capture to a permanent file / File** : indique le chemin du fichier. Si aucun nom permanent n’est donné, Wireshark peut utiliser un fichier temporaire.
- **Output format** : PCAPNG est le format par défaut documenté et prend en charge plus de métadonnées que PCAP classique. PCAPNG est particulièrement utile pour plusieurs interfaces, commentaires et informations supplémentaires.
- **Processes** : sur les systèmes pris en charge, peut enregistrer des informations reliant certains paquets TCP/UDP à un processus local. Ces métadonnées peuvent contenir un nom d’utilisateur, un chemin ou une ligne de commande sensible ; certaines lignes de commande peuvent exposer un secret. N’active pas cette option sans besoin et ne partage pas le fichier sans l’inspecter.
- **Create a new file automatically…** : crée un nouveau fichier selon une limite comme le nombre de paquets, la taille, la durée ou l’heure murale.
- **Use a ring buffer with** : fait tourner un ensemble borné de fichiers. Quand le nombre fixé est atteint, les fichiers les plus anciens peuvent être remplacés. C’est adapté à une surveillance circulaire autorisée, mais risqué si l’on oublie que les anciennes données seront écrasées.

Pour une capture longue, fixe un dossier, une taille maximale et une durée, puis vérifie l’espace disque. Ne laisse pas une capture illimitée tourner sans surveillance.

### 21.4 Onglet Options

- **Update list of packets in real-time** : actualise la liste des paquets pendant la capture. Désactivé, l’affichage peut attendre l’arrêt.
- **Automatically scroll during live capture** : garde les nouveaux paquets à l’écran. Désactive-le temporairement si tu analyses une partie ancienne.
- **Show capture information during capture** : montre des informations d’état pendant l’enregistrement.
- **Name Resolution** : active ou désactive la résolution des adresses MAC, réseau et transport. La résolution réseau peut effectuer des requêtes DNS selon les réglages ; pour une analyse strictement passive ou reproductible, considère de la désactiver et conserve les adresses numériques.
- **Stop capture automatically after…** : arrête la capture après un nombre de paquets/fichiers, une taille ou une durée définie.

### 21.5 Capture Filters : ce qu’ils font et quand les utiliser

Un **capture filter** agit au moment où les paquets sont reçus. Il réduit le volume sauvegardé, mais peut retirer définitivement de la capture les échanges exclus. Exemples de syntaxe libpcap/BPF :

```text
host 192.0.2.10
```

Capture le trafic à destination ou en provenance de l’adresse d’exemple `192.0.2.10`.

```text
udp port 53
```

Capture le trafic UDP associé au port 53. Cela ne couvre pas nécessairement toutes les situations où DNS peut être utilisé : il faut comprendre le réseau et le protocole visé.

```text
host 192.0.2.10 and tcp port 443
```

Combine un hôte avec un protocole/port TCP. La syntaxe de capture n’est pas la syntaxe d’affichage.

**Règle de travail pour débuter :** si le volume le permet et que l’autorisation est claire, capture un périmètre utile sans filtre restrictif, puis utilise un filtre d’affichage pour explorer. Utilise un filtre de capture lorsque le débit ou le stockage l’exige et que tu sais précisément quelles données tu peux exclure.

### 21.6 Enregistrement en direct : méthode courte

1. Ouvre **Capture → Options**.
2. Choisis l’interface en comparant le nom, les adresses et l’indicateur de trafic.
3. Laisse les options par défaut tant qu’un besoin concret ne justifie pas de les modifier.
4. Indique un fichier durable si tu dois conserver la capture ; choisis PCAPNG dans les cas usuels.
5. Définis une durée ou une limite si la capture peut être longue.
6. N’ajoute un filtre de capture qu’après l’avoir vérifié.
7. Démarre, reproduis une seule action contrôlée, puis arrête.
8. Vérifie le nombre de paquets et les échanges attendus. Note les pertes éventuelles et le point d’observation.

## 22. Menu Analyze / Analyse

Le menu **Analyze** aide à interpréter les paquets déjà disponibles. Il ne répare pas le réseau et ne remplace pas le jugement de l’analyste.

### 22.1 Filtres et expressions

- **Display Filters…** : gère les filtres d’affichage enregistrés, nommés et réutilisables.
- **Display Filter Macros…** : crée des expressions paramétrées qui peuvent servir dans des filtres d’affichage enregistrés. Une macro d’affichage n’est pas un filtre de capture.
- **Display Filter Expression…** : ouvre un constructeur qui aide à choisir un champ, une comparaison et une valeur. C’est un bon outil pour apprendre les noms exacts des champs.
- **Apply as Column** (`Shift+Ctrl+I`) : transforme le champ sélectionné dans les détails en colonne de la liste. Pratique pour comparer rapidement une valeur dans beaucoup de paquets.
- **Apply as Filter** : construit et applique immédiatement un filtre à partir du champ sélectionné. Le menu contextuel peut proposer des choix tels que remplacer le filtre actuel ou ajouter une condition.
- **Prepare as Filter** : prépare la même expression sans l’appliquer tout de suite. Cela permet de relire la condition avant de filtrer.
- **Conversation Filter** : filtre les paquets appartenant à une conversation, éventuellement dans un sens ou les deux selon le protocole et les options présentes.

Exemple de logique : sélectionne `ip.src` dans l’arbre de détails puis **Apply as Filter**. Wireshark peut générer un filtre qui isole l’adresse source correspondante. La valeur et l’expression exacte dépendent du champ sélectionné.

### 22.2 Enabled Protocols

**Enabled Protocols…** ouvre la liste des dissectors activés. Un *dissector* est le décodeur qui explique à Wireshark comment interpréter des octets comme un protocole.

- Désactiver un protocole peut empêcher son décodage et ses sous-dissections.
- Cela peut accélérer ou simplifier une analyse dans certains cas.
- Cela peut aussi faire disparaître des champs, des filtres, des statistiques ou des options Follow.
- Ce réglage ne supprime pas les octets du fichier.

Si un paquet apparaît sous forme de données inconnues après un changement, vérifie d’abord si le protocole a été désactivé. Note les changements de préférences dans le compte rendu.

### 22.3 Decode As

**Decode As…** permet de demander à Wireshark d’interpréter un flux ou un port comme un protocole choisi, lorsque l’identification automatique ne convient pas. Exemple pédagogique : un service de laboratoire utilise un port non standard et l’analyste sait, grâce à une preuve indépendante, qu’il transporte un protocole reconnu.

Ce choix est une hypothèse de décodage, pas une preuve que l’application utilise réellement ce protocole. Si le décodage devient illisible, rétablis l’affectation d’origine. Ne choisis pas un protocole seulement parce qu’il produit un écran qui semble familier.

### 22.4 SCTP

Lorsque le paquet sélectionné appartient à une association SCTP, le menu peut proposer des actions liées à cette association, notamment des filtres ou des informations spécialisées. Si aucun paquet SCTP reconnu n’est sélectionné, ces commandes peuvent être grisées ou absentes.

### 22.5 Follow / Suivre un flux

Le sous-menu **Follow** permet de suivre les données d’un flux reconnu, par exemple TCP, UDP, TLS, HTTP, HTTP/2, QUIC, WebSocket, SIP ou USB CDC selon la capture et la version.

Wireshark applique alors un filtre de conversation et ouvre une fenêtre de suivi. Pour TCP, les données sont présentées dans l’ordre du flux ; les directions sont différenciées par des couleurs. Les octets non imprimables peuvent apparaître comme des points. Les contenus chiffrés restent chiffrés tant que les conditions de déchiffrement ne sont pas remplies.

**À quoi cela sert :** reconstruire une requête et une réponse applicatives, isoler une session ou comprendre le dialogue entre client et serveur.

**Ce que cela ne prouve pas :** que le contenu affiché est complet si la capture commence au milieu du flux, qu’un protocole est correctement interprété si le décodage est supposé, ni qu’un contenu chiffré est en clair.

### 22.6 Show Packet Bytes

**Show Packet Bytes** ouvre un outil pour afficher ou transformer les octets sélectionnés : décodage Base64, décompression ou interprétation comme un autre jeu de caractères ou un type de contenu, selon les données. Les transformations ne rendent pas automatiquement un contenu fiable.

Traite les données extraites comme non fiables. Ne lance pas un exécutable ou un script exporté pour « voir ce qu’il fait ». Analyse-le dans un environnement isolé avec une procédure défensive adaptée.

### 22.7 Expert Info

**Expert Info** regroupe les éléments que certains dissectors signalent comme remarquables, par exemple des retransmissions, des erreurs de protocole ou des comportements inhabituels. Les catégories courantes vont des commentaires/notifications aux notes, avertissements et erreurs.

Un message Expert Info est un indice à examiner, pas un verdict automatique d’attaque ou de panne. Par exemple, une retransmission peut être compatible avec une perte, une congestion, un problème de capture ou d’autres causes. Ouvre le paquet, regarde le contexte avant et après, puis compare avec les journaux et une autre source si disponible.

## 23. Menu Statistics / Statistiques

Les statistiques résument une capture ou une partie sélectionnée. Elles répondent à des questions comme : « quels protocoles apparaissent ? », « quels hôtes parlent le plus ? » ou « quand le volume augmente-t-il ? ». Elles décrivent seulement ce qui est présent au point de capture.

### 23.1 Statistiques générales

| Élément | Ce qu’il résume | Exemple SOC ou dépannage |
|---|---|---|
| **Capture File Properties** | Format, durée, nombre de paquets, interfaces et métadonnées disponibles | Vérifier si la capture couvre toute la période utile et si des commentaires ou informations de pertes existent |
| **Resolved Addresses** | Noms associés aux adresses lorsque la résolution est disponible | Vérifier quels noms Wireshark a associés ; comparer avec les adresses brutes |
| **Protocol Hierarchy** | Arbre des protocoles, nombres et volumes observés | Repérer rapidement un protocole inattendu ou une capture dominée par un type de trafic |
| **Conversations** | Échanges entre deux endpoints, volumes, durée et débit moyen | Repérer les principales communications et lancer Follow Stream sur un échange pertinent |
| **Endpoints** | Hôtes/adresses observés par couche de protocole | Voir les adresses présentes et leurs compteurs ; utile pour dresser la liste des systèmes visibles |
| **Packet Lengths** | Répartition des tailles de paquets | Distinguer des échanges de contrôle de transferts plus volumineux, avec prudence |
| **I/O Graphs** | Compteurs ou volumes tracés dans le temps, avec filtres et intervalles | Repérer une pointe de trafic ou comparer TCP, DNS, ICMP ou une adresse sur la même chronologie |
| **Plots** | Valeurs de champs sélectionnés représentées dans le temps | Explorer comment une valeur observée évolue pendant la capture |
| **Service Response Time** | Durée entre requêtes et réponses de protocoles pris en charge | Estimer les délais applicatifs observés ; distinguer délai serveur, réseau et limites du point de capture |
| **Distribution** | Distribution de valeurs d’un champ et, selon la fenêtre, entropie | Examiner si une valeur ou une catégorie domine, sans traiter l’entropie seule comme indicateur de malveillance |

### 23.2 Conversations et endpoints : ne pas les confondre

- Un **endpoint** représente une extrémité logique à une couche donnée : adresse MAC, adresse IP, ou combinaison adresse IP + port pour TCP/UDP.
- Une **conversation** représente le trafic associé entre deux extrémités.

La fenêtre peut limiter l’analyse au filtre d’affichage courant. Vérifie ce réglage : si le filtre masque des paquets, les nombres de conversations peuvent ne représenter qu’une partie du fichier. Une adresse très active peut être un serveur DNS, un proxy, une mise à jour logicielle ou un système compromis ; il faut regarder le protocole, le rôle attendu et la période.

### 23.3 Hiérarchie des protocoles : lire les pourcentages correctement

Les protocoles sont imbriqués : une même trame peut compter dans Ethernet, IPv4, TCP, TLS et HTTP. Les pourcentages des lignes ne sont donc pas nécessairement additionnables à 100 %. Certaines données peuvent être réassemblées entre plusieurs trames ou rester non décodées.

Utilise la hiérarchie pour orienter le triage, pas pour conclure qu’un protocole absent n’a pas été utilisé : il peut être masqué par un filtre, non capturé, encapsulé, chiffré ou non reconnu.

### 23.4 I/O Graphs et Plots

Un graphique I/O agrège des compteurs ou des octets par intervalle de temps. Selon les réglages, tu peux afficher plusieurs courbes, associer un filtre à chaque courbe et comparer les pics.

Exemple de raisonnement SOC :

1. Construis une courbe pour tout le trafic.
2. Ajoute une courbe filtrée sur une machine ou un protocole pertinent.
3. Observe si le pic coïncide avec une requête, une connexion ou un transfert.
4. Reviens à la liste des paquets à cet instant et vérifie le détail.

Le graphique ne donne pas la cause de la pointe. Les intervalles, le filtre, l’horloge et les paquets manquants influencent la forme.

### 23.5 Statistiques spécialisées par protocole

Le menu peut ajouter des fenêtres spécifiques si le dissector correspondant est présent et si la capture contient des paquets reconnus. La liste change selon les versions et composants.

| Famille / entrée courante | À quoi elle sert en gros |
|---|---|
| **DHCP (BOOTP)** | Résumer les échanges de configuration réseau DHCP |
| **DNS** | Examiner des compteurs et requêtes DNS selon les vues disponibles |
| **HTTP / HTTP2** | Résumer des requêtes et réponses reconnues dans la capture |
| **TCP Stream Graphs** | Visualiser certaines propriétés d’un flux TCP dans le temps |
| **UDP Multicast Streams** | Examiner les flux de diffusion multicast UDP reconnus |
| **IPv4 Statistics / IPv6 Statistics** | Compter, classer ou regrouper des informations IP |
| **Flow Graph** | Montrer l’ordre des échanges entre endpoints, utile pour expliquer une séquence |
| **Service Response Time** | Mesurer des délais requête/réponse pour les protocoles pris en charge |
| **ONC-RPC, BACnet, Collectd, ANCP, HART-IP, HPFEEDS, F5, SOME/IP, DTN, RSerPool, 29West, Sametime, NetPerfMeter, ILNP** | Fonctions spécialisées de protocoles ou environnements particuliers ; elles sont utiles si tu travailles effectivement avec ces protocoles |

Il n’est pas nécessaire de mémoriser toutes les fenêtres rares au départ. Pour le SOC généraliste, commence par **Capture File Properties**, **Protocol Hierarchy**, **Conversations**, **Endpoints**, **I/O Graphs**, **DNS**, **Flow Graph**, **TCP Stream Graphs** et **Expert Info**. Ensuite, étudie les outils propres à ton environnement.

### 23.6 Procédure de triage par les statistiques

1. Ouvre les propriétés du fichier et confirme sa durée, son nombre de paquets et son contexte.
2. Regarde la hiérarchie des protocoles pour voir les grandes familles de trafic.
3. Consulte Endpoints pour identifier les adresses observées.
4. Consulte Conversations pour repérer les échanges volumineux, longs ou inattendus.
5. Applique un filtre d’affichage et compare les résultats avec le total non filtré.
6. Construis un I/O Graph pour situer les périodes d’activité.
7. Ouvre les paquets et les flux correspondants avant d’émettre une conclusion.
8. Note les limites : point de capture, filtre, pertes, chiffrement et durée.

## À retenir

- **Capture** décide ce qui entre dans le fichier ; un filtre de capture peut écarter définitivement des paquets.
- **Analyze** aide à sélectionner, décoder et interpréter les données déjà capturées.
- **Statistics** résume les données visibles ; les nombres dépendent du fichier et parfois du filtre actif.
- Une couleur, une statistique ou un message Expert Info est un indice à vérifier dans les paquets et le contexte.

## Références officielles pour cette partie

- Menu Capture : https://www.wireshark.org/docs/wsug_html_chunked/ChUseCaptureMenuSection.html
- Options de capture : https://www.wireshark.org/docs/wsug_html_chunked/ChCapCaptureOptions.html
- Filtres de capture : https://www.wireshark.org/docs/wsug_html_chunked/ChCapCaptureFilterSection.html
- Menu Analyze : https://www.wireshark.org/docs/wsug_html_chunked/ChUseAnalyzeMenuSection.html
- Suivre les flux : https://www.wireshark.org/docs/wsug_html_chunked/ChAdvFollowStreamSection.html
- Expert Info : https://www.wireshark.org/docs/wsug_html_chunked/ChAdvExpert.html
- Menu Statistics : https://www.wireshark.org/docs/wsug_html_chunked/ChUseStatisticsMenuSection.html
- Statistiques : https://www.wireshark.org/docs/wsug_html_chunked/ChStatistics.html
- Conversations : https://www.wireshark.org/docs/wsug_html_chunked/ChStatConversations.html
- Endpoints : https://www.wireshark.org/docs/wsug_html_chunked/ChStatEndpoints.html
- Hiérarchie des protocoles : https://www.wireshark.org/docs/wsug_html_chunked/ChStatHierarchy
- I/O Graphs : https://www.wireshark.org/docs/wsug_html_chunked/ChStatIOGraphs.html

# Partie III — Menus spécialisés et aide

## 24. Menu Telephony / Téléphonie

Le menu **Telephony** rassemble des vues spécialisées pour la voix sur IP, la signalisation téléphonique et certains protocoles mobiles ou opérateurs. Il ne crée pas une capture téléphonique : il analyse les paquets déjà capturés et reconnus.

### 24.1 VoIP Calls

**VoIP Calls…** recherche des appels VoIP reconnus dans le trafic capturé, à partir des protocoles de signalisation, et associe les flux média RTP lorsqu’ils sont identifiables. La documentation Wireshark cite notamment H.323, IAX2, ISUP, MGCP/MEGACO, SIP, SKINNY et UNISTIM.

La fenêtre permet, selon la version, de :

- limiter la liste au filtre d’affichage courant ;
- passer d’une heure relative à une heure absolue ;
- ouvrir une séquence d’appel ou préparer un filtre ;
- sélectionner les flux RTP associés ;
- ouvrir le lecteur RTP lorsque le média et le codec sont compatibles ;
- copier les informations de la liste pour un rapport.

L’absence d’un appel dans cette fenêtre ne prouve pas qu’aucun appel n’a eu lieu : la capture peut manquer la signalisation ou le média, le protocole peut être chiffré ou le décodeur ne pas reconnaître le flux.

### 24.2 RTP : flux, analyse et lecteur

Le sous-menu **RTP** donne accès aux outils qui apparaissent selon la capture et la sélection :

- **RTP Streams** : liste les flux RTP reconnus et permet de sélectionner, filtrer, marquer, exporter ou analyser des flux.
- **RTP Stream Analysis** : présente des statistiques par flux, telles que numéros de séquence, délais entre paquets, gigue (*jitter*), décalage, bande passante et pertes estimées à partir des séquences.
- **RTP Player** : visualise et, si le codec est pris en charge, lit les flux audio. Il peut aussi exporter certains contenus.

Ces mesures dépendent de la qualité et de la durée de la capture ainsi que de la capacité de Wireshark à décoder le codec. Un paquet manquant dans la capture peut ressembler à une perte sur le réseau ; il faut donc distinguer perte observée dans la trace et perte réelle sur le réseau.

**Précaution de confidentialité :** une capture VoIP peut contenir le contenu audio, les numéros, identifiants d’appel, adresses et métadonnées personnelles. Lire ou exporter un appel exige une autorisation explicite et un stockage protégé.

### 24.3 SIP Flows et SIP Statistics

- **SIP Flows** se concentre sur les échanges SIP reconnus et les séquences de signalisation.
- **SIP Statistics** résume des informations relatives aux messages SIP dans la capture.

SIP sert souvent à établir, modifier ou terminer une session ; le média est souvent transporté séparément, par exemple en RTP. Une capture limitée à SIP ne garantit donc pas que le son soit présent.

### 24.4 Autres outils téléphonie

Les autres entrées dépendent de protocoles présents. Elles incluent dans les versions documentées : **ANSI**, **GSM**, **IAX2 Stream Analysis**, **ISUP Messages**, **LTE**, **MTP3**, **Osmux**, **RTSP**, **SCTP**, **SMPP Operations**, **UCP Messages**, **F1AP Messages**, **NGAP Messages**, **E2AP Messages**, **DIS Streams**, **H.225**, **WAP-WSP Packet Counter**.

Leur rôle général est de présenter des messages, séquences ou statistiques pour ces protocoles. Elles sont utiles dans les réseaux télécoms et environnements spécialisés, mais ne sont pas nécessaires pour commencer l’analyse SOC d’un réseau informatique classique.

Si une commande est grisée ou absente, vérifie que la capture contient le protocole attendu, que le paquet adéquat est sélectionné et que la version de Wireshark inclut le dissector concerné.

## 25. Menu Wireless / Sans fil

Le menu **Wireless** fournit des statistiques sur le trafic sans fil déjà présent dans la capture. La présence de ce menu ne signifie pas que la carte est en mode moniteur ni qu’elle a capturé toutes les trames radio environnantes. Le point d’observation, le pilote, le matériel, les clés et le type de capture restent déterminants.

### 25.1 WLAN Traffic

**WLAN Traffic** résume les réseaux Wi-Fi reconnus dans les trames capturées. La vue peut regrouper certaines requêtes de sondage (*probe requests*) avec un réseau dont le SSID correspond et copier le tableau vers un fichier CSV.

Cette fenêtre décrit les trames réellement présentes dans la capture. Elle ne permet pas à elle seule de conclure qu’un réseau est accessible, vulnérable ou malveillant.

### 25.2 Bluetooth Devices

**Bluetooth Devices** présente les informations sur les appareils Bluetooth observés, telles que l’adresse, le fabricant lorsqu’il est connu, le nom et l’interface. Les adresses ou noms observés ne prouvent pas nécessairement l’identité physique de l’utilisateur ou du propriétaire de l’appareil.

### 25.3 Bluetooth ATT Server Attributes

Cette vue concerne les attributs du serveur ATT (*Attribute Protocol*) visibles dans les échanges Bluetooth Low Energy décodés. Elle sert aux analystes qui étudient la découverte de services et de caractéristiques BLE. Les valeurs visibles dépendent de ce qui a été capturé et décodé.

### 25.4 Bluetooth HCI Summary

**Bluetooth HCI Summary** résume des informations issues des échanges HCI (*Host Controller Interface*) présents dans une capture compatible. Cela concerne souvent une trace entre l’hôte et son contrôleur Bluetooth, plutôt qu’une écoute radio universelle.

### 25.5 Déchiffrement Wi-Fi : vue d’ensemble

Wireshark peut analyser certains flux Wi-Fi chiffrés si les conditions de capture et les clés appropriées sont réunies. Le cours consacrera un chapitre distinct à ce sujet, car une capture « Wi-Fi » faite depuis l’interface normale de l’ordinateur n’est pas équivalente à une capture radio complète. Les clés de déchiffrement sont des secrets : ne les intègre pas à un PCAP partagé et ne les publie jamais sur GitHub.

## 26. Menu Tools / Outils

Le menu **Tools** contient des fonctions complémentaires. Le nombre d’entrées varie selon la version et les composants disponibles.

### 26.1 Firewall ACL Rules

Cette fonction peut générer des règles en ligne de commande pour certains pare-feu à partir d’un paquet sélectionné, notamment Cisco IOS, Linux Netfilter, OpenBSD pf ou le pare-feu Windows dans les versions documentées.

Wireshark suppose notamment que la règle sera appliquée à une interface externe. Ce résultat est un **brouillon à relire**, pas une configuration prête à appliquer :

- vérifie le sens, l’interface, les adresses, le protocole et les ports ;
- vérifie la politique implicite et l’ordre des règles du pare-feu cible ;
- teste dans un laboratoire ou une configuration de préproduction ;
- garde une méthode de retour arrière.

La commande peut être indisponible si un seul paquet n’est pas sélectionné.

### 26.2 Credentials

**Credentials** recherche dans la capture des identifiants que certains dissectors savent extraire, notamment dans des protocoles qui peuvent transporter des informations d’authentification visibles, tels que FTP, HTTP, IMAP, POP ou SMTP selon le trafic et la version.

C’est utile en réponse à incident pour déterminer si des identifiants ont pu être exposés. Cette fonction peut révéler des noms d’utilisateur et mots de passe en clair. Utilise-la uniquement sur une capture autorisée, limite l’accès au résultat et n’insère jamais de vrais secrets dans un rapport public.

La liste est limitée aux identifiants que Wireshark peut reconnaître dans la capture ; une liste vide ne prouve pas que le trafic ne contenait aucun secret.

### 26.3 MAC Address Blocks

Cette commande consulte les données de registre utilisées pour associer certains préfixes MAC à un fabricant. Cela aide à mettre un nom de fournisseur à côté d’une adresse, mais le préfixe n’identifie pas avec certitude le propriétaire, l’utilisateur ou l’emplacement d’un appareil. Les adresses peuvent être administrées localement, virtualisées ou aléatoires.

### 26.4 TLS Keylog Launcher

Lorsque cette fonction et l’environnement le permettent, **TLS Keylog Launcher** peut démarrer une application avec une variable d’environnement pointant vers un fichier de secrets TLS. Ces secrets peuvent permettre de déchiffrer certaines sessions capturées qui correspondent aux clés enregistrées.

Les secrets TLS permettent de lire des échanges protégés. Ils doivent être traités comme des identifiants sensibles, conservés séparément et supprimés selon la procédure prévue. Une capture avec secrets intégrés ou associée à un fichier de clés ne doit pas être partagée sans analyse de risque et autorisation.

### 26.5 Lua Debugger et Lua Console

- **Lua Debugger** aide à examiner et dépanner des scripts Lua utilisés avec Wireshark.
- **Lua Console** donne accès à l’interpréteur Lua intégré lorsque cette prise en charge est disponible.

Ces fonctions s’adressent surtout aux personnes qui développent ou maintiennent des extensions. N’exécute pas un script Lua inconnu sur une machine de production ; lis le code et teste-le dans un environnement contrôlé.

## 27. Menu Help / Aide

Le menu **Help** sert à trouver la documentation et les informations de diagnostic sur l’installation.

| Entrée | Utilité |
|---|---|
| **User’s Guide** (`F1`) | Ouvre le guide utilisateur correspondant à la version documentée. |
| **Manual Pages → …** | Ouvre les pages de manuel locales disponibles pour les outils en ligne de commande, comme `tshark` ou `dumpcap`. Le sous-menu dépend des composants installés. |
| **Website** | Ouvre le site officiel Wireshark. |
| **FAQs** | Ouvre les réponses aux questions fréquentes. |
| **Downloads** | Ouvre la page officielle de téléchargement. |
| **Wiki** | Ouvre le wiki Wireshark, qui contient des informations et exemples communautaires ; vérifie les points sensibles dans la documentation officielle. |
| **Sample Captures** | Ouvre des captures d’exemple utiles pour apprendre sans utiliser de données réelles. Lis la licence et les conditions d’utilisation de chaque fichier. |
| **Release Notes** | Affiche les changements et corrections de la version courante. Utile pour vérifier qu’un menu ou un champ a changé. |
| **About Wireshark** | Affiche la version, les bibliothèques, plugins, composants et chemins utilisés. Les onglets disponibles peuvent aider à diagnostiquer un codec ou un plugin absent. |
| **Check for Updates → …** | Vérifie les mises à jour via l’outil intégré sur les plateformes où il est fourni ; la documentation actuelle indique Windows et macOS. Sous Kali/Parrot, les mises à jour passent par APT et les dépôts configurés. |

Les liens Web peuvent être masqués si le navigateur n’est pas configuré ou si la version ne les expose pas. Tu peux toujours consulter le guide dans un navigateur en allant directement sur le site officiel.

## 28. Règles pratiques pour les fonctions spécialisées

1. **Une commande absente ou grisée est souvent contextuelle.** Sélectionne un paquet du bon protocole et vérifie que Wireshark l’a décodé.
2. **La capture détermine la limite de l’analyse.** Les menus avancés ne peuvent pas reconstruire des paquets absents.
3. **Les outils d’extraction peuvent dévoiler des données confidentielles.** Vérifie le fichier avant de copier, exporter ou publier.
4. **Une sortie générée est à valider.** C’est particulièrement vrai pour les règles de pare-feu, les fichiers extraits, les statistiques et les interprétations de voix.
5. **Consigne la version et les plugins.** Une différence entre Windows, Kali et Parrot peut venir de la version, des codecs, des permissions ou des paquets installés.

## Références officielles pour cette partie

- Menu Telephony : https://www.wireshark.org/docs/wsug_html_chunked/ChUseTelephonyMenuSection.html
- Appels VoIP : https://www.wireshark.org/docs/wsug_html_chunked/ChTelVoipCalls.html
- RTP : https://www.wireshark.org/docs/wsug_html_chunked/ChTelRTP.html
- Menu Wireless : https://www.wireshark.org/docs/wsug_html_chunked/ChUseWirelessMenuSection.html
- WLAN Traffic : https://www.wireshark.org/docs/wsug_html_chunked/ChWirelessWLANTraffic
- Bluetooth Devices : https://www.wireshark.org/docs/wsug_html_chunked/ChWirelessBluetoothDevices.html
- Menu Tools : https://www.wireshark.org/docs/wsug_html_chunked/ChUseToolsMenuSection.html
- Menu Help : https://www.wireshark.org/docs/wsug_html_chunked/ChUseHelpMenuSection

# Partie III — Barres, panneaux, menus contextuels et réglages

## 29. Barre d’outils principale

La barre principale regroupe des boutons pour les actions fréquentes. Elle reprend des commandes déjà présentes dans les menus : elle ne constitue pas un moteur d’analyse différent.

Les boutons sont activés ou grisés selon le contexte. Par exemple, **Stop** ne sert que pendant une capture ; certaines actions de fichier nécessitent qu’une capture soit ouverte. Si un bouton est grisé, regarde si le bon fichier, paquet ou état de capture est actif.

Les boutons visibles peuvent varier selon la version et le système. La barre principale documentée comprend notamment les commandes de début, d’arrêt et de redémarrage de capture, ainsi que l’ouverture et l’enregistrement de fichiers. Elle peut être masquée par **View → Main Toolbar** pour agrandir les panneaux.

## 30. Barre de filtre d’affichage

La barre **Filter** est l’endroit où saisir ou choisir un **display filter**. Elle ne modifie pas le contenu du PCAP : elle détermine quelles lignes sont affichées.

| Élément | Fonction |
|---|---|
| **Bookmarks** | Gérer ou choisir des filtres enregistrés. Les filtres de capture et d’affichage sont des listes différentes. |
| **Filter Input** | Saisir ou modifier une expression de filtre. Wireshark vérifie la syntaxe pendant la saisie. |
| **Fond rouge** | La saisie est invalide ou incomplète ; il faut la corriger avant de l’appliquer. |
| **Fond vert** | L’expression est reconnue comme valide. Cela confirme la syntaxe, pas que le filtre répond bien à la question métier. |
| **Apply** / Entrée | Appliquer le filtre à la liste affichée. Sur une très grosse capture, le calcul peut prendre du temps. |
| **Clear** | Retirer le filtre courant et réafficher les paquets, sous réserve des options d’affichage. |
| **Recent** | Choisir parmi les derniers filtres appliqués. |
| **Add Button (+)** | Créer un bouton de filtre réutilisable. |
| **Filter Button** | Appliquer immédiatement le filtre associé au bouton. Les boutons peuvent être regroupés avec `//` dans leur libellé, par exemple `TCP//SYN` et `TCP//RST`. |

### 30.1 Une erreur typique à éviter

Un filtre valide peut retourner zéro paquet. Cela ne signifie pas automatiquement que le trafic n’a jamais existé : le filtre peut viser la mauvaise interface, le mauvais sens, une syntaxe trop restrictive, un paquet absent ou un protocole non décodé. Commence par une expression simple, vérifie les champs observés dans un paquet, puis ajoute les conditions une à une.

### 30.2 Enregistrer un filtre

Les listes de filtres enregistrés servent à éviter les fautes de frappe et à garder des filtres réutilisables. Pour créer une entrée, donne-lui un nom lisible, puis distingue clairement sa famille : par exemple `CAP - DNS UDP` et `DISP - DNS requêtes`. Le nom est une étiquette pour l’utilisateur ; c’est l’expression qui détermine le filtrage.

## 31. Panneaux de la capture

### 31.1 Packet List — liste des paquets

Chaque ligne représente un paquet ou une trame du fichier courant. Sélectionner une ligne met à jour les panneaux Détails et Octets. Les colonnes par défaut comprennent généralement :

- **No.** : numéro dans la capture originale ; il ne change pas lorsque le filtre masque des lignes ;
- **Time** : horodatage selon le format choisi ;
- **Delta** : temps relatif au paquet précédent affiché dans la présentation courante ;
- **Source / Destination** : adresses associées au paquet, selon le décodage et les colonnes ;
- **Protocol** : protocole principal ou le plus haut niveau reconnu ;
- **Length** : longueur rapportée par l’analyseur selon les données disponibles ;
- **Info** : résumé textuel du contenu décodé.

Les dissectors des couches supérieures peuvent remplacer dans les colonnes certaines informations des couches inférieures. Ainsi, la colonne Protocol ne décrit pas forcément toutes les couches présentes. Il faut ouvrir le panneau Détails pour voir l’arbre complet.

La première colonne peut afficher des symboles de relation : début/fin de conversation, requête/réponse, accusé de réception, retransmission ou réassemblage. Ce sont des aides visuelles fondées sur le décodage ; elles ne remplacent pas l’examen des paquets liés.

### 31.2 Colonnes personnalisées

On peut ajouter une colonne depuis un champ du panneau Détails avec **Apply as Column**, ou configurer les colonnes dans **Preferences → Appearance → Columns**. Une colonne personnalisée peut afficher un champ tel que port, nom DNS, indicateur TCP, processus ou valeur de protocole si ce champ existe dans la version et la capture.

Utilise les colonnes pour comparer rapidement des paquets en série. Elles sont moins adaptées aux valeurs ambiguës ou répétées : vérifie le champ sous-jacent et son occurrence quand un protocole contient plusieurs occurrences du même champ.

### 31.3 Packet Details — détails du paquet

Le panneau **Packet Details** présente l’arbre des protocoles et des champs pour la ligne sélectionnée. Déplie une couche à la fois : Ethernet, IP, TCP/UDP, puis application. Chaque champ a une valeur et souvent une définition qui apparaît dans la barre d’état lorsqu’il est sélectionné.

Deux éléments demandent une attention particulière :

- Les champs calculés par Wireshark sont parfois entre crochets. Ils sont produits par l’analyseur à partir des données ; ils ne sont pas forcément des octets transmis tels quels.
- Les champs bleus soulignés peuvent être des liens vers un paquet correspondant. Un double-clic permet de suivre cette relation.

Exemple : un temps de réponse ou une indication d’analyse TCP peut être calculé à partir de plusieurs paquets. Pour un rapport, précise si tu cites une valeur brute de la trame ou une valeur dérivée par Wireshark.

### 31.4 Packet Bytes — octets du paquet

Le panneau **Packet Bytes** affiche un dump hexadécimal : l’offset, les octets en hexadécimal et une colonne de caractères lisibles. Les octets non imprimables sont remplacés par un point. Quand tu sélectionnes un champ dans Détails, Wireshark met en évidence les octets associés.

Plusieurs onglets peuvent apparaître si Wireshark a réassemblé des données réparties sur plusieurs paquets ou produit une vue déchiffrée. Ces onglets secondaires sont des sources de données reconstituées : ils ne doivent pas être confondus avec les octets bruts de la trame d’origine.

Dans un paquet où une chaîne est visible en ASCII, cela ne veut pas automatiquement dire qu’elle forme un message complet ou qu’elle est sûre à utiliser. L’encodage, le découpage, le protocole et le contexte comptent.

### 31.5 Packet Diagram — diagramme de paquet

Le panneau **Packet Diagram**, s’il est disponible et activé, dessine les couches et champs de premier niveau dans une présentation proche des diagrammes pédagogiques. Il est utile pour comprendre la structure, faire une capture d’écran de cours ou illustrer une analyse.

Il ne montre pas nécessairement tous les détails comme l’arbre complet ou chaque octet. Utilise Détails pour lire un champ précis et Octets pour vérifier sa représentation brute.

## 32. Barre d’état

La barre d’état résume l’état courant. Selon l’espace et la version, elle montre :

- un message de contexte ou le nom du fichier ;
- un indicateur Expert Info correspondant au niveau le plus élevé trouvé ; cliquer dessus ouvre la fenêtre Expert Info ;
- le nombre total de paquets capturés, le nombre affiché après filtre, les paquets marqués et ignorés ;
- les paquets perdus, lorsqu’une perte de capture est connue ;
- le profil de configuration actif ; cliquer sur cette zone permet de changer de profil ;
- le nom du champ de filtre associé à l’élément sélectionné dans Détails.

Les compteurs **Captured**, **Displayed**, **Marked**, **Dropped** et **Ignored** ne signifient pas la même chose. En particulier, « Displayed » peut être inférieur à « Captured » simplement à cause du filtre courant. « Dropped » signale une perte de capture rapportée par le mécanisme concerné ; l’absence de compteur non nul ne prouve pas que la capture est parfaite.

## 33. Menus contextuels — clic droit

Un clic droit ouvre un menu adapté à l’endroit où tu te trouves. C’est souvent le chemin le plus rapide vers une fonction, mais le contenu dépend du champ, du paquet, du protocole et de la version.

### 33.1 Dans l’en-tête d’une colonne

On peut aligner le texte, redimensionner la colonne, la figer avec celles à gauche, changer son affichage, la modifier dans les préférences, la masquer ou la retirer. Ces actions modifient la présentation, pas le PCAP.

### 33.2 Dans la liste des paquets

Le menu peut proposer : marquer/ignorer le paquet, fixer une référence temporelle, épingler une ligne, modifier l’heure, ajouter un commentaire, créer/appliquer/préparer un filtre, générer un filtre de conversation, colorer une conversation, suivre un flux, copier résumé ou octets, changer les préférences de protocole, faire un **Decode As** ou ouvrir le paquet dans une fenêtre séparée.

Le sous-menu **Copy** peut produire du texte tabulé, CSV, YAML, un filtre ou différentes représentations des octets. Vérifie toujours le contenu du presse-papiers avant de le coller dans un ticket ou un document partagé.

### 33.3 Dans les détails du paquet

Selon le champ sélectionné, le menu permet d’appliquer ou préparer un filtre, créer une colonne ou une règle de couleur, suivre un flux, copier la description, le nom de champ ou la valeur, exporter des octets, ouvrir une page de référence, ajuster les préférences du protocole, faire un **Decode As** ou naviguer vers un paquet lié.

Un clic droit sur `ip.src`, par exemple, fournit des opérations cohérentes avec une adresse IP ; un clic droit sur un indicateur TCP propose d’autres choix. Le champ sélectionné change donc les options présentées.

### 33.4 Dans la zone d’octets

Les options de copie comprennent notamment dump hexadécimal, texte imprimable, flux hexadécimal sans séparateurs, binaire brut ou chaîne échappée. L’affichage peut être basculé en hexadécimal ou binaire, et le texte associé peut être montré en ASCII, EBCDIC ou UTF-8 selon les options disponibles.

Le texte imprimable est une interprétation de certains octets ; il peut être incomplet, trompeur ou contenir des données confidentielles. Copie seulement ce dont tu as besoin.

### 33.5 Dans le diagramme

Le menu peut afficher les valeurs de champs sur le diagramme, enregistrer celui-ci comme image ou le copier comme image matricielle. Avant de publier une image, vérifie qu’elle ne montre pas d’adresse, de nom interne, d’identifiant ou de données sensibles.

## 34. Preferences / Préférences

Les préférences règlent l’apparence et le comportement de Wireshark. Elles ne sont pas toutes nécessaires pour apprendre. Modifie un réglage à la fois et note sa valeur d’origine lorsqu’il peut influencer l’interprétation.

Les catégories les plus utiles à connaître sont :

- **Appearance** : langue de l’interface, démarrage, historique, confirmation avant fermeture, complétion de filtre, colonnes, disposition des panneaux, thème et police.
- **Columns** : titre, type, champ associé, occurrence, résolution de nom, largeur et alignement. Les colonnes sont une aide à la lecture.
- **Layout** : emplacement des panneaux, lisibilité et comportement de la liste.
- **Capture** : interface par défaut, mode promiscuité/moniteur, format PCAPNG, enregistrement de processus, rafraîchissement et sources de capture externes.
- **Filter Buttons** : raccourcis d’affichage créés par l’utilisateur.
- **Name Resolution** : conversion d’adresses numériques en noms. La résolution réseau peut solliciter DNS selon les réglages ; dans une analyse forensique stricte, cela peut introduire du trafic extérieur et compliquer la reproductibilité.
- **Protocols** : options propres à chaque dissector. Un changement peut modifier ce qui est décodé et certaines statistiques.
- **Expert Items** : réglages liés à la sévérité d’éléments Expert dans les préférences. Une sévérité personnalisée modifie la présentation de l’alerte, pas le paquet réseau.
- **User Interface** : options de disposition et de navigation qui peuvent évoluer avec la version.

Les noms exacts des catégories et réglages varient avec les versions et les builds. La fenêtre **Help → About Wireshark** permet de noter la version et les composants disponibles.

## 35. Configuration Profiles / Profils

Un profil regroupe des préférences pour travailler avec une configuration adaptée. Wireshark peut conserver par profil des filtres de capture et d’affichage, macros de filtre, règles de couleur, protocoles désactivés, associations Decode As, colonnes et certaines dispositions récentes.

Exemples de profils utiles :

- **Default** : environnement neutre ; garde-le comme point de retour.
- **Apprentissage** : colonnes simples, thème lisible, filtres de base.
- **SOC** : colonnes source/destination/ports, boutons de filtres utiles et couleurs cohérentes.
- **Wireless** ou **Processes** : profils globaux fournis dans certaines distributions, adaptés à des captures spécifiques.

Depuis **Edit → Configuration Profiles…**, tu peux créer, copier, supprimer, importer ou exporter des profils personnels. Le profil actif est également visible dans la barre d’état. Avant de partager un profil, vérifie qu’il ne contient pas de filtre, de commentaire ou de chemin interne que tu souhaites garder privé.

### 35.1 Bon usage des profils

1. Garde le profil par défaut aussi proche que possible de son état initial.
2. Copie-le pour créer un profil de travail.
3. Change les colonnes, filtres et couleurs dans le nouveau profil.
4. Note les filtres associés au profil et ce qu’ils signifient.
5. Exporte le profil seulement après l’avoir vérifié sur une capture d’exemple.

## Références officielles pour cette partie

- Barre principale : https://www.wireshark.org/docs/wsug_html_chunked/ChUseMainToolbarSection
- Barre de filtre : https://www.wireshark.org/docs/wsug_html_chunked/ChUseFilterToolbarSection.html
- Liste des paquets : https://www.wireshark.org/docs/wsug_html_chunked/ChUsePacketListPaneSection.html
- Détails du paquet : https://www.wireshark.org/docs/wsug_html_chunked/ChUsePacketDetailsPaneSection
- Octets du paquet : https://www.wireshark.org/docs/wsug_html_chunked/ChUsePacketBytesPaneSection.html
- Diagramme de paquet : https://www.wireshark.org/docs/wsug_html_chunked/ChUsePacketDiagramPaneSection.html
- Barre d’état : https://www.wireshark.org/docs/wsug_html_chunked/ChUseStatusbarSection
- Menus contextuels : https://www.wireshark.org/docs/wsug_html_chunked/ChWorkDisplayPopUpSection.html
- Préférences : https://www.wireshark.org/docs/wsug_html_chunked/ChCustPreferencesSection.html
- Profils : https://www.wireshark.org/docs/wsug_html_chunked/ChCustConfigProfilesSection.html

# Partie IV — Capturer proprement

## 36. Choisir l’interface et le mode de capture

Une capture commence par une question, pas par un bouton. Avant de démarrer, écris en une phrase ce que tu veux observer : « Je veux voir la requête DNS émise par ma VM vers son résolveur pendant l’ouverture du site de test. » Cette phrase indique un équipement, une interface, un protocole et une période.

### 36.1 Procédure de choix de l’interface

1. Identifie la machine qui émet ou reçoit le trafic.
2. Liste ses interfaces : Ethernet, Wi-Fi, loopback, VPN, adaptateurs virtuels.
3. Vérifie les adresses IP de chaque interface et compare-les à la topologie du laboratoire.
4. Observe l’indicateur d’activité pendant que tu génères un trafic contrôlé.
5. Capture quelques secondes et vérifie si les adresses attendues apparaissent.
6. Si le trafic manque, change d’interface ou de point de capture avant de conclure qu’il n’a pas eu lieu.

L’interface qui montre le plus d’activité n’est pas forcément la bonne. Les mises à jour, la synchronisation, les diffusions ou un VPN peuvent produire beaucoup de trafic sans rapport avec la question.

### 36.2 Mode normal, mode promiscuité et mode moniteur

- **Mode normal** : la carte remet principalement au système les trames qui lui sont destinées, plus certains trafics de diffusion/multidiffusion.
- **Mode promiscuité** : demande à une interface Ethernet de remettre à l’analyseur les trames qu’elle reçoit même si elles ne sont pas destinées à son adresse MAC. Cela ne force pas un commutateur à envoyer les conversations des autres ports vers le poste de capture.
- **Mode moniteur Wi-Fi** : demande à l’interface sans fil une observation radio plus complète des trames 802.11 et des informations associées. Le support dépend du chipset, du pilote, du système et du canal. Il peut interrompre la connexion Wi-Fi normale.

Ces modes répondent à des besoins différents. Le terme « promiscuité » ne signifie pas « voir tout le réseau ».

## 37. Capture filter — filtrer avant l’enregistrement

Un **capture filter** utilise la syntaxe libpcap/BPF. Il décide quels paquets le mécanisme de capture remet au programme et conserve. Les paquets exclus ne seront pas récupérables dans ce fichier.

### 37.1 Primitives courantes

| Besoin | Exemple de filtre de capture | Sens |
|---|---|---|
| Un hôte source ou destination | `host 192.0.2.10` | Paquets où cette adresse est source ou destination |
| Un hôte seulement source | `src host 192.0.2.10` | Paquets envoyés depuis cet hôte |
| Un réseau | `net 192.0.2.0/24` | Paquets dont une adresse appartient à ce préfixe |
| TCP ou UDP port 443 | `port 443` | Port 443 en source ou destination pour TCP/UDP |
| TCP destination 443 | `tcp dst port 443` | Paquets TCP dont le port destination est 443 |
| DNS classique UDP/TCP | `port 53` | Trafic TCP ou UDP sur le port 53 ; ne couvre pas à lui seul tous les DNS chiffrés ou non standards |
| Une adresse MAC | `ether host 00:11:22:33:44:55` | Trames dont l’adresse Ethernet correspond en source ou destination |
| Combiner hôte et service | `host 192.0.2.10 and tcp port 443` | Les deux conditions doivent correspondre |
| Exclure une source | `tcp port 23 and not src host 192.0.2.10` | Telnet TCP sauf les paquets envoyés par cet hôte |
| Choisir plusieurs ports | `(tcp port 80 or tcp port 443)` | HTTP/HTTPS TCP classiques, avec parenthèses pour rendre la logique claire |

Les adresses `192.0.2.0/24` et MAC ci-dessus sont des valeurs d’exemple pour la documentation ; remplace-les par les valeurs de ton laboratoire autorisé.

### 37.2 Logique et erreurs courantes

Les mots-clés logiques usuels sont `and`, `or` et `not`. Utilise des parenthèses lorsqu’une expression combine plusieurs conditions. Les primitives `src` et `dst` précisent le sens de l’adresse ou du port.

Erreurs fréquentes :

- saisir une expression de filtre d’affichage comme `ip.addr == 192.0.2.10` dans le champ de capture ;
- oublier que `port 53` ne concerne pas nécessairement toutes les formes de DNS ;
- filtrer seulement un sens et manquer la réponse ;
- choisir un port supposé alors que l’application utilise un port non standard ;
- appliquer un filtre restrictif avant d’avoir compris le trafic attendu.

### 37.3 Quand mettre un capture filter ?

Mets un filtre de capture lorsque la quantité de données, la confidentialité ou le stockage l’exige, et que tu connais le périmètre à conserver. Au début d’une investigation, capture plutôt un périmètre autorisé et raisonnable puis filtre l’affichage. Cela garde la possibilité de reformuler la question après avoir vu les premiers échanges.

Avant de lancer une capture importante, saisis le filtre dans la fenêtre Capture Options, vérifie que Wireshark l’accepte, puis examine la sortie BPF compilée si le résultat est inattendu. Une syntaxe acceptée peut toujours être logiquement trop étroite.

## 38. Capture Options — les réglages à comprendre

La fenêtre **Capture → Options** rassemble l’interface, le filtre, les options d’entrée, la destination et le comportement d’affichage.

### 38.1 Entrée

- **Interface** : sélectionne une ou plusieurs sources de capture.
- **Traffic** : indicateur d’activité pour aider au choix.
- **Link-layer Header** : type d’en-tête enregistré, par exemple Ethernet ou 802.11 lorsque disponible.
- **Promiscuous** : mode promiscuité, sous réserve du réseau et de l’interface.
- **Snaplen** : longueur maximale conservée par paquet. Une troncature peut empêcher d’analyser les données applicatives.
- **Buffer** : tampon noyau utilisé pour absorber les paquets avant leur traitement. Le réglage par défaut est généralement préférable tant qu’un problème de perte n’est pas mesuré.
- **Monitor Mode** : options spécifiques Wi-Fi lorsque supportées.
- **Capture Filter** : expression BPF appliquée avant stockage.

### 38.2 Sortie

- **File** : chemin d’enregistrement. Un fichier temporaire est utilisé si aucun chemin permanent n’est indiqué.
- **Format** : PCAPNG est le format par défaut actuel et prend en charge plusieurs interfaces et plus de métadonnées que le PCAP historique. Certains outils tiers peuvent toutefois mieux accepter PCAP ; vérifie les besoins d’échange avant conversion.
- **Processes** : peut enregistrer un lien entre les paquets TCP/UDP et des processus locaux, si le système et les privilèges le permettent. Le chemin exécutable, l’utilisateur ou la ligne de commande peuvent révéler des informations sensibles, y compris un mot de passe passé en argument.
- **Create a new file automatically…** : démarre un nouveau fichier à une limite choisie, par exemple temps, taille ou nombre de paquets.
- **Use a ring buffer with…** : limite le nombre de fichiers utilisés en réécrivant le plus ancien lorsque le tampon circulaire est plein.

### 38.3 Enregistrement et fichiers découpés

- **Fichier temporaire unique** : pratique pour une courte expérimentation ; il faut ensuite enregistrer le résultat au bon endroit.
- **Fichier nommé unique** : facile à retrouver, mais peut grossir beaucoup.
- **Plusieurs fichiers continus** : sépare une capture longue en morceaux successifs sans effacer les premiers.
- **Plusieurs fichiers en ring buffer** : limite l’espace consommé et garde les données les plus récentes, mais écrase les fichiers les plus anciens.

Le découpage rend les fichiers plus faciles à manipuler, mais peut séparer le début d’une session de la suite. Si Wireshark n’a pas le paquet d’établissement TCP ou la signalisation d’un flux, certaines vues reconstituées peuvent perdre du contexte.

### 38.4 Options d’affichage et arrêt automatique

- **Update list of packets in real-time** : actualise la liste pendant la capture ; cela consomme du CPU pour décoder et afficher.
- **Automatically scroll during live capture** : suit les paquets les plus récents.
- **Show capture information during capture** : présente des compteurs d’état.
- **Name Resolution** : peut demander des résolutions de noms selon la configuration ; désactive-la si tu veux minimiser les interactions extérieures ou conserver une analyse strictement numérique.
- **Stop capture automatically after…** : arrête selon un nombre de paquets/fichiers, une taille ou une durée.

Le mécanisme de capture ne sait pas, dans la fenêtre graphique, arrêter automatiquement selon le contenu sémantique d’un paquet comme « arrêter quand cette URL apparaît ». Pour cela, il faut une méthode d’analyse ou d’automatisation adaptée.

### 38.5 Préparer une capture longue

Avant une collecte longue, vérifie l’espace disque libre, fixe des limites de taille et de durée, décide si les anciens fichiers peuvent être remplacés, protège le répertoire et note le fuseau horaire. Une capture longue peut contenir des données non pertinentes ou sensibles : le principe de minimisation doit guider le périmètre et la durée.

## 39. Choisir un point de capture

Le point de capture répond à la question « depuis quel endroit observons-nous les paquets ? ». Deux captures simultanées prises à deux endroits différents peuvent légitimement montrer des paquets différents.

| Point de capture | Ce qu’il est utile d’observer | Limite principale |
|---|---|---|
| Poste client | Ce que l’application du poste envoie et reçoit localement | Peut voir des effets du pare-feu, VPN, offload ou de la pile réseau du poste |
| Serveur | Les échanges reçus et envoyés par le service | Ne montre pas nécessairement tout ce qui se passe entre client et serveur |
| Port miroir/SPAN du commutateur | Trafic copié depuis certains ports ou VLAN selon configuration | Un mauvais filtrage, une direction oubliée ou une surcharge du port miroir peut manquer des paquets |
| TAP réseau | Copie passive du trafic d’un lien selon l’équipement utilisé | Nécessite matériel, emplacement et accès adaptés |
| Hyperviseur / interface virtuelle | Trafic d’une VM ou d’un segment virtuel | Visibilité dépend du mode de réseau et du commutateur virtuel |
| Routeur / pare-feu | Trafic qui traverse certaines interfaces ou politiques | Le NAT, le chiffrement et les règles peuvent changer les adresses ou limiter la visibilité |

### 39.1 Capture sur réseau Ethernet commuté

Sur un switch, le trafic unicast entre deux autres ports n’est pas envoyé automatiquement à l’ordinateur qui lance Wireshark. Le mode promiscuité n’outrepasse pas cette règle de commutation. Pour observer un trafic qui ne concerne pas le poste, il faut un point qui le reçoit réellement : port miroir configuré par l’administrateur, TAP, équipement de capture ou capture sur un hôte concerné.

Ne change pas la configuration d’un réseau de production pour « voir si ça marche » sans plan, autorisation et méthode de retour arrière. Un port miroir mal configuré peut surcharger la destination ou exposer des données à un poste non autorisé.

### 39.2 Captures distantes

Wireshark peut gérer des interfaces distantes avec des mécanismes dédiés lorsque le service correspondant tourne sur la cible. Les options d’authentification et le transport doivent être vérifiés. Une capture distante sans authentification n’est pas sécurisée ; préfère un tunnel SSH lorsque la procédure et la plateforme le permettent. Ne publie pas les identifiants d’accès ni l’adresse de gestion dans le PCAP ou le rapport.

## 40. Wi-Fi : limites et prérequis

### 40.1 Capture depuis une carte connectée au Wi-Fi

En mode normal, Wireshark voit surtout le trafic de la machine, ainsi que certaines trames de diffusion/multidiffusion. Cela ne signifie pas qu’il reçoit toutes les communications radio des autres stations.

### 40.2 Capture en mode moniteur

Le mode moniteur peut fournir des en-têtes 802.11 et des trames de gestion/contrôle selon l’adaptateur, le pilote, le système et le canal configuré. Il peut déconnecter la carte du réseau. Sous Windows, les capacités et options dépendent du pilote Npcap et du matériel ; sous Linux, elles dépendent du pilote et de la pile sans-fil.

Une capture radio peut manquer des trames si la carte écoute sur le mauvais canal ou ne peut pas suivre plusieurs canaux à la fois. Une absence dans le fichier n’est donc pas la preuve que la trame n’a pas été émise.

### 40.3 Chiffrement Wi-Fi

Voir des trames 802.11 ne signifie pas voir le contenu applicatif en clair. Le chiffrement Wi-Fi et le chiffrement TLS sont deux couches différentes. Pour analyser le contenu, il faut les conditions de capture, le contexte et les clés de déchiffrement autorisées. Le cours traitera le déchiffrement Wi-Fi dans une partie spécifique, avec les précautions nécessaires pour les secrets.

## 41. Captures multi-interfaces et horodatages

Wireshark peut capturer simultanément depuis plusieurs interfaces. PCAPNG est utile pour conserver l’identifiant de l’interface associé à chaque paquet.

Avant de combiner plusieurs points, considère :

- chaque interface peut avoir une horloge ou une précision d’horodatage différente ;
- les mêmes paquets peuvent apparaître deux fois si les points se recouvrent ;
- un paquet peut être observé avant et après NAT, encapsulation ou pare-feu ;
- le port miroir peut recevoir plus de trafic que sa capacité et perdre des paquets ;
- la segmentation de capture peut séparer le contexte d’un flux.

Pour comparer deux traces, note la machine, l’interface, l’emplacement, l’heure UTC ou locale et la synchronisation de l’horloge. Ne fusionne pas les fichiers avant d’avoir conservé les originaux et compris leurs timestamps.

## 42. Pourquoi une capture peut être incomplète ou trompeuse

Une capture n’est pas une copie parfaite de « tout le réseau ». Des paquets peuvent manquer à plusieurs étapes :

1. **Mauvais point d’observation** : le trafic ne passe pas par l’interface surveillée.
2. **Mauvaise interface** : VPN, Wi-Fi ou carte virtuelle mal choisi.
3. **Filtre trop étroit** : le paquet a été rejeté avant l’écriture du fichier.
4. **Pertes au niveau du pilote, du buffer ou de la charge CPU** : le système n’a pas remis tous les paquets à Wireshark.
5. **Port miroir surchargé** : plusieurs liens produisent plus de trafic que le lien de destination ne peut transmettre.
6. **Snaplen trop court** : seule une partie des octets a été enregistrée.
7. **Capture commencée trop tard ou arrêtée trop tôt** : handshake, requête ou réponse manquante.
8. **Limite du support** : Wi-Fi, VLAN, tunnel, encapsulation, offload ou virtualisation change ce qui est visible.
9. **Résolution/décodage différent** : les données sont présentes mais Wireshark ne les interprète pas comme attendu.

### 42.1 Distinguer quatre notions

- **Paquet absent du fichier** : Wireshark ne peut pas l’analyser.
- **Paquet présent mais caché** : un filtre d’affichage le masque ; effacer le filtre le fait réapparaître.
- **Paquet partiellement capturé** : le début existe, mais le snaplen ou une troncature a coupé le reste.
- **Paquet présent mais non décodé** : les octets sont là, mais le protocole est inconnu, mal identifié ou non disséqué.

Avant d’écrire « le serveur n’a pas répondu », vérifie que la capture couvrait le bon lien, le bon sens, toute la durée et le protocole concerné. Si possible, compare avec une capture à l’autre extrémité et avec les journaux du serveur.

## Checklist avant de cliquer sur Start

- [ ] Autorisation et objectif écrits.
- [ ] Point d’observation défini.
- [ ] Interface confirmée par son nom, ses adresses et un test bref.
- [ ] Mode promiscuité/moniteur activé seulement si nécessaire et supporté.
- [ ] Capture filter relu et validé ; aucune condition inutile.
- [ ] Format, nom, dossier, durée, taille et limites de fichiers définis.
- [ ] Secrets ou métadonnées de processus non collectés sans besoin.
- [ ] Espace disque et méthode d’arrêt vérifiés.
- [ ] Heure, fuseau, interfaces et version consignés pour le rapport.

## Références officielles pour cette partie

- Prérequis de capture : https://www.wireshark.org/docs/wsug_html_chunked/ChCapPrerequisitesSection.html
- Options de capture : https://www.wireshark.org/docs/wsug_html_chunked/ChCapCaptureOptions.html
- Filtres de capture : https://www.wireshark.org/docs/wsug_html_chunked/ChCapCaptureFilterSection.html
- Fichiers et ring buffer : https://www.wireshark.org/docs/wsug_html_chunked/ChCapCaptureFiles.html
- Gestion des interfaces : https://www.wireshark.org/docs/wsug_html_chunked/ChCapManageInterfacesSection.html
- Configuration des couches liaison : https://www.wireshark.org/docs/wsug_html_chunked/ChCapLinkLayerHeader.html
- Guide Wi-Fi : https://wiki.wireshark.org/CaptureSetup/WLAN
- Guide Ethernet : https://wiki.wireshark.org/CaptureSetup/Ethernet
+# Partie V — Lire et filtrer

## 43. Display filter — filtrer l’affichage

Un **display filter** choisit les paquets visibles dans la fenêtre. Il ne supprime pas les autres paquets du fichier. C’est comme poser un filtre sur une lampe : les objets cachés derrière le filtre sont toujours dans la pièce.

La barre de filtre d’affichage est généralement en haut de la fenêtre. Saisis l’expression puis appuie sur Entrée ou utilise le bouton d’application. Une expression invalide est signalée par l’interface ; une expression valide peut ne retourner aucun paquet, ce qui est différent d’une erreur de syntaxe.

Exemples pour commencer :

| Question | Filtre | À retenir |
|---|---|---|
| Voir les paquets DNS décodés | `dns` | Montre le protocole DNS s’il est correctement décodé |
| Voir HTTP classique | `http` | Ne signifie pas « tout le trafic Web » ; HTTPS est chiffré et HTTP/2 ou HTTP/3 peuvent avoir d’autres champs |
| Voir TCP | `tcp` | Affiche les paquets reconnus comme TCP |
| Voir une adresse IPv4 en source ou destination | `ip.addr == 192.0.2.10` | Le champ couvre les deux sens |
| Voir seulement une source IPv4 | `ip.src == 192.0.2.10` | La réponse peut avoir cette adresse en destination |
| Voir le port 443 en TCP ou UDP | `tcp.port == 443 || udp.port == 443` | Les deux expressions couvrent séparément les transports |
| Voir les débuts de connexion TCP | `tcp.flags.syn == 1 && tcp.flags.ack == 0` | Indice de début, pas preuve d’un scan |
| Voir les retransmissions signalées | `tcp.analysis.retransmission` | Dépend des paquets présents dans la capture |
| Voir les requêtes pour un nom DNS | `dns.qry.name == "example.org"` | Vérifie le nom effectivement décodé |

Les adresses réservées à la documentation, comme `192.0.2.10` et `example.org`, sont des exemples. Remplace-les par les valeurs de ton laboratoire.

### 43.1 Une méthode sûre en trois gestes

1. Commence par un filtre large, par exemple `dns` ou `tcp`.
2. Ajoute une condition à la fois, puis vérifie que les paquets attendus restent visibles.
3. Efface le filtre pour revenir à l’ensemble du fichier et contrôle les paquets voisins avant de conclure.

Un filtre de confort peut rendre une capture très lisible, mais il peut aussi cacher la réponse, le paquet précédent ou le contexte d’une alerte. Note l’expression exacte utilisée et le nombre de paquets affichés.

## 44. Syntaxe des filtres d’affichage

Le filtre d’affichage utilise les **noms de champs de Wireshark**, pas les mots de la syntaxe BPF. Les champs sont fournis par les dissectors. L’autocomplétion et **Display Filter Expression** aident à retrouver un nom de champ et les valeurs attendues.

### 44.1 Champs, protocoles et valeurs

- `tcp` ou `dns` teste la présence d’un protocole décodé.
- `ip.src` est un champ d’adresse source IPv4 ; `ipv6.src` est son équivalent IPv6.
- `tcp.dstport` est le port TCP de destination ; `udp.dstport` est le port UDP de destination.
- `dns.qry.name` contient le nom demandé dans une requête DNS.

Le champ `ip.addr` est pratique pour « source OU destination ». Un champ directionnel (`ip.src`, `ip.dst`) répond à une question différente. Si une conversation va dans les deux sens, filtrer seulement `ip.src` ne montrera pas les paquets de retour.

Les noms exacts peuvent évoluer entre versions ou différer selon le dissector. Dans la fenêtre de détails, sélectionne un champ puis utilise le menu contextuel **Apply as Filter** ou **Prepare a Filter**. Wireshark construit un filtre à partir du champ décodé.

### 44.2 Comparaisons et logique

Les comparateurs usuels sont `==`, `!=`, `>`, `<`, `>=` et `<=`. Les opérateurs logiques sont `&&` (ET), `||` (OU) et `!` (NON). Les mots `and`, `or` et `not` sont aussi acceptés.

| Intention | Exemple | Lecture simple |
|---|---|---|
| ET | `tcp && ip.addr == 192.0.2.10` | TCP et l’adresse apparaît d’un côté ou de l’autre |
| OU | `dns || dhcp` | DNS ou DHCP |
| NON | `tcp && !tcp.analysis.retransmission` | TCP, sauf les retransmissions signalées |
| Comparaison | `tcp.len > 0` | Segment TCP ayant des données |
| Présence | `dns.qry.name` | Paquets où ce champ existe |

Utilise des parenthèses quand le filtre mélange ET et OU. Par exemple, `(ip.addr == 192.0.2.10 || ip.addr == 192.0.2.20) && tcp` signifie TCP lié à l’une ou l’autre adresse.

### 44.3 Contient et expression régulière

`contains` recherche une séquence dans un champ ; `matches` compare une chaîne à une expression régulière. Exemple : `http.host contains "example"` cherche ce texte dans le champ hôte HTTP. Ces opérateurs peuvent être coûteux sur un grand fichier : limite d’abord le protocole, l’hôte ou la période.

Le texte recherché peut être absent parce que le trafic est chiffré, compressé, tronqué ou décodé autrement. Une séquence qui apparaît n’est pas une preuve de contexte : examine le paquet et le champ concernés.

### 44.4 Suggestions, erreurs et champs répétés

Si Wireshark signale le filtre comme invalide, vérifie l’orthographe, le nom du champ, les guillemets et le type de valeur. Si le filtre est valide mais que la liste devient vide, enlève les conditions une par une. La valeur peut différer de ce qui était attendu, le protocole peut ne pas être décodé ou le champ peut se trouver dans un autre paquet.

Certains protocoles peuvent apparaître plusieurs fois dans un même paquet. Pour ces cas avancés, consulte la documentation du **Layer operator** et la référence des champs de la version installée. Pour débuter, l’autocomplétion et le filtre généré depuis un champ suffisent généralement.

## 45. Filtres de capture et filtres d’affichage

| Propriété | Capture filter | Display filter |
|---|---|---|
| Moment | Avant ou pendant l’enregistrement | Après la capture |
| Syntaxe | BPF/libpcap | Champs Wireshark |
| Paquets non correspondants | Non conservés par cette capture | Conservés, mais masqués |
| Exemple hôte | `host 192.0.2.10` | `ip.addr == 192.0.2.10` |
| Exemple DNS | `port 53` (DNS classique TCP/UDP) | `dns` (protocole DNS décodé) |
| Usage courant | Réduire le volume avant stockage | Explorer un fichier existant |

Image simple : le filtre de capture est le videur à la porte ; ce qu’il refuse n’entre jamais dans la salle. Le filtre d’affichage est un rideau : les objets cachés sont toujours là.

### 45.1 Quel filtre choisir ?

- **Investigation exploratoire** : capture autorisée et raisonnable, filtre d’affichage ensuite.
- **Collecte volumineuse avec contrainte de stockage** : filtre de capture après avoir défini le périmètre, la durée et les protocoles utiles.
- **Recherche répétée dans un fichier** : filtre d’affichage enregistré ou macro.
- **Besoin de relecture** : conserve l’original non filtré si la politique le permet ; exporte séparément la sélection utile et documente le filtre.

Si le paquet n’a pas été conservé à cause d’un filtre de capture, un filtre d’affichage ne peut pas le recréer.

## 46. Rechercher du texte, des octets, des champs et des motifs

**Find Packet** cherche dans le fichier ouvert. Selon la version, les modes peuvent inclure une chaîne d’affichage, une chaîne, une séquence hexadécimale ou une expression régulière. La recherche part du paquet sélectionné et suit la direction choisie ; elle ne remplace pas un filtre d’affichage.

### 46.1 Recherche pratique

1. Sélectionne le paquet où commencer, ou le premier paquet pour parcourir le fichier.
2. Ouvre **Edit → Find Packet**.
3. Choisis le type de recherche et la zone à examiner.
4. Saisis la valeur, puis utilise **Find Next**.
5. Examine le paquet complet et son contexte.

Exemples : chercher `example.org` dans une charge DNS lisible ; chercher `16 03 01` dans les octets comme piste possible d’un en-tête TLS ; chercher une adresse IP dans l’affichage. Une séquence d’octets peut apparaître par hasard : confirme sa position et le protocole décodé.

### 46.2 Recherche versus filtre

Une recherche trouve une occurrence et déplace la sélection. Un filtre affiche tous les paquets qui satisfont une condition. Pour repérer toutes les requêtes DNS d’un nom, `dns.qry.name == "example.org"` est plus reproductible qu’une recherche texte ponctuelle.

Avec TLS, le contenu applicatif n’est généralement pas trouvable en clair sans secrets de session utilisables et autorisés. L’absence d’un texte dans les résultats ne prouve donc pas qu’il n’a pas été envoyé.

## 47. Colonnes, couleurs, paquets marqués et commentaires

### 47.1 Colonnes pour une question précise

Une colonne est un raccourci visuel vers un champ. Source, Destination, Protocol, Length et Info constituent une base. Pour un triage SOC, ajoute au besoin `tcp.stream`, les ports ou `dns.qry.name`. Dans **Preferences → Appearance → Columns**, tu peux ajouter, retirer, réordonner ou configurer les colonnes selon ta version.

Pour créer une colonne à partir d’un champ décodé, sélectionne-le dans **Packet Details**, puis utilise **Apply as Column** dans le menu contextuel. Vérifie la nouvelle colonne sur plusieurs paquets. Une colonne vide ou répétitive est peut-être construite à partir d’un champ inadéquat.

Les colonnes changent le résumé visuel, pas les paquets. La colonne **Info** est une synthèse du dissector, pas une interprétation complète.

### 47.2 Règles de couleur

Les règles de coloration facilitent le repérage visuel. Wireshark fournit des règles usuelles, notamment pour certaines conditions TCP, mais une couleur n’est pas un verdict de sécurité.

- Garde une palette limitée et cohérente.
- Note ce que chaque couleur signifie.
- Vérifie l’expression de la règle.
- Ne déduis pas qu’un paquet coloré en rouge est malveillant.
- Exporte les règles dans un profil seulement après les avoir vérifiées.

### 47.3 Marquer, ignorer et annoter

- **Mark Packet** pose un repère temporaire ; le filtre pour les paquets marqués dépend du champ proposé par la version.
- **Ignore Packet** masque un paquet dans l’analyse courante. Il reste dans le fichier ; réactive les paquets ignorés pour le retrouver.
- **Packet Comment** ajoute une note associée au paquet lorsque le format et l’outil le permettent. Évite d’y inscrire des secrets inutiles.

Ces fonctions améliorent la navigation mais ne modifient pas le trafic original. Pour partager une analyse, consigne les hypothèses, les filtres et le numéro de paquet ; ce numéro peut changer si le fichier est exporté ou fusionné.

## 48. Follow Stream — reconstruire une conversation

La fonction **Follow** regroupe des données liées à un flux (par exemple TCP, UDP, TLS ou HTTP/2 selon le protocole et la version) et les affiche dans l’ordre reconstitué. C’est comme remettre dans l’ordre les morceaux d’un échange postal.

Depuis un paquet, ouvre **Analyze → Follow** ou le menu contextuel, puis choisis le type de flux proposé. Wireshark applique généralement un filtre au flux sélectionné. La fenêtre sépare les directions, permet parfois de limiter à un sens, de rechercher dans la conversation ou de sauvegarder les données affichées.

### 48.1 Ce qu’un flux révèle

- **HTTP non chiffré** : méthodes, en-têtes et parfois corps peuvent être visibles ; la réassemblage, la compression et les limites de capture comptent.
- **HTTPS/TLS** : sans secrets de session utilisables et autorisés, le contenu applicatif demeure chiffré. Les métadonnées, tailles et horaires peuvent rester visibles.
- **TCP** : Wireshark réassemble les segments selon les numéros de séquence et les données disponibles. Un début manquant peut rendre le texte incomplet.
- **UDP** : pas de flux ordonné avec accusé de réception TCP ; le regroupement dépend du protocole et de l’implémentation.

### 48.2 Pièges d’interprétation

1. Un texte qui ressemble à une commande n’identifie pas automatiquement la personne ou le programme qui l’a envoyé.
2. Les données peuvent être partielles, transformées ou décodées selon une hypothèse.
3. Le numéro `tcp.stream` est local à l’analyse de cette capture, pas un identifiant universel.
4. Un filtre sur un flux ne montre pas nécessairement le contexte DNS ou TLS qui l’a précédé.
5. Les données sauvegardées peuvent contenir des identifiants, fichiers ou informations privées : protège-les comme le PCAP.

Si le texte est illisible, examine l’arbre des protocoles, les octets, les paquets voisins et les mécanismes de chiffrement ou de compression.

## 49. Exporter des objets et extraire des éléments utiles

**File → Export Objects** propose, selon les protocoles et paquets présents, des objets reconstruits (par exemple HTTP, SMB ou TFTP, selon la version). Ce n’est pas une récupération universelle : Wireshark doit avoir capturé assez de données et reconnaître le protocole.

### 49.1 Procédure prudente

1. Garde le PCAP original protégé ; travaille sur une copie si tu dois modifier ou expurger la trace.
2. Note le filtre, la conversation et les numéros de paquets associés à l’objet.
3. Vérifie le protocole, le nom et la taille indiqués.
4. Enregistre l’objet dans un répertoire de laboratoire isolé.
5. Ne l’ouvre pas automatiquement. Calcule une empreinte si l’objet doit être documenté, puis analyse-le dans un environnement prévu.
6. Note les limites : contenu incomplet, chiffrement, capture tronquée, réassemblage ou doublons possibles.

L’extension ne garantit pas le type réel du fichier. Les objets exportés peuvent être malveillants ou contenir des secrets. Un objet absent peut être chiffré, incomplet, encapsulé dans un protocole non pris en charge ou hors du périmètre capturé.

## Références officielles pour cette partie

- Filtrer les paquets pendant la consultation : https://www.wireshark.org/docs/wsug_html_chunked/ChWorkViewSection.html
- Construire des expressions de filtre : https://www.wireshark.org/docs/wsug_html_chunked/ChWorkBuildDisplayFilterSection.html
- Recherche de paquets : https://www.wireshark.org/docs/wsug_html_chunked/ChWorkFindPacketSection.html
- Menus contextuels : https://www.wireshark.org/docs/wsug_html_chunked/ChWorkDisplayPopUpSection.html
- Suivre des flux : https://www.wireshark.org/docs/wsug_html_chunked/ChAdvFollowStreamSection.html
- Exporter des données et objets : https://www.wireshark.org/docs/wsug_html_chunked/ChIOExportSection.html
- Référence des champs : https://www.wireshark.org/docs/dfref/
