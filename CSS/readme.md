# 📘 Documentation CSS Complète (Avec Commentaires)

## 1. Introduction à CSS

CSS (**Cascading Style Sheets**) est un langage utilisé pour décrire la présentation des pages web.

* HTML = structure (le squelette)
* CSS = style (les couleurs, tailles, mise en page)

👉 Séparation du contenu (HTML) et de la présentation (CSS).

---

## 2. Inclusion du CSS dans un projet

### a. Inline CSS

```html
<p style="color: red;">Texte en rouge</p>
```

<!-- Utilisé rarement car mélange contenu + style -->

### b. Internal CSS

```html
<style>
  p { color: red; }
</style>
```

<!-- Placé dans <head>, pratique pour une seule page -->

### c. External CSS

```html
<link rel="stylesheet" href="style.css">
```

<!-- La meilleure méthode : fichier séparé réutilisable -->

---

## 3. Syntaxe CSS

```css
sélecteur {
  propriété: valeur;
}
```

Exemple :

```css
h1 {
  color: blue;   /* Propriété couleur appliquée */
  font-size: 24px; /* Taille du texte en pixels */
}
```

---

## 4. Les Sélecteurs CSS

### a. Sélecteurs de base

```css
p { color: green; }       /* Sélectionne tous les <p> */
#idExemple { color: red; } /* Sélection par ID (unique) */
.classeExemple { color: blue; } /* Sélection par classe */
```

### b. Sélecteurs combinés

```css
div p { color: purple; }   /* Tous les <p> dans un <div> */
div > p { color: brown; }  /* <p> enfant direct de <div> */
h1, h2 { color: orange; }  /* Plusieurs sélecteurs */
```

### c. Pseudo-classes

```css
a:hover { color: red; }   /* Quand la souris passe dessus */
input:focus { border: 2px solid blue; } /* Quand actif */
```

### d. Pseudo-éléments

```css
p::first-line { font-weight: bold; } /* Première ligne */
p::before { content: "👉 "; } /* Ajoute un contenu avant */
```

---

## 5. Les Propriétés CSS Importantes

### a. Couleurs et Arrière-plan

```css
body {
  background-color: #f0f0f0; /* Couleur */
  background-image: url("image.jpg");
  background-size: cover;   /* Couvre toute la page */
}
```

### b. Texte

```css
h1 {
  font-family: Arial, sans-serif; /* Police */
  font-size: 32px;               /* Taille */
  text-align: center;             /* Alignement */
  text-transform: uppercase;      /* MAJUSCULE */
  text-decoration: underline;     /* Souligné */
}
```

### c. Boîtes (Box Model)

Chaque élément HTML est une **boîte** avec :

* **content** (contenu)
* **padding** (espace interne)
* **border** (bordure)
* **margin** (espace externe)

```css
div {
  width: 200px;
  padding: 10px;     /* espace interne */
  border: 2px solid black;
  margin: 20px;      /* espace externe */
}
```

---

## 6. Positionnement et Affichage

### a. Display

```css
div { display: block; }   /* Occupe toute la ligne */
span { display: inline; } /* Dans la ligne */
p { display: none; }      /* Masqué */
```

### b. Position

```css
.box1 { position: static; }   /* Par défaut */
.box2 { position: relative; top: 10px; } /* Relative */
.box3 { position: absolute; top: 0; left: 0; } /* Absolue */
.box4 { position: fixed; bottom: 0; } /* Fixé */
```

### c. Flexbox (mise en page moderne)

```css
.container {
  display: flex;
  justify-content: center; /* alignement horizontal */
  align-items: center;     /* alignement vertical */
}
```

### d. Grid (plus avancé)

```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 colonnes égales */
  gap: 10px; /* espace entre les cases */
}
```

---

## 7. Responsivité

### a. Unités relatives

* `px` → pixels (fixe)
* `%` → relatif au parent
* `em` / `rem` → relatif à la taille du texte

### b. Media Queries

```css
@media (max-width: 768px) {
  body { font-size: 14px; } /* Pour les petits écrans */
}
```

---

## 8. Transitions & Animations

### a. Transition

```css
button {
  background: blue;
  transition: background 0.3s ease;
}
button:hover {
  background: red; /* Changement progressif */
}
```

### b. Animation

```css
@keyframes bouger {
  from { transform: translateX(0); }
  to { transform: translateX(100px); }
}

div {
  animation: bouger 2s infinite alternate;
}
```

---

## 9. Bonnes pratiques

* Toujours utiliser un fichier CSS externe.
* Bien commenter son code `/* comme ceci */`.
* Utiliser des classes plutôt que des IDs pour réutiliser le style.
* Penser mobile-first avec **media queries**.

---

## 10. Exemple Complet

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1 class="titre">Bienvenue</h1>
  <p id="intro">Ceci est un exemple CSS</p>
  <button>Clique-moi</button>
</body>
</html>
```

```css
/* === Style global === */
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

/* === Titres === */
.titre {
  color: blue;
  text-align: center;
}

/* === Paragraphe === */
#intro {
  color: gray;
  font-size: 18px;
}

/* === Bouton avec transition === */
button {
  background: green;
  color: white;
  border: none;
  padding: 10px 20px;
  transition: background 0.5s;
}
button:hover {
  background: darkgreen;
}
```