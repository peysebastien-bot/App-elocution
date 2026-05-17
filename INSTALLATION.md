# 📱 Installation de "Reprendre la parole" sur Android

Votre application a été transformée en **Progressive Web App (PWA)**, ce qui signifie qu'elle peut être installée comme une vraie app sur Android, tout en restant du pur HTML/CSS/JavaScript.

---

## 📂 Structure des fichiers

Voici comment organiser vos fichiers :

```
mon-app-elocution/
├── index.html              # Le cœur de l'application (renommé)
├── manifest.json           # Métadonnées PWA
├── service-worker.js       # Pour fonctionnement hors ligne
├── icon.svg                # Icône source (optionnelle après conversion)
├── icon-192.png            # Icône 192x192 (À GÉNÉRER)
├── icon-512.png            # Icône 512x512 (À GÉNÉRER)
└── icon-maskable-*.png     # Versions maskable (À GÉNÉRER)
```

---

## 🎨 Étape 1 : Générer les icônes PNG

Vous avez deux options :

### **Option A : Utiliser un convertisseur en ligne (plus simple)**

1. Allez sur https://cloudconvert.com/svg-to-png
2. Uploadez le fichier `icon.svg`
3. Générez une version **192x192** et une **512x512**
4. Téléchargez et nommez-les :
   - `icon-192.png`
   - `icon-512.png`

**Pour les versions maskable** (optionnel mais recommandé) :
- Allez sur https://maskable.app/
- Uploadez les PNG générés
- Vérifiez que le design reste lisible
- Téléchargez et nommez-les :
  - `icon-maskable-192.png`
  - `icon-maskable-512.png`

### **Option B : Utiliser ImageMagick en local**
Si vous avez `ImageMagick` d'installé :
```bash
convert icon.svg -resize 192x192 icon-192.png
convert icon.svg -resize 512x512 icon-512.png
```

---

## 📤 Étape 2 : Mettre en ligne votre app

Pour que l'app soit installable sur Android, il faut qu'elle soit en ligne. Vous avez plusieurs options :

### **Option A : GitHub Pages (gratuit, facile)**

1. Créez un dossier sur votre ordinateur avec tous les fichiers
2. Créez un repo GitHub : https://github.com/new
3. Uploadez vos fichiers
4. Allez dans **Settings** → **Pages**
5. Sélectionnez **Deploy from a branch** → `main`
6. Attendez quelques secondes
7. Votre site sera accessible à : `https://votre-username.github.io/nom-du-repo`

### **Option B : Netlify (gratuit)**

1. Allez sur https://netlify.com
2. Connectez votre compte GitHub
3. Sélectionnez le repo
4. Clickez **Deploy**
5. C'est tout ! Netlify génère une URL

### **Option C : Vercel (gratuit)**

1. Allez sur https://vercel.com
2. Importez votre repo GitHub
3. Cliquez **Deploy**
4. L'app est en ligne en quelques secondes

### **Option D : Serveur personnel**

Si vous avez un serveur, uploadez simplement les fichiers via FTP/SFTP.

---

## 📱 Étape 3 : Installer sur Android

Une fois votre app en ligne, voici comment l'installer sur votre téléphone Android :

### **Via Chrome (méthode 1)**

1. Ouvrez Chrome sur votre téléphone Android
2. Allez à l'URL de votre app
3. Attendez 1-2 secondes
4. Un menu devrait apparaître en bas : **"Installer l'application"**
5. Cliquez dessus
6. L'app s'ajoute à votre écran d'accueil

### **Via menu Chrome (méthode 2)**

1. Ouvrez l'app dans Chrome
2. Cliquez sur le menu **⋮** (trois points) en haut à droite
3. Sélectionnez **"Installer l'application"**
4. Confirmez

### **Ajouter à l'écran d'accueil (méthode 3)**

1. Ouvrez l'app dans Chrome
2. Cliquez sur le menu **⋮**
3. Sélectionnez **"Ajouter à l'écran d'accueil"**
4. Confirmez et personnalisez le nom si vous voulez

---

## ✨ Avantages de la PWA

Une fois installée, votre app :
- ✅ S'ouvre comme une vraie app (sans barre d'adresse)
- ✅ Fonctionne **hors ligne** (grâce au service worker)
- ✅ Peut accéder au microphone
- ✅ Se lance directement depuis l'écran d'accueil
- ✅ Se met à jour automatiquement quand vous modifiez le code

---

## 🔧 Troubleshooting

### **L'app n'apparaît pas en haut du Chrome ?**

- Vérifiez que votre site est en **HTTPS** (obligatoire pour PWA)
- Attendez 30 secondes que Chrome la détecte
- Rafraîchissez la page (Ctrl+R)
- Essayez via le menu **⋮**

### **Le micro ne fonctionne pas après installation ?**

- Allez dans **Paramètres** → **Applications** → **Reprendre la parole**
- Accordez la permission pour le **Microphone**

### **Les polices Google ne se chargent pas hors ligne ?**

- C'est normal pour la première visite (elles se cachent)
- Visitez l'app une première fois avec internet
- Les polices seront cachées pour les visites suivantes

### **L'icône n'apparaît pas ?**

- Vérifiez que les fichiers `icon-192.png` et `icon-512.png` sont au même niveau que `index.html`
- Videz le cache du navigateur et réinstallez l'app

---

## 📝 Fichiers reçus

Vous avez reçu :

- ✅ **index.html** — Votre app complète (renommée depuis programme-elocution.html)
- ✅ **manifest.json** — Métadonnées PWA (nom, couleurs, icônes)
- ✅ **service-worker.js** — Permet le fonctionnement hors ligne
- ✅ **icon.svg** — Icône source (à convertir en PNG)
- 📄 **INSTALLATION.md** — Ce fichier

---

## 🚀 Résumé rapide

1. Convertissez `icon.svg` en `icon-192.png` et `icon-512.png`
2. Mettez tous les fichiers en ligne (GitHub Pages, Netlify, etc.)
3. Ouvrez l'app sur Android dans Chrome
4. Installez-la via le menu Chrome
5. Profitez ! 🎉

---

## 💡 Pour modifier l'app

Si vous voulez modifier quelque chose (textes, couleurs, phrases), éditez simplement `index.html` avec un éditeur de texte :

- **Textes** : Cherchez le texte et modifiez-le
- **Couleurs** : Cherchez les codes hexa comme `#c9956b` (couleur principale) et `#1a1a1a` (fond)
- **Exercices** : Trouvez la section `<div class="exercise">` et modifiez

Sauvegardez et uploadez le fichier modifié. L'app se mettra à jour automatiquement ! 

---

**Questions ?** N'hésitez pas si vous avez besoin d'aide ! 😊
