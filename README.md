#  Pipeline Big Data pour Données Télécom

Ce projet simule un pipeline Big Data complet pour la gestion de données télécoms. Il couvre toutes les étapes : génération de données synthétiques (CDR/EDR), ingestion avec Kafka, traitement en streaming via Spark, tarification, facturation et génération de rapports JSON et PDF.
Ce pipeline est un excellent exemple d'architecture moderne en Data Engineering, intégrant des outils de streaming, de batch processing, de gestion de qualité des données et de visualisation.

##  Objectifs du projet

- Générer des enregistrements télécoms réalistes (voix, SMS, data)
- Simuler des anomalies pour tester la robustesse du pipeline
- Traiter les données en temps réel avec Spark Streaming
- Appliquer des règles de tarification par service
- Générer des factures personnalisées pour chaque client
- Exporter les résultats en JSON et PDF

##  Technologies utilisées

| Outil / Langage     | Rôle dans le projet                           |
|---------------------|-----------------------------------------------|
| Python              | Scripts de génération, tarification, billing  |
| Apache Kafka        | Transport en temps réel des CDR               |
| Apache Spark        | Traitement des données (Streaming & Batch)    |
| PostgreSQL          | Stockage des clients et résultats tarifés     |
| PDFKit              | Génération des factures PDF                   |
| JSON                | Format des enregistrements et résultats       |

##  Architecture du pipeline
graph LR
A[Générateur de données synthétiques] --> B[Kafka Producer]
B --> C[Médiation Spark Streaming]
C --> D[Rating Engine - Spark Batch]
D --> E[Billing Engine - Spark Batch]
E --> F[Factures JSON & PDF]
