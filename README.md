Projet Goutte d’Eau – MVP
Projet réalisé dans le cadre du Mastère Management de la Transformation Digitale en IA
Bloc 2 – Conception et développement de l’architecture fonctionnelle

🎯 Objectif du projet

L’objectif du projet est de concevoir un MVP de prédiction du risque de pluie à partir de données météorologiques ouvertes. Ce MVP doit couvrir l’ensemble de la chaîne fonctionnelle attendue : collecte des données depuis une API, traitement et stockage en base de données, entraînement d’un modèle de machine learning, exposition d’une API de prédiction, évaluation du modèle, documentation et mise à disposition d’une première interface graphique. Le périmètre est volontairement limité à une seule région et l’outil s’adresse en priorité aux agriculteurs, afin de fournir une première preuve de concept exploitable.



👥 Cibles fonctionnelles
Agriculteurs : prédictions simples basées sur la localisation
Collectivités territoriales : vision agrégée
Gestionnaires des risques : indicateurs avancés
🏗️ Architecture fonctionnelle (MVP)
Le MVP repose sur les composants suivants :

Pipeline technique (src/)

collect_data.py : collecte des datas et construction de la base de données
preprocess_data.py : prétraitement des données météo
model_classification.py : modèle de classification du risque de pluie
model_regression.py : modèle de régression pour l’intensité de pluie
pipeline_totale.py : pipeline complet générant le CSV de prédictions
Stockage des données

static/data/predictions_consolidees.csv : utilisé par l’API et l’interface
API REST (app.py)

Fournit des endpoints pour :
liste des stations, dates, heures
récupération des données pour une station/date/heure
prédictions pour un point GPS
vérification santé de l’API
Interface web

templates/ + static/ → visualisation interactive des prévisions
🧰 Stack technique
Langage : Python, JavaScript, HTML, CSS
API : FastAPI
Data science / ML : Pandas, Scikit-learn
Interface : interface web
📊 Évaluation du modèle
Indicateur	
Accuracy globale	
Precision classe 
Recall classe 
F1-score 
🌱 Éco-responsabilité
Pipeline simple et réutilisable pour limiter les calculs
CSV généré pour éviter l’entraînement à chaque lancement

♿ Accessibilité
Interface lisible et navigation simple
Préparation pour une future mise en conformité WCAG
🚀 Installation et exécution
# Cloner le projet
git clone https://github.com/Evan-Rouzaud-git/Projet-goutte-eau.git
cd projet-goutte-eau

📂 Structure du projet
projet-goutte-eau/
├── app.py                 
├── src/
│   ├── collect_preprocess_data.py
│   ├── model_classification.py
│   ├── model_Random forest.py
│   └── pipeline_totale.py
├── static/
│   ├── css/
│   ├── js/
│   ├── frames_masked/
│   └── data/
│       └── station_pipelines/  # CSV utilisé par l'API
├── templates/               # Interface web
├── requirements.txt
└── README.md
