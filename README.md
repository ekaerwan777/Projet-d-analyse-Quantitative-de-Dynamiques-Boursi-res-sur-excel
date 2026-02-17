
# Projet Analyse Quantitative des Dynamiques Boursières

### Étude comparative : AMUNDI SA – UNIBAIL SA – ROBORTET SA

## 1. Présentation du projet

Ce projet propose une analyse quantitative descriptive des dynamiques de marché de trois sociétés cotées : **AMUNDI SA**, **UNIBAIL SA** et **ROBORTET SA**.

L’objectif est de caractériser leurs comportements respectifs à travers une approche multi-échelle combinant :

* Une analyse **journalière** de la volatilité et des tendances.
* Une analyse **intraday** de l’instabilité directionnelle au sein d’une séance.

L’étude repose exclusivement sur les données contenues dans les fichiers Excel fournis. Aucune donnée externe n’a été ajoutée.

---

## 2. Structure des données

Chaque titre dispose de deux niveaux d’observation principaux :

* **Feuille `JOUR`** : données agrégées quotidiennes.
* **Feuille `MIN`** : données intraday (granularité minute).

Les indicateurs exploités sont :

### Indicateurs journaliers

* True Range (TR)
* Average True Range sur 15 jours (ATR(15))
* Simple Moving Average (SMA(15))
* Exponential Moving Average (EMA(15))
* Moyenne Mobile Centrée (MMC(15))
* Écart-type sur 15 jours (STD(15))

### Indicateurs intraday

* Couleur de la bougie (haussière / baissière)
* Indicateur binaire de changement de couleur
* Classe_Pct : segmentation de la séance en cinq quintiles temporels

---

## 3. Méthodologie

L’analyse adoptée est **descriptive et exploratoire**.
Elle vise à extraire des profils comportementaux sans construire de modèle prédictif.

La logique repose sur deux dimensions complémentaires :

### 3.1 Volatilité journalière

La volatilité est mesurée via l’ATR(15), qui capture l’amplitude moyenne des mouvements quotidiens.
Les moyennes mobiles (SMA, EMA, MMC) permettent d’identifier les phases de tendance et de consolidation.

### 3.2 Instabilité directionnelle intraday

L’instabilité est mesurée par le nombre de changements de direction au cours d’une séance.

La répartition des changements selon les quintiles de la séance permet d’identifier le moment de stabilisation directionnelle.

---

## 4. Résultats principaux

### 4.1 Profils observés

| Indicateur                         | AMUNDI SA                  | UNIBAIL SA     | ROBORTET SA                |
| ---------------------------------- | -------------------------- | -------------- | -------------------------- |
| ATR(15) moyen                      | 1.32 €                     | 3.18 €         | 16.94 €                    |
| Changements intraday moyens / jour | 7.25                       | 7.91           | 3.69                       |
| Stabilisation intraday             | Très rapide (≈ 20% séance) | Rapide (≈ 40%) | Extrêmement rapide (≈ 20%) |

### 4.2 Enseignements majeurs

1. **La volatilité et l’instabilité ne sont pas synonymes.**
   Un ATR élevé n’implique pas nécessairement une forte instabilité directionnelle.

2. **ROBORTET SA** présente une volatilité journalière très élevée mais peu de retournements intraday.
   Le titre est directionnel une fois le mouvement initial engagé.

3. **UNIBAIL SA** combine volatilité élevée et instabilité intraday marquée.
   Le comportement est plus erratique.

4. **AMUNDI SA** présente un profil intermédiaire avec une instabilité concentrée à l’ouverture.

---

## 5. Discussion critique

### 5.1 Apports

* Dissociation claire entre amplitude des mouvements (ATR) et fréquence des retournements.
* Mise en évidence de profils de marché distincts.
* Utilisation combinée de deux échelles temporelles complémentaires.

### 5.2 Limites

* Analyse purement descriptive, sans validation statistique formelle.
* Dépendance au paramétrage des indicateurs (fenêtre de 15 jours).
* Indicateur de changement binaire ne mesurant pas l’ampleur des mouvements.
* Absence de normalisation de la volatilité (ATR non rapporté au niveau de prix).

---

## 6. Perspectives d’amélioration

* Normalisation de la volatilité (ATR relatif).
* Introduction de tests statistiques pour comparer les moyennes.
* Modélisation probabiliste des transitions intraday.
* Extension de l’étude à un univers plus large (ex. CAC 40).
* Automatisation complète du processus via un script Python.

---

## 7. Contenu du dépôt

* `Rapport_Dynamique_Boursiere_final.pdf`
* `AMUNDI SA.xlsx`
* `UNIBAIL SA.xlsx`
* `ROBORTET SA.xlsx`

---

## 8. Nature du projet

Projet académique d’analyse quantitative à visée exploratoire.
Ce travail illustre une capacité à structurer, analyser et interpréter des données financières multi-échelles avec rigueur méthodologique.

---

Si tu veux, je peux maintenant :

* Te proposer une version plus orientée **finance de marché / quant**
* Ou une version plus orientée **data science / analytique**
* Ou optimiser le README pour qu’il soit percutant pour un recruteur spécifique (finance, data, consulting, etc.)
