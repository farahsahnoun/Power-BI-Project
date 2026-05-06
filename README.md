Projet Goutte d’Eau – MVP
Projet réalisé dans le cadre du Mastère Management de la Transformation Digitale en IA
Bloc 2 – Conception et développement de l’architecture fonctionnelle
🎯 Objectif du projet

L’objectif du projet Goutte d’Eau est de concevoir un MVP (Minimum Viable Product) capable de prédire le risque de pluie à partir de données météorologiques ouvertes. Le projet couvre l’ensemble de la chaîne fonctionnelle attendue dans un projet de transformation digitale orienté intelligence artificielle : collecte des données, traitement et nettoyage, stockage, entraînement d’un modèle de machine learning, génération de prédictions et restitution via une interface utilisateur.

Le périmètre du MVP est volontairement limité à une seule région afin de démontrer la faisabilité technique de la solution dans un cadre de preuve de concept. L’application s’adresse principalement aux agriculteurs, afin de leur fournir une estimation simple et rapide du risque de pluie pour les aider dans leurs prises de décision quotidiennes.

👥 Cibles fonctionnelles
Cible	Besoin principal
Agriculteurs	Obtenir une estimation rapide du risque de pluie
Collectivités territoriales	Visualiser les tendances météorologiques locales
Gestionnaires des risques	Disposer d’indicateurs météo exploitables
🏗️ Architecture fonctionnelle du MVP

Le MVP repose sur plusieurs composants organisés autour d’une architecture simple et modulaire.

🔹 Pipeline de traitement des données

Le dossier src/ regroupe les différents scripts Python utilisés pour le traitement des données et l’entraînement des modèles :

Script	Rôle
collect_preprocess_data.py	Collecte des données météo et nettoyage des données
model_classification.py	Modèle de classification du risque de pluie
model_random_forest.py	Entraînement du modèle Random Forest
pipeline_totale.py	Pipeline global générant les prédictions
🔹 Stockage des données

Les données consolidées sont générées sous forme de fichier CSV afin de limiter les traitements lourds et d’améliorer les performances du MVP.

Emplacement	Utilisation
static/data/station_pipelines/	Stockage des prédictions consolidées utilisées par l’API et l’interface
🔹 API REST

L’application expose une API REST développée en Python permettant :

de récupérer les données météo
d’effectuer des prédictions
de consulter les stations disponibles
de vérifier l’état de fonctionnement du service
Principaux endpoints
Endpoint	Fonction
/stations	Liste des stations disponibles
/predict	Prédiction du risque de pluie
/health	Vérification de l’état de l’API
🔹 Interface utilisateur

Une interface web légère permet de visualiser les prévisions météo et les résultats des prédictions.

Dossier	Fonction
templates/	Pages HTML de l’interface
static/	Fichiers CSS, JavaScript et données

L’interface a été conçue pour rester simple, lisible et facilement exploitable dans le cadre d’un MVP.

🧰 Stack technique
Catégorie	Technologies
Langage principal	Python
Frontend	HTML, CSS, JavaScript
API	FastAPI
Data Science	Pandas, Scikit-learn
Machine Learning	Random Forest
Stockage	CSV / SQLite
Interface utilisateur	Interface web
📊 Évaluation du modèle

Après entraînement du modèle Random Forest, plusieurs indicateurs de performance ont été calculés afin d’évaluer la qualité des prédictions.

Indicateur	Valeur
Accuracy globale	91,69 %
Precision classe “Pluie”	42 %
Recall classe “Pluie”	23 %
F1-score classe “Pluie”	30 %

Le modèle obtient une bonne précision globale sur l’ensemble des données. Cependant, les performances restent plus limitées sur la détection des épisodes pluvieux, principalement en raison du déséquilibre entre les périodes de pluie et les périodes sèches dans les données utilisées.

🌱 Éco-responsabilité

Le projet a été conçu dans une logique de sobriété numérique :

utilisation d’un pipeline léger et réutilisable
génération de fichiers CSV consolidés pour éviter un réentraînement systématique
limitation des traitements lourds
architecture simplifiée adaptée à un MVP

Cette approche permet de réduire la consommation de ressources tout en conservant un fonctionnement fluide et exploitable.

♿ Accessibilité

L’interface utilisateur a été pensée pour rester simple et facilement compréhensible :

navigation claire
interface lisible
affichage simplifié des résultats
structure compatible avec une future amélioration selon les recommandations WCAG

L’objectif est de proposer une première interface accessible même à des utilisateurs non techniques.

🚀 Installation et exécution
1. Cloner le projet
git clone https://github.com/farahsahnoun/Power-BI-Project.git
cd Power-BI-Project
2. Installer les dépendances
pip install -r requirements.txt
3. Lancer l’application
streamlit run app.py
📂 Structure du projet
Projet-Goutte-Eau/
│
├── app.py
│
├── src/
│   ├── collect_preprocess_data.py
│   ├── model_classification.py
│   ├── model_random_forest.py
│   └── pipeline_totale.py
│
├── static/
│   ├── css/
│   ├── js/
│   ├── data/
│   │   └── station_pipelines/
│
├── templates/
│
├── model.pkl
├── requirements.txt
└── README.md
