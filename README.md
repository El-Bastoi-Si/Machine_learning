#RAPPORT DE PROJET : ML & DEEP LEARNING
Sujet : Impact de la consommation de caféine sur la qualité et la durée du sommeil selon l’âge.                        Étudiant : ISSOUMAILA El-Bastoi-Si

1. Présentation du problème
L'objectif de ce projet est d'étudier comment la consommation de caféine affecte le repos nocturne. La problématique centrale est de déterminer si cet impact varie de manière significative avec l'âge de l'individu. Nous traitons ce problème comme une tâche de classification pour prédire la catégorie de Sleep_Quality.

2. Description du dataset
Le dataset contient des informations sur l'apport en caféine (Caffeine_mg), les données démographiques (Age, Gender, BMI) et les habitudes de vie (Stress_Level, Smoking). Nous disposons d'environ 10 000 entrées.

3. Analyse exploratoire (EDA)
L'analyse montre une corrélation négative entre la caféine et les heures de sommeil. Nous avons remarqué que les classes de qualité du sommeil sont déséquilibrées, avec une majorité de "Good". Nous avons supprimé la colonne Coffee_Intake car elle était redondante (corrélation de 1.0) avec Caffeine_mg.

4. Feature Engineering
Pour répondre à la problématique, nous avons créé une feature d'interaction : Age_x_Caffeine. Cette variable permet au modèle de comprendre que l'effet de la caféine n'est pas le même à 20 ans qu'à 60 ans, ce qui enrichit considérablement l'analyse.

5. Modèles ML testés
Nous avons mis en place un pipeline de traitement (StandardScaler et OneHotEncoder)  et testé les modèles suivants :

Régression Logistique : 98,95%

KNN : 92,15%

Decision Tree : 99,05%

SVM : 98,40%


Random Forest : 98,95% 

6. Tuning des hyperparamètres
Nous avons effectué un GridSearchCV sur le Random Forest pour optimiser la profondeur des arbres et le nombre d'estimateurs.

Résultat avant tuning : 98,95%


Résultat après tuning : 99,28%  Cela prouve l'importance de l'optimisation pour gagner en précision.

7. Explicabilité (SHAP)
L'utilisation de SHAP confirme que Sleep_Hours et Caffeine_mg sont les prédicteurs les plus forts. Le graphique d'interaction montre clairement que l'âge modifie la manière dont la caféine impacte la prédiction, validant ainsi notre hypothèse de départ.

8. Modèle Deep Learning (ANN)
Nous avons conçu un réseau de neurones simple (3 couches denses avec Dropout).

Performance : L'accuracy dépasse 99%.


Analyse de la perte : Les courbes de train_loss et val_loss convergent vers zéro sans s'écarter, ce qui prouve l'absence d'overfitting.

9. Conclusion et limites
Conclusion : Le projet démontre avec succès que la caféine dégrade la qualité du sommeil et que ce phénomène est modulé par l'âge. Limites : Le déséquilibre des données (trop de "Good") pourrait limiter la précision sur des cas de sommeil "Poor" très spécifiques. De plus, d'autres facteurs comme l'heure de consommation (non présente dans le dataset) pourraient affiner l'étude.
