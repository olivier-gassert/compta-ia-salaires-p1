# Compta-IA-salaires-p1

Ce projet vise à automatiser la génération d'écritures comptables à partir de documents PDF tels que les fiches de paie, en combinant vision par ordinateur et traitement de texte.

## Partie 1 : Reconnaissance des fiches de paie (préapprentissage)

Cette première étape consiste à entraîner un modèle à reconnaître les fiches de paie parmi d'autres types de documents. Ce **préapprentissage** sera ensuite transféré dans la suite du projet pour l'extraction des informations comptables.

---

## Objectifs de cette première partie

### Constitution du dataset

Créer des **fiches de salaire fictives**
Mélanger ces fiches avec un autre jeu de données (FUNSD) et unifier le format des documents (conversion en JPEG pour utiliser EfficientNetB0)
Unifier les annotations pour faciliter l'apprentissage supervisé

### Préparation

Uniformisation des images (taille, type, niveaux de gris)
Scission train/test
Conversion en tableaux NumPy
Structure d’accueil des labels

-  Créer des **fiches de salaire fictives**
-  Mélanger ces fiches avec un autre jeu de données (FUNSD) et unifier le format des documents (conversion en JPEG pour utiliser EfficientNetB0)
-  Appliquer de la **data augmentation** pour compenser la petite taille du dataset
-  Unifier les annotations pour faciliter l'apprentissage supervisé
-  Concevoir deux modèles :
	-- Un premier modèle simple pour valider la démarche
	-- Un second modèle plus complexe pour améliorer la performance
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

##  Données utilisées

Les images utilisées dans ce projet proviennent de deux sources :

-  Un dataset personnel que j'ai créé, comprenant :
	Fiches de paie fictives (au format JPEG)
	Annotations associées (au format JSON)

➡️ Ces données peuvent être utilisées à des fins non commerciales.  
➡️ Je dispose d'autres exemples disponibles sur demande.  
➡️ Je serais reconnaissant si vous me citez si vous utilisez ce dataset, mais cela reste facultatif.

-  Le dataset FUNSD : [https://guillaumejaume.github.io/FUNSD/](https://guillaumejaume.github.io/FUNSD/)

➡️ Le dataset FUNSD est fourni à des fins non commerciales.  
➡️ Les annotations utilisées dans ce projet sont personnelles et ne proviennent pas du dataset original.

##  Merci de citer :

@inproceedings{jaume2019,  
    title = {FUNSD: A Dataset for Form Understanding in Noisy Scanned Documents},  
    author = {Guillaume Jaume, Hazim Kemal Ekenel, Jean-Philippe Thiran},  
    booktitle = {Accepted to ICDAR-OST},  
    year = {2019}  
}

##  Citation suggérée :

@dataset{Gassert2025,  
    author = {Olivier Gassert},  
    title = {Échantillon de dataset de fiches de paie fictives},  
    year = {2025},  
    note = {Disponible dans le projet GitHub : Compta-IA-salaires-p1}  
}

