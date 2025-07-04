# Compta-IA-salaires-p1

Ce projet vise à automatiser la génération d'écritures comptables à partir de documents PDF tels que les fiches de paie, en combinant vision par ordinateur et traitement de texte.

## Partie 1 : Reconnaissance des fiches de paie (préapprentissage)

Cette première étape consiste à entraîner un modèle à reconnaître les fiches de paie parmi d'autres types de documents. Ce **préapprentissage** sera ensuite transféré dans la suite du projet pour l'extraction des informations comptables.

---

##  Objectifs de cette première partie

-  Créer des **fiches de salaire fictives**
-  Mélanger ces fiches avec un autre jeu de données (FUNSD) et unifier le format des documents (conversion en JPEG pour utiliser EfficientNetB0)
-  Appliquer de la **data augmentation** pour compenser la petite taille du dataset
-  Unifier les annotations pour faciliter l'apprentissage supervisé
-  Concevoir deux modèles :
	Un premier modèle simple pour valider la démarche
	Un second modèle plus complexe pour améliorer la performance
-  Enregistrer les poids du modèle pour une utilisation ultérieure :
	Sauvegarde complète avec `model.save`
	Sauvegarde des poids seuls avec `model.save_weights`
	Compression des poids avec TensorFlow Lite (`tflite`) et optimisation en `float16` pour réduire la taille
-  Exporter l’apprentissage pour le réutiliser dans le second notebook

---

## Difficultés rencontrées

-  Le jeu de données était **trop petit pour un entraînement robuste.**
-  Les documents provenant de différentes sources (fiches et FUNSD) nécessitaient une **uniformisation des formats et annotations.**
-  La mise en place d’un pipeline simple mais efficace pour un **premier prototype fonctionnel.**

Cette partie a surtout servi à valider la démarche et à préparer un préapprentissage utile pour la suite du projet.

---
