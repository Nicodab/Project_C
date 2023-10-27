# Project_C

Pré-requis:
- OS: Linux
- installer Docker > v20.0.3

------
### Récupérer le projet
Cette étape permet de de récupérer le projet C de table de correspondance chaînes-condensats codé en C.
```bash
  git clone https://github.com/Nicodab/Project_C.git
  cd Project_C
```
Remarque: une fois dans dossier du projet à la racine, nous avons un Dockerfile qui va nous servir à construre l'image docker contenant toutes les librairies et fichiers source necéssaire de mon projet pour faire tourner l'application dans un conteneur.
### Construction de l'image Docker
```bash
  docker build -t nomImage .
  docker run -it nomImage
```

Une fois dans le conteneur docker vous aurez accès au dossier 'app' qui contient les fichiers sources dans le dossier src, le Makefile dont le Dockerfile s'est servi pour compiler le projet.  
La compilation ayant déjà été un succès, vous trouverez le fichier exécutable **finalproject**.

### Exécution depuis le conteneur
Mode G: génération de la table de correspondance chaînes-condensats.
Depuis un fichier texte *inputFile* contenant des chaînes de caractères, une table de correspondance (T3C) *outputFile* sera crée avec ":" comme séparateur.
```bash
  ./finalproject -G <inputFile> -o <outputFile>
```

Mode L: Lecture de la table de correspondance)  
Depuis une T3C, le programme construit son arbre binaire.
remarque: Avec l'option *--balanced*, un arbre binaire de recherche équilibré est construit à partir de l'arbre binaire crée lors de la lecture du fichier d'entrée pour le mode L.
```bash
  ./finalproject -L <inputFile>
```

L'algorithme de chiffrement par défaut est le SHA256.

