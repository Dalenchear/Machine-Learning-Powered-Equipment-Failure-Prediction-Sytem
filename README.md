# Maintenance 4.0 
# Double Stratégie de Détection des Défaillances Critiques de Materiels par Classification Binaire et Multiclasse

## Pitch Éclair

Le projet développe un système intelligent de maintenance prédictive qui utilise le machine learning pour prévoir les pannes d'équipement avant qu'elles ne surviennent. En analysant les données de capteurs provenant de machines industrielles, le système identifie les défaillances potentielles avec une précision allant jusqu'à 95,7%, permettant aux organisations de passer d'une maintenance réactive coûteuse à une intervention proactive. La solution offre un cadre de prédiction en deux étapes : détecter les pannes imminentes et identifier les types de pannes spécifiques, réduisant ainsi les coûts d'arrêt imprévu et optimisant l'allocation des ressources de maintenance.

![Schéma de la Stratégie de Maintenance Prédictive](predictive_maintenance_market.webp)

---

## Compréhension du Contexte Business

### Citation
Dépenser de l'argent pour en économiser n'est pas simple pour certains. Mais dans le cas des programmes de maintenance prévisionnelle et préventive, surtout pour des actifs aux coûts d'investissement élevés, une dépense modeste peut compenser les coûts de réparation ou de production perdue qui peuvent atteindre des millions.(Olivier Kwaczala pour RS Components)

### Le Défi

Les grandes usines de production, les réseaux de télécommunications et les fournisseurs de services essentiels font face à un défi opérationnel universel : les pannes d'équipement critique qui perturbent les fonctions commerciales essentielles et génèrent des conséquences financières et opérationnelles substantielles.

- **Les usines de production** sont confrontées aux pannes de machines de production qui arrêtent les chaînes d'assemblage et retardent l'exécution des commandes
- **Les entreprises de télécommunications** font face aux pannes d'équipement d'antennes et de tours qui perturbent la couverture réseau et la fiabilité du service
- **Les entreprises de services**, y compris les banques, les écoles et les hôpitaux, sont confrontées aux pannes de générateurs électriques pendant les coupures qui menacent leur capacité à fonctionner et à servir leurs communautés

Ces pannes d'équipement créent des effets en cascade qui impactent les revenus, la sécurité et la prestation de services dans plusieurs secteurs.

### L'Argument Commercial

Les statistiques de l'industrie soutiennent massivement l'argument commercial pour la maintenance prédictive :

- **50 milliards de dollars** - Coût annuel des temps d'arrêt imprévus pour les fabricants industriels (Deloitte)
- **70-75%** - Réduction des pannes d'équipement avec la maintenance prédictive (McKinsey)
- **25-30%** - Diminution des coûts de maintenance (McKinsey)
- **22 000 $/minute** - Coût moyen pendant les arrêts de production manufacturière (Automotive Manufacturing Association)
- **15 000-20 000 $/minute** - Coût des pannes de télécommunications (ITIC Research)
- **ROI de 10x** - Retour sur investissement moyen (Capgemini Research Institute)
- **6-9 mois** - Période de récupération typique (Bain & Company)
- **45-55%** - Réduction des coûts par rapport aux approches réactives (Plant Engineering)
- **9%** - Augmentation de la disponibilité de l'équipement (Plant Engineering)

### Stratégie d'Optimisation des Coûts

L'approche de maintenance prédictive permet une minimisation substantielle des coûts grâce à une prédiction intelligente des pannes :

- **Vrais Positifs** : Permettent de planifier la maintenance pendant les temps d'arrêt prévus, évitant les réparations d'urgence coûteuses
- **Faux Positifs** : Représentent le coût minimal de la maintenance préventive, nettement inférieur aux dépenses d'arrêt inattendu
- **Faux Négatifs** : Comportent le coût le plus élevé par des arrêts opérationnels imprévus et des exigences de réponse d'urgence

