# Analyse de captures Wireshark — 5 PCAP

Ce laboratoire regroupe cinq exercices fictifs fournis dans le cadre d’un cours. Le compte rendu explique la démarche suivie, les filtres utilisés, les observations et les preuves visuelles.

## Parcours

1. **PCAP 1** — isoler un flux TCP et lire une charge utile en clair.
2. **PCAP 2** — examiner une session FTP et extraire les objets transférés.
3. **PCAP 3** — suivre un flux TCP et identifier le fichier vidéo reconstitué.
4. **PCAP 4** — analyser l’authentification HTTP Basic et les réponses du serveur.
5. **PCAP 5** — relier une requête HTTP authentifiée aux éléments de sa réponse.

## Fichiers

Les archives prévues pour cette analyse sont :

- `Wireshark_GitHub_package.zip` — rapport PDF/DOCX et preuves visuelles classées par PCAP.
- `Wireshark_PCAPs_1_to_5.zip` — les cinq captures originales et leurs empreintes SHA-256.

Les fichiers binaires seront disponibles dans la section [Releases](https://github.com/bricehach/cybersecurity-soc-lab/releases) du dépôt dès leur ajout à une publication. Les noms des PCAP doivent être conservés pour reproduire les filtres, numéros de trames et numéros de flux du rapport.

## Reproductibilité et intégrité

Après extraction des archives, ouvrir les captures dans Wireshark. Le manifeste `SHA256SUMS.txt` fourni avec les PCAP permet de vérifier leur intégrité :

```bash
sha256sum -c SHA256SUMS.txt
```

Les valeurs d’authentification et adresses visibles dans les traces sont propres aux scénarios fictifs du laboratoire et ne correspondent pas à des accès de production.
