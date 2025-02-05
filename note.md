# Étape 1 : Initialiser un dépôt Git
mkdir git-merge-demo
cd git-merge-demo
git init

# Étape 2 : Créer un fichier index.html et ajouter du contenu
echo "<h1>Bienvenue sur Main</h1>" > index.html
git add index.html
git commit -m "Initial commit on main"

git branch develop  # Créer la branche develop
git checkout develop  # Passer sur develop

# Étape 3 : Modifier le fichier sur develop
echo "<p>Ajout d'un paragraphe sur develop</p>" >> index.html
git add index.html
git commit -m "Ajout de contenu sur develop"

git checkout main  # Revenir sur main

git merge develop  # Fusionner develop dans main

# Étape 4 : Pousser sur GitHub
git remote add origin <URL_DU_REPO>
git push -u origin main
git push origin develop