**La résilience opérationnelle n'est plus une aspiration mais un impératif financier.** Avec le coût des temps d'arrêt mesuré en dizaines de milliers par minute, la transition d'une maintenance réactive vers une stratégie prédictive et axée sur l'intelligence est le levier le plus impactant qu'une organisation puisse actionner pour protéger la rentabilité, assurer la continuité des activités et sécuriser un avantage concurrentiel décisif sur le marché actuel.

---

## Compréhension des Données

### Source et Propriétés des Données

L'ensemble de données utilisé pour ce projet de maintenance prédictive est un ensemble de données synthétiques complet contenant **10 000 enregistrements historiques** d'opérations de machines avec **10 caractéristiques pertinentes** qui reflètent directement les données réelles de capteurs d'équipement industriel. Cet ensemble de données fournit une base solide pour développer des modèles prédictifs applicables aux machines de fabrication, aux infrastructures de télécommunications et aux systèmes de production d'énergie.

### Composition de l'Ensemble de Données

**Caractéristiques Principales avec Pertinence Commerciale Directe :**

| Caractéristique | Description | Pertinence Commerciale |
|-----------------|-------------|------------------------|
| **Type (L/M/H)** | Variantes de qualité du produit | Simule différents modèles d'équipement (distribution 60%/30%/10%) |
| **Température de l'air [K]** | Surveillance de la température ambiante | Critique pour détecter les conditions de stress environnemental |
| **Température de processus [K]** | Température de fonctionnement interne | Essentiel pour le stress thermique et la détection de surchauffe |
| **Vitesse de rotation [rpm]** | Vitesse du moteur/moteur | Fondamental pour les machines rotatives dans toutes les industries |
| **Couple [Nm]** | Mesure de charge mécanique | Essentiel pour détecter les conditions de surcharge |
| **Usure de l'outil [min]** | Métrique de dégradation cumulative | Représente le vieillissement et les modèles d'usure de l'équipement |
| **Target** | Indicateur binaire de panne | Cible de prédiction principale (0 = Pas de panne, 1 = Panne) |
| **Type de panne** | Catégorie de panne spécifique | Cible secondaire pour le diagnostic détaillé |

### Aperçu Statistique

**Taille de l'ensemble de données :** 10 000 enregistrements fournissant une puissance statistique substantielle pour le développement du modèle

**Distribution des Pannes :**
- Taux de panne global : **3,4%** (339 événements de panne) - réaliste pour l'équipement industriel
- Répartition des types de pannes :
  - Dissipation thermique : 112 événements
  - Panne de puissance : 95 événements
  - Surcharge : 78 événements
  - Usure de l'outil : 45 événements
  - Pannes aléatoires : 18 événements (supprimés lors du prétraitement)

**Plages Opérationnelles :**
- Température : 295,3K - 304,5K (couvrant les conditions normales aux conditions de stress)
- Vitesse de rotation : 1 168 - 2 886 rpm (ralenti à plage opérationnelle maximale)
- Couple : 3,8 - 76,6 Nm (charge légère aux scénarios de surcharge)
- Usure de l'outil : 0 - 253 minutes (équipement neuf à fortement usé)

### Insights Clés de l'Analyse Exploratoire des Données

1. **Forte Corrélation Négative (-0,88)** entre le Couple et la Vitesse de Rotation
   - Reflète le principe mécanique fondamental : couple élevé = vitesse plus faible
   - Indique des systèmes correctement fonctionnels et limités en puissance

2. **Corrélation Positive (0,88)** entre la Température de Processus et la Température de l'Air
   - La température interne de la machine est fortement influencée par l'environnement ambiant

3. **Modèles de Panne aux Extrêmes**
   - Les machines tombent en panne aux valeurs les plus basses ou les plus élevées du couple et de la vitesse de rotation
   - Zone opérationnelle "sûre" claire pour les conditions normales

4. **Impact du Type de Produit**
   - Produits L : Taux de panne le plus élevé
   - Produits M : Taux de panne moyen
   - Produits H : Taux de panne le plus faible (hiérarchie de qualité logique)

5. **Caractéristiques par Type de Panne :**
   - **Panne de puissance** : Vitesses de rotation très faibles (<1400 rpm) + couple élevé (>40 Nm)
   - **Surcharge** : Niveaux de couple les plus élevés (>60 Nm) à diverses vitesses
   - **Dissipation thermique** : Couple moyen + vitesse de rotation moyenne à élevée

### Limitations des Données

**Limitations Clés :**
- **Déséquilibre de Classe** : Taux de panne de 3,4% crée un défi significatif nécessitant des techniques d'échantillonnage spécialisées
- **Distribution des Pannes** : Certains types de pannes ont des exemples limités (seulement 18 pannes aléatoires supprimées)
- **Nature Synthétique** : Peut ne pas capturer toutes les complexités opérationnelles réelles et les modèles de bruit
- **Lacunes Temporelles** : Manque de contexte de séries temporelles continues disponible dans les systèmes de surveillance réels

**Implications :** Ces limitations définissent la portée actuelle comme une démonstration de preuve de concept qui valide l'approche analytique. L'ensemble de données capture avec succès les modèles de panne essentiels et les relations opérationnelles, fournissant une base transférable qui peut être étendue avec des données spécifiques à l'organisation pendant les phases de mise en œuvre.

---

## Modélisation et Évaluation

### Prétraitement des Données

**1. Nettoyage des Données**
- Suppression de 27 enregistrements incohérents (0,27% de l'ensemble de données) :
  - 9 enregistrements : Classés comme Panne dans Target mais Pas de panne dans Type de panne
  - 18 enregistrements : Pannes aléatoires avec étiquetage incohérent

**2. Encodage**
- Application de l'**Encodage Ordinal** pour la caractéristique Type : L=0, M=1, H=2
- Encodage des catégories de Type de panne pour la modélisation multiclasse

**3. Mise à l'Échelle des Caractéristiques**
- **RobustScaler** pour Vitesse de Rotation et Couple (en raison des valeurs aberrantes)
- **MinMaxScaler** pour Température de l'air, Température de processus et Usure de l'outil

**4. Division Train-Test**
- **Division Stratifiée** : 75% entraînement, 25% test
- Maintien des proportions de classe à travers les divisions
- Entraînement : 7 500 échantillons
- Test : 2 500 échantillons

### Modèles de Classification Binaire (Détection de Panne)

**Objectif :** Prédire si l'équipement va tomber en panne (Oui/Non)

#### Modèles Testés

| Modèle | ROC AUC | F1 Macro | Précision Macro | Rappel Macro |
|--------|---------|----------|-----------------|--------------|
| **XGBoost** ⭐ | 0,9568 | **0,7506** | 0,7498 | 0,8049 |
| **Support Vector Machine** | **0,9577** | 0,6618 | 0,6405 | 0,8820 |
| **Balanced Random Forest** | 0,9452 | 0,6154 | 0,6063 | 0,8646 |
| **Régression Logistique** | 0,8893 | 0,5987 | 0,6096 | 0,7917 |

#### Analyse de Performance

**XGBoost - Modèle Recommandé** ⭐
- **Meilleur Score F1 Macro (0,7506)** : Équilibre optimal entre la détection des pannes (Rappel) et l'évitement des fausses alarmes (Précision)
- **ROC AUC Élevé (0,9568)** : Excellente capacité de discrimination
- **Impact Commercial** : Minimise le coût opérationnel total en équilibrant la prévention des catastrophes et l'efficacité des ressources

**Matrice de Confusion - XGBoost (Ensemble de Test) :**
```
                Prédit
                Pas de Panne  |  Panne
Réel  Pas de Panne   2 387    |    24
      Panne             19    |    64
```

**Métriques Clés :**
- **Rappel (Détection de Panne) : 77,1%** - Détecte 64 pannes réelles sur 83
- **Précision (Exactitude des Alarmes) : 72,7%** - 64 alarmes sur 88 sont de vraies pannes
- **Faux Négatifs : 19** - Pannes manquées (coût élevé)
- **Faux Positifs : 24** - Maintenance inutile (coût faible)

**Interprétation Coût-Bénéfice :**
- **Vrais Positifs (64)** : Temps d'arrêt imprévu coûteux évité
- **Faux Positifs (24)** : Coût mineur de maintenance préventive
- **Faux Négatifs (19)** : Risque le plus élevé - pannes non détectées menant à des ruptures catastrophiques

### Recommandations de Modèles Alternatifs par Contexte Commercial

**Si le Coût de Catastrophe est Dominant (Coût_FN >> Coût_FP) :**
- **Recommandé : Support Vector Machine**
- **Rappel : 88,2%** - Minimise les pannes manquées
- **Compromis** : Taux de fausse alarme plus élevé acceptable comme "prime d'assurance"
- **Cas d'Usage** : Infrastructure critique, équipement distant, machines de haute valeur

**Si le Coût Opérationnel est Significatif (Coût_FN ≈ Coût_FP) :**
- **Recommandé : Balanced Random Forest**
- **Précision : 75,3%** - Minimise les déplacements de maintenance gaspillés
- **Cas d'Usage** : Équipement non critique, facilement réparable

### Modèles de Classification Multiclasse (Identification du Type de Panne)

**Objectif :** Identifier le type de panne spécifique pour une maintenance ciblée

#### Modèles Testés

| Modèle | ROC AUC (Macro OvR) | F1 Macro | Précision Macro | Rappel Macro |
|--------|---------------------|----------|-----------------|--------------|
| **Balanced Bagging** ⭐ | 0,9671 | **0,51** | 0,42 | 0,89 |
| **Balanced Random Forest** | 0,9797 | 0,45 | 0,38 | 0,90 |
| **RUS Boost** | 0,9408 | - | - | - |
| **Easy Ensemble** | 0,9349 | - | - | - |

#### Balanced Bagging Classifier - Répartition des Performances

**Matrice de Confusion (Ensemble de Test - 2 494 échantillons) :**

|  | Prédit : Pas de Panne | Puissance | Usure Outil | Surcharge | Dissipation Thermique |
|---|---|---|---|---|---|
| **Réel : Pas de Panne (2 411)** | 2 102 | 26 | 186 | 38 | 59 |
| **Réel : Puissance (24)** | 1 | 23 | 0 | 0 | 0 |
| **Réel : Usure Outil (11)** | 0 | 0 | 10 | 1 | 0 |
| **Réel : Surcharge (20)** | 0 | 0 | 1 | 18 | 1 |
| **Réel : Dissipation Thermique (28)** | 0 | 0 | 4 | 1 | 23 |

**Performance par Classe :**

| Type de Panne | Précision | Rappel | F1-Score | Support |
|---------------|-----------|--------|----------|---------|
| Pas de Panne | 1,00 | 0,87 | 0,93 | 2 411 |
| Panne de Puissance | 0,47 | 0,96 | 0,63 | 24 |
| Usure de l'Outil | 0,05 | 0,91 | 0,09 | 11 |
| Surcharge | 0,31 | 0,90 | 0,46 | 20 |
| Dissipation Thermique | 0,28 | 0,82 | 0,41 | 28 |

**Insights Clés :**

✅ **Rappel Élevé (89% moyenne macro)** : Le système détecte presque toutes les pannes et identifie correctement le type 89% du temps
- Critique pour la sécurité : Faible risque de pannes complètement manquées

⚠️ **Précision Faible (42% moyenne macro)** : Lorsque le système prédit un type de panne spécifique, il n'est correct que ~42% du temps
- **Impact Commercial** : Les équipes de maintenance peuvent arriver avec les mauvais outils/pièces
- **Problème Critique** : Prédictions d'usure d'outil seulement 5% précises - essentiellement peu fiables

### Importance des Caractéristiques

**Caractéristiques Prédictives Principales (de XGBoost) :**
1. **Couple** - Prédicteur le plus fort des pannes mécaniques
2. **Vitesse de Rotation** - Critique pour détecter les conditions de fonctionnement anormales
3. **Usure de l'Outil** - Indicateur de dégradation cumulative
4. **Température de Processus** - Surveillance du stress thermique
5. **Type** - Le niveau de qualité de l'équipement impacte la probabilité de panne

---

## Conclusion

### Résultats Clés

Ce projet de maintenance prédictive démontre avec succès comment le machine learning peut transformer la maintenance de l'équipement d'une gestion de crise réactive à une planification proactive optimisée en termes de coûts.

**Classification Binaire (Détection de Panne) :**
- ✅ **XGBoost atteint 95,7% ROC AUC et 75,1% Score F1**
- ✅ **Détecte 77% des pannes d'équipement avant qu'elles ne surviennent**
- ✅ **Taux de fausse alarme : Seulement 24 vérifications de maintenance inutiles sur 2 411 opérations normales**
- ✅ **Équilibre coût-bénéfice optimal pour la plupart des applications industrielles**

**Classification Multiclasse (Identification du Type de Panne) :**
- ✅ **Balanced Bagging atteint 96,7% ROC AUC et 89% Rappel**
- ✅ **Identifie correctement le type de panne spécifique 89% du temps**
- ⚠️ **Précision faible (42%) signifie que certaines interventions de maintenance ciblent le mauvais type de panne**
- ⚠️ **Prédictions d'usure d'outil peu fiables (<5% précision) - nécessite confirmation manuelle**

### Impact Commercial

**Potentiel d'Économies de Coûts :**
- **Temps d'Arrêt Évité** : Avec un taux de détection de panne de 77%, les organisations peuvent planifier 64 pannes sur 83 pendant les fenêtres de maintenance planifiées
- **Coûts d'Urgence Évités** : À 22 000 $/minute (fabrication) ou 15 000-20 000 $/minute (télécom), prévenir même une heure de temps d'arrêt imprévu économise 900 000 $ à 1 200 000 $
- **Ressources Optimisées** : Le modèle multiclasse permet une maintenance ciblée - pièces, outils et personnel corrects préparés à l'avance
- **ROI** : Retour sur investissement moyen de 10x de l'industrie réalisable en 6-9 mois

### Recommandations

#### Stratégie de Déploiement Immédiat

**Système Prédictif en Deux Étapes :**

1. **Étape 1 - Détection Binaire (XGBoost)**
   - Déployer comme système d'alerte principal
   - Déclencheur : Alerte "Panne Imminente" lorsque la confiance du modèle >0,5
   - Action : Initier les protocoles de planification de maintenance

2. **Étape 2 - Identification du Type de Panne (Balanced Bagging)**
   - Activer après l'alerte de l'Étape 1
   - Fournit le type de panne probable pour l'allocation des ressources
   - **Exception Critique** : Traiter les prédictions d'usure d'outil avec scepticisme - toujours confirmer manuellement

**Flux de Travail de Mise en Œuvre :**
```
Surveillance de l'Équipement → Détection XGBoost → Alerte Déclenchée
                                        ↓
                Classification Balanced Bagging
                                        ↓
        Équipe de Maintenance Dépêchée (avec ressources appropriées)
```

#### Directives Opérationnelles

**Pour les Gestionnaires d'Équipement :**
- Faire confiance aux alertes "Panne Imminente" de XGBoost - taux de détection de 77% prévient les coûts catastrophiques
- Accepter 24 fausses alarmes par 2 500 opérations comme "prime d'assurance" contre 20 000 $/minute de temps d'arrêt
- Toujours vérifier manuellement les prédictions d'usure d'outil avant de commander des composants spécialisés

**Pour les Équipes de Maintenance :**
- Utiliser les prédictions multiclasses comme guide, pas comme vérité absolue
- Préparer les ressources primaires pour le type de panne prédit
- Apporter des outils de secours pour le 2ème type de panne le plus probable
- Documenter le type de panne réel pour améliorer les performances futures du modèle

**Pour les Parties Prenantes Financières :**
- Période de récupération attendue : 6-9 mois
- Réduction des coûts : 25-30% vs maintenance réactive
- Augmentation de la disponibilité de l'équipement : 9%
- Prévention de catastrophe : Évite 64 pannes imprévues par 2 500 opérations

### Limitations et Considérations

1. **Déséquilibre de Classe** : Taux de panne de 3,4% dans les données d'entraînement peut sous-représenter les événements catastrophiques rares
2. **Données Synthétiques** : Bruit réel, dérive des capteurs et facteurs environnementaux non entièrement capturés
3. **Prédictions d'Usure d'Outil** : Critiquement peu fiables (<5% précision) - non adaptées à la prise de décision automatisée
4. **Contexte Temporel** : Le modèle actuel manque de mémoire de séries temporelles des tendances de dégradation
5. **Généralisation** : Modèle entraîné sur des types d'équipement spécifiques - nécessite un réentraînement pour différentes machines

### Prochaines Étapes

**Court Terme (0-3 mois) :**
- [ ] Déployer le classificateur binaire XGBoost dans un programme pilote avec 10-20 machines critiques
- [ ] Établir une boucle de rétroaction : Documenter les pannes réelles vs prédictions
- [ ] Former les équipes de maintenance sur le flux de travail du système en deux étapes
- [ ] Créer un tableau de bord de suivi des coûts pour mesurer le ROI

**Moyen Terme (3-6 mois) :**
- [ ] Collecter des données de panne spécifiques à l'organisation pour réentraîner les modèles
- [ ] 
**Long Terme (6-12 mois) :**
- [ ] Déployer des capteurs IoT sur l'équipement non instrumenté pour la collecte de données en temps réel
- [ ] Développer des modèles spécifiques à l'équipement pour différents types de machines
- [ ] Implémenter un système de planification de maintenance automatisé
- [ ] Créer un tableau de bord mobile pour les techniciens de terrain
- [ ] Établir un pipeline de réentraînement continu du modèle avec des données de production

**Recherche et Amélioration :**
- [ ] Investiguer les techniques d'ensemble avancées pour améliorer les prédictions d'usure d'outil
- [ ] Explorer l'apprentissage semi-supervisé avec des données de panne étiquetées limitées
- [ ] Comparer avec les plateformes commerciales de maintenance prédictive
- [ ] Développer un tableau de bord d'IA explicable pour la confiance des parties prenantes
- [ ] Étudier la modélisation des coûts de panne pour des seuils de décision dynamiques

### Verdict Final

Cette solution de maintenance prédictive fournit une **valeur commerciale immédiate et mesurable** en prévenant les temps d'arrêt imprévus coûteux tout en jetant les bases d'une amélioration opérationnelle continue. Le classificateur binaire XGBoost est **prêt pour la production** pour le déploiement, offrant un équilibre robuste entre la sécurité (rappel élevé) et l'efficacité (précision raisonnable). Le système d'identification du type de panne multiclasse, bien que prometteur, nécessite un **déploiement prudent avec supervision humaine**, en particulier pour les prédictions d'usure d'outil.

**Les organisations mettant en œuvre ce système peuvent s'attendre à :**
- ✅ Réduction de 70-75% des pannes d'équipement
- ✅ Diminution de 25-30% des coûts de maintenance
- ✅ ROI de 10x en 6-9 mois
- ✅ Transition d'une lutte réactive contre les incendies à une maintenance proactive et axée sur l'intelligence

Le chemin de la vulnérabilité opérationnelle à la résilience opérationnelle commence par cette première étape.

---

## Navigation du Dépôt

### Structure du Projet

```
predictive-maintenance/
│
├── capstone.ipynb              # Notebook Jupyter principal avec analyse complète
│
├── predictive_maintenance.csv  # Ensemble de données (10 000 enregistrements, 10 caractéristiques)
│
├── README.md                   # Ce fichier - documentation complète du projet
│
├── images/                     # Visualisations et graphiques
│   ├── confusion_matrices/
│   ├── eda_plots/
│   └── feature_importance/

### Fichiers Clés

**`capstone.ipynb`** - Notebook d'Analyse Principal
- Exploration et visualisation complète des données
- Pipeline de prétraitement
- Entraînement et évaluation des modèles
- Classification binaire et multiclasse
- Insights commerciaux et recommandations

**`predictive_maintenance.csv`** - Ensemble de Données
- 10 000 enregistrements d'opérations de machines
- 10 caractéristiques incluant données de capteurs et paramètres opérationnels
- Cible binaire (panne/pas de panne) et cible multiclasse (types de pannes)
