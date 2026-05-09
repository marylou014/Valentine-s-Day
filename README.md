# 💖 Valentine's Day Project

Ce projet est un projet interactif, ludique et romantique conçu pour poser la question : **"Veux-tu être mon Valentine ?"** à mon copain. Ce dépôt contient une série d'étapes et de mini-jeux pour mener vers la question finale.

## 🚀 Caractéristiques & Mini-Jeux

Le projet ne se contente pas d'une simple question ; il propose un véritable parcours :

1. **La Vérification d'Identité** : Un écran d'accueil "sécurisé" (et personnalisé) qui demande le nom et le prénom pour s'assurer que le message est adressé à la bonne personne. Avec un message d'erreur si les informations sont incorrectes.
2. **Le Jeu des Cœurs / le quizz** : Une phase interactive où l'utilisateur doit répondre à des questions à choix multiple, avec des éléments visuels pour débloquer la suite. Chaque bonne réponse mène à la question suivante.
3. **Le Casse-Tête du "Non"** : Un classique revisité où le bouton "Non" fuit le curseur de la souris ou se déplace aléatoirement, rendant le refus techniquement (et sentimentalement) impossible.
4. **La Récompense Finale** : Une animation de célébration une fois que le "Oui" est enfin cliqué et la possibilité d'ouvrir 3 "cadeaux" (des coupons).

## 🏗️ Infrastructure Technique

Le projet est conçu pour être **léger, rapide et sans dépendances lourdes**, facilitant son déploiement sur n'importe quel hébergeur statique.

* **Frontend** : HTML et CSS pour une structure sémantique et une mise en page moderne (Flexbox/Grid).
* **Interactivité** : JavaScript. Aucun framework (comme React ou Vue) n'est requis, ce qui garantit un temps de chargement quasi instantané.
* **Animations** : Utilisation des `keyframes` CSS et des transitions JS pour une fluidité optimale, même sur les navigateurs mobiles.
* **Hébergement** : Compatible avec **GitHub Pages**, et peut aussi être utilisé en local.

## 📦 Installation

1. **Cloner le dépôt** :
   ```bash
   git clone https://github.com/marylou014/Valentine-s-Day.git
   ```

2. **Configuration** : Modifiez les noms dans le code source (voir section Personnalisation).
3. **Lancement** : Ouvrez `index.html` dans votre navigateur.

## 🛠️ Personnalisation (Important)

Ce projet peut être adapté à votre histoire. Voici comment modifier les éléments clés pour personnaliser l'expérience. Tous les fichiers sont dans le répertoire racine du projet.

### 1. Nom et Prénom (Vérification d'Identité)

Pour que le script fonctionne avec la personne de votre choix, vous devez modifier les variables d'identification dans le fichier `index.html`.

> [!IMPORTANT]
> **Vérification du nom** : Dans le script JavaScript intégré à `index.html`, localisez la fonction `verifierDonnee()`. Vous devez impérativement changer les valeurs des variables `bonPrenom` et `bonNom` par ceux de votre destinataire pour qu'il/elle puisse accéder aux mini-jeux. Sans cela, l'accès aux mini-jeux restera bloqué.

**Étapes :**
- Ouvrez `index.html` dans un éditeur de texte.
- Trouvez la section `<script>` en bas du fichier.
- Modifiez les lignes suivantes :
  ```javascript
  const bonPrenom = "Prénom";  // Remplacez par le prénom réel, par exemple "Marie"
  const bonNom = "Nom";        // Remplacez par le nom réel, par exemple "Dupont"
  ```
- Sauvegardez le fichier.

**Exemple :**
Si votre partenaire s'appelle "Jean Dupont", changez en :
```javascript
const bonPrenom = "Jean";
const bonNom = "Dupont";
```

### 2. Modifier le Quiz

Vous pouvez changer les questions et les réponses pour les rendre plus personnelles. Les questions sont définies directement dans le fichier `jeux.html`.

**Étapes :**
- Ouvrez `jeux.html` dans un éditeur de texte.
- Chaque question est dans une `<div class="card quiz-container">`.
- Pour modifier une question :
  - Changez le texte dans `<h2>Question X : [Votre question]</h2>`.
  - Modifiez les options dans les `<div class="option">` :
    - Changez le texte dans `<span>[Option]</span>`.
    - Si c'est une image, remplacez `src="img/[image].png"` par votre image (placez-la dans le dossier `img/`).
  - Dans le bouton `<button onclick="verifierReponse(X, '[reponse_correcte]')">`, changez `'[reponse_correcte]'` par la nouvelle valeur correcte.
- Pour ajouter une question, copiez une section entière de quiz (par exemple, de `<div class="card quiz-container" id="quiz1">` à `</div>`), changez l'ID (quiz6, etc.), et ajustez les fonctions JavaScript si nécessaire.

**Exemple :**
Pour changer la Question 1 :
- Original : `<h2>Question 1 : Mes fleurs préférées ?</h2>`
- Modifié : `<h2>Question 1 : Quel est mon film préféré ?</h2>`
- Changez les options : `<span>Les Roses</span>` en `<span>Titanic</span>`, etc.
- Mettez à jour `onclick="verifierReponse(1, 'titanic')"` (et ajustez les IDs).

Vous pouvez ajouter autant de questions que vous le souhaitez pour prolonger le quizz !

### 3. Personnaliser les Cadeaux et la Fin

À la fin du parcours, une section "Cadeaux" apparaît avec des images de coupons. Pour la modifier :

**Étapes :**
- Ouvrez `cadeaux.html` dans un éditeur de texte.
- Pour changer les images des cadeaux :
  - Dans les `<div class="option" onclick="ouvrirPopUp('img/[image].PNG')">`, remplacez `'img/[image].PNG'` par le chemin de votre nouvelle image (placez-la dans `img/`).
- Pour modifier le GIF de célébration : Changez `src="img/kiss.gif"` dans `<img id="gif">`.
- Les textes des cadeaux sont dans les images elles-mêmes ; remplacez les fichiers dans `img/` par vos propres coupons personnalisés.

**Exemple :**
- Pour "Cadeau 1", changez `onclick="ouvrirPopUp('img/bon_bisou.PNG')"` en `onclick="ouvrirPopUp('img/mon_cadeau_personnel.PNG')"` et ajoutez votre image dans `img/`.

Les images et les GIFs dans ce projet proviennent de Pinterest ou ont été générés par IA. Vous pouvez les remplacer par des images personnelles pour plus de personalisation.

### Conseils Généraux
- **Images** : Toutes les images sont dans le dossier `img/`. Assurez-vous que les formats sont compatibles (PNG, JPG, GIF).
- **CSS** : Pour changer les styles (couleurs, polices), modifiez `style.css`.
- **Test** : Après modifications, ouvrez `index.html` dans un navigateur pour tester.
- **Sécurité** : Ce projet est statique ; ne stockez pas d'informations sensibles.

## ✒️ Auteur

Fait avec ❤️ par [Marylou014](https://github.com/marylou014)

_Aider en partie par l'IA_