# 🔒 Projet : Analyse et Détection d'Anomalies dans les Logs de Sécurité

Ce dépôt présente un projet d'analyse de données axé sur la **détection proactive d'anomalies et d'incidents potentiels de cybersécurité** à partir de journaux d'événements (logs). L'objectif est de transformer des données brutes de logs en renseignements exploitables pour renforcer la posture de sécurité d'un système ou d'un réseau.

---

### 🎯 Objectif du Projet

L'enjeu principal est de développer une approche pour :
* **Identifier les activités suspectes :** Repérer les `event_type` inhabituels, les actions non autorisées (`action: Deny`, `Failed`), ou les `risk_score` élevés.
* **Comprendre les schémas d'attaque potentiels :** Analyser les séquences d'événements (`timestamp`, `source_ip`, `destination_ip`) pour détecter des tentatives d'intrusion ou des comportements malveillants.
* **Fournir des insights actionnables :** Permettre aux équipes de sécurité de réagir rapidement aux menaces émergentes.

---

### 📊 Données Utilisées

Le projet s'appuie sur un jeu de données de logs d'événements de sécurité, incluant des informations détaillées sur le trafic et les interactions système :

* **Horodatage (`timestamp`) :** Moment de l'événement.
* **Adresses IP (`source_ip`, `destination_ip`) :** Origine et destination du trafic.
* **Type d'événement (`event_type`) :** Nature de l'activité (ex: `Login`, `Firewall Deny`, `Malware Alert`, `File Access`, `Service Start`).
* **Détails Réseau :** `protocol` (TCP, UDP, HTTP, HTTPS, ICMP, SSH), `port`.
* **Utilisateur (`username`) :** Compte impliqué dans l'événement.
* **Action (`action`) :** Résultat de l'événement (ex: `Allow`, `Deny`, `Failed`).
* **Taille de la Charge Utile (`payload_size_kb`) :** Volume de données (peut contenir `NaN` ou `large_payload`).
* **Score de Risque (`risk_score`) :** Évaluation numérique de la criticité de l'événement (allant de 0 à 100).

---

### 🚀 Méthodologie et Compétences Appliquées

Ce projet démontre une maîtrise des techniques d'analyse de données appliquées à la cybersécurité :

1.  **Exploration de Données (EDA) de Logs :**
    * Analyse des distributions des `event_type`, `protocol`, `action`.
    * Identification des événements à `risk_score` élevé et leur fréquence.
    * Analyse temporelle des événements (`timestamp`) pour détecter des pics d'activité.

2.  **Prétraitement et Nettoyage de Données Spécifique aux Logs :**
    * **Gestion des valeurs manquantes :** Traitement des `NaN` dans `payload_size_kb` et `username`.
    * **Normalisation des valeurs textuelles :** Uniformisation des formats (ex: `user_185` vs `user-48`, `N/A_PORT` vs numériques) et gestion des valeurs non numériques (`large_payload`).
    * **Conversion de types :** Assurer que `timestamp` est un type date/heure et que `payload_size_kb` est numérique.
    * **Extraction d'informations :** Potentielle extraction de caractéristiques à partir des IP ou des ports.

3.  **Analyse d'Anomalies et Identification des Menaces :**
    * Utilisation du `risk_score` comme indicateur clé pour filtrer et prioriser les événements critiques.
    * Regroupement et agrégation des logs pour identifier des patterns récurrents ou des comportements anormaux par `source_ip`, `destination_ip`, ou `username`.
    * Analyse des `event_type` tels que `Malware Alert`, `Firewall Deny`, ou `Login Failed` comme signaux d'alerte.

4.  **Visualisation des Insights :**
    * Création de graphiques (par exemple, distributions des scores de risque, fréquence des types d'événements, top des IP sources/destinations suspectes) pour communiquer visuellement les menaces détectées.

---

### ✨ Apprentissages Clés & Valeur Ajoutée

Ce projet m'a permis de :
* Maîtriser le traitement de données non structurées ou semi-structurées (logs).
* Développer une approche structurée pour la détection d'anomalies.
* Comprendre l'importance de la qualité des données dans un contexte de cybersécurité.
* Démontrer ma capacité à transformer des données techniques en insights actionnables pour la prise de décision.

---

### 🛠️ Technologies Utilisées

* **Langage :** Python
* **Bibliothèques :** `Pandas` (manipulation de données), `NumPy` (opérations numériques), `Matplotlib`, `Seaborn` (visualisation), `re` (expressions régulières pour le parsing de logs).
* **Environnement :** Jupyter Notebook (ou Google Colab)

---


---

### 📧 Contact

Pour toute question ou opportunité de collaboration en alternance, n'hésitez pas à me contacter :

* **LinkedIn :** [www.linkedin.com/in/mounir-siraji-389b2ba5]
* **Email :** conseilmounir@gmail.com
