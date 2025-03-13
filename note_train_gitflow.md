Voici un exemple de **Gitflow simplifié** pour une petite interface de fonctionnalités, en utilisant **GitHub**.  

### **1. Initialisation du projet et du dépôt GitHub**  
```sh
# Créer un nouveau projet
mkdir my-project && cd my-project

# Initialiser Git
git init

# Créer un fichier index.html et styles.css dans un dossier
mkdir src && cd src
touch index.html styles.css
cd ..

# Ajouter un fichier README.md
echo "# My Project" > README.md

# Premier commit
git add .
git commit -m "Initial commit with project structure"

# Ajouter le dépôt distant (remplace [URL_DU_REPO] par l’URL de ton repo GitHub)
git remote add origin [URL_DU_REPO]

# Pousser la branche principale
git branch -M master
git push -u origin master
```

---

### **2. Création et travail sur les branches**
```sh
# Créer et passer sur la branche develop
git checkout -b develop
git push -u origin develop

# Créer et passer sur la branche features
git checkout -b features
git push -u origin features

# Créer et passer sur la sous-branche basicFeatures
git checkout -b basicFeatures
git push -u origin basicFeatures
```

---

### **3. Implémentation des fichiers**
Ajoute du contenu minimal à **src/index.html** et **src/styles.css** :  

#### **`src/index.html`**
```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Features</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Bienvenue sur mon interface</h1>
</body>
</html>
```

#### **`src/styles.css`**
```css
body {
    font-family: Arial, sans-serif;
    text-align: center;
    background-color: #f4f4f4;
}
```

---

### **4. Commit et push des changements**
```sh
git add .
git commit -m "Ajout de l'interface de base"
git push origin basicFeatures
```

---

### **5. Merge vers `features` puis `develop`**
```sh
# Aller sur la branche features
git checkout features
git merge basicFeatures
git push origin features

# Aller sur la branche develop
git checkout develop
git merge features
git push origin develop
```

---

### **6. Pull Request vers `master`**
1. Aller sur GitHub.
2. Créer une **Pull Request** de `develop` vers `master`.
3. Valider la PR et **merger**.
4. Supprimer les branches `features` et `basicFeatures` si elles ne sont plus utiles :
   ```sh
   git branch -d basicFeatures
   git push origin --delete basicFeatures

   git branch -d features
   git push origin --delete features
   ```

Et voilà, ton interface basique est intégrée proprement en suivant **Gitflow** !
