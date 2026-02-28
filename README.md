# EasyTrack

EasyTrack est une application web professionnelle (PWA) de suivi de musculation et d'analyse de composition corporelle (Visbody). Conçue pour être légère, rapide et 100% gratuite, elle fonctionne entièrement côté client avec une synchronisation des données en temps réel sur une base de données cloud (Supabase).

Pensée pour une utilisation mobile à la salle de sport, elle permet de tracker ses performances, d'estimer sa progression globale et de visualiser l'évolution de son corps grâce à des tableaux de bord interactifs.

## Fonctionnalités principales

* **Suivi des entraînements :** Programmes de base (Push, Pull, Legs) et séances spécifiques (Full Body, Bras, Points faibles).
* **Mémoire intelligente :** Affichage automatique des performances de la séance précédente pour chaque exercice afin de viser la surcharge progressive.
* **Calculateur de progression (1RM) :** Calcul automatique de la performance globale théorique via la formule d'Epley et affichage de la progression en pourcentage.
* **Bilan Visbody Pro :** Tableau de bord avancé gérant les 8 paramètres officiels d'analyse corporelle (Poids, Score Santé, Masse grasse, Muscle, Eau, Os/Minéraux, Graisse viscérale, Métabolisme).
* **Graphiques dynamiques :** Visualisation individuelle de chaque métrique via Chart.js pour une lecture claire de l'évolution.
* **Support visuel :** Intégration de photos anatomiques pour chaque exercice, affichables à la demande pendant la séance.

## Technologies utilisées

* **Frontend :** HTML5, CSS3, JavaScript (Vanilla)
* **Design :** Tailwind CSS (via CDN)
* **Graphiques :** Chart.js
* **Backend / Base de données :** Supabase (PostgreSQL)
* **Hébergement :** GitHub Pages

## Guide d'installation

L'application est conçue pour être déployée facilement en quelques minutes, sans serveur complexe.

### 1. Configuration de Supabase (Base de données)

1. Créez un projet gratuit sur Supabase.
2. Allez dans le "Table Editor" et créez deux tables (désactivez l'option "Enable Row Level Security (RLS)" pour simplifier l'accès) :

**Table 1 : `workouts`**
* `date` (type: date)
* `workout_id` (type: text)
* `data` (type: jsonb)

**Table 2 : `visbody`**
* `date` (type: date)
* `weight` (type: float4)
* `score` (type: float4)
* `fat` (type: float4)
* `muscle` (type: float4)
* `water` (type: float4)
* `bone` (type: float4)
* `visceral` (type: float4)
* `bmr` (type: float4)

### 2. Configuration du code source

1. Dans votre fichier `index.html`, localisez la section des clés API (vers la ligne 170).
2. Remplacez les valeurs par celles de votre projet Supabase (trouvables dans Project Settings > API) :

### 3. Déploiement sur GitHub Pages

Hébergez le code sur un dépôt GitHub public ou privé.

Allez dans l'onglet Settings du dépôt, puis dans la section Pages.

Sous Build and deployment, choisissez la branche main et sauvegardez.

L'application sera accessible via une URL publique dans les minutes qui suivent. Sur smartphone, utilisez la fonction "Ajouter à l'écran d'accueil" pour l'utiliser comme une application native.

#### Configuration des images d'exercices
Pour obtenir un rendu visuel professionnel (style anatomique avec muscles en surbrillance), vous devez remplacer les liens par défaut dans le dictionnaire exerciseImages du fichier index.html.

Pour trouver les images idéales, effectuez une recherche sur Google Images en utilisant les mots-clés exacts ci-dessous, faites un clic droit sur l'image choisie et sélectionnez "Copier l'adresse de l'image" avant de coller le lien dans le code.

Séance Push

Développé couché : bench press anatomy illustration

Chest press inclinée : incline chest press machine anatomy

Développé militaire : seated dumbbell shoulder press anatomy

Triceps barre droite : triceps pushdown anatomy

Triceps barre V : v-bar triceps pushdown anatomy

Séance Pull

Tirage vertical : lat pulldown anatomy illustration

Tirage horizontal : seated cable row anatomy

Rowing : barbell row anatomy

Biceps poulie : cable bicep curl anatomy

Curl marteau : dumbbell hammer curl anatomy

Séance Legs

Squat pendulum : pendulum squat anatomy

Soulevé de terre roumain : romanian deadlift anatomy

Presse : leg press machine anatomy

Leg extension : leg extension anatomy

Leg curl : seated leg curl anatomy

Mollets : standing calf raise anatomy

Bonus : Full Body

Fentes bulgares : bulgarian split squat anatomy

Développé incliné haltères : incline dumbbell press anatomy

Tirage poitrine : front lat pulldown anatomy

Élévations latérales : dumbbell lateral raise anatomy

Curl pupitre : preacher curl anatomy

Abdos : machine crunch anatomy

Bonus : Bras & Épaules

Curl barre : barbell bicep curl anatomy

Extension triceps poulie : overhead cable triceps extension anatomy

Face pull : cable face pull anatomy

Dips : triceps dips anatomy illustration

Bonus : Points faibles

Pull-over : dumbbell pullover anatomy

Écarté poulie vis-à-vis : cable crossover anatomy

Tirage bras tendus : straight arm pulldown anatomy

Oiseau haltères : reverse fly anatomy

Shrugs : dumbbell shrug anatomy
```javascript
const SUPABASE_URL = 'VOTRE_URL_SUPABASE';
const SUPABASE_ANON_KEY = 'VOTRE_CLE_ANON_SUPABASE';
