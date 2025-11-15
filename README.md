# Analyse du Churn Client pour "Telco"

## 1. Le Problème Business (La Demande)
Notre client, un opérateur "Telco", constate une perte de clients (churn) mais n'en comprend pas les causes exactes. L'objectif de ce projet n'est pas seulement de mesurer le taux de churn, mais de diagnostiquer les raisons principales du départ des clients.

La question business est : "Qui part, pourquoi, et sur quels leviers devons-nous agir en priorité pour réduire l'attrition et maximiser notre revenu (MRR) ?"

## 2. Les Données
Source : [Dataset "Telco Customer Churn" par IBM (disponible sur Kaggle)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn?resource=download).

Contenu : ~7000 lignes de clients anonymisés.

Dimensions clés :

Infos Client : gender, SeniorCitizen, Partner, Dependents.

Infos Contrat : tenure (ancienneté), Contract, PaymentMethod, MonthlyCharges, TotalCharges.

Services Souscrits : PhoneService, InternetService (DSL, Fiber), OnlineSecurity, TechSupport, etc.

KPI Cible : Churn (Yes/No).

## 3. Plan d'Analyse & Hypothèses
Notre analyse sera guidée par la vérification des hypothèses suivantes :

### Hypothèses sur le Contrat et la Valeur
* H1 (Engagement) : Les clients avec un contrat Month-to-month (sans engagement) ont un taux de churn significativement plus élevé que les clients engagés sur 1 ou 2 ans.

* H2 (Prix) : À service égal, les clients ayant les MonthlyCharges les plus élevées sont plus susceptibles de partir.

* H3 (Ancienneté) : Le churn est plus concentré chez les nouveaux clients (ancienneté tenure < 12 mois) que chez les clients fidèles.

### Hypothèses sur le Produit et le Service
* H4 (Support Technique) : Les clients n'ayant pas souscrit au service TechSupport churnent davantage, car ils sont plus susceptibles d'être frustrés par des problèmes techniques.

* H5 (Type d'Internet) : Le type d'accès internet Fiber optic (plus cher/moderne) génère un churn différent (peut-être plus élevé à cause d'instabilité ou de prix) que le DSL.

### Hypothèses sur la Démographie
* H6 (Démographie) : Le statut SeniorCitizen influence le comportement de churn (par exemple, moins de tolérance aux problèmes techniques ou sensibilité au prix).

## 4. La Stack Technique (Nos Outils)
Stockage/Requêtage : SQLite

Analyse & Nettoyage : Python (Pandas, NumPy).

Visualisation & EDA : Matplotlib / Seaborn.

Dashboarding & Storytelling : Tableau (ou Power BI).