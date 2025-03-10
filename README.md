# Cours complet de JavaScript pour débutants

## Introduction au JavaScript

### Qu'est-ce que JavaScript ?

JavaScript est un langage de programmation qui permet d'ajouter de l'interactivité aux sites web. Contrairement à HTML (structure) et CSS (style), JavaScript apporte le comportement dynamique à vos pages web.

### Pourquoi apprendre JavaScript ?

- C'est l'un des langages les plus populaires au monde
- Essentiel pour le développement web moderne
- Permet de créer des applications web interactives
- Base pour de nombreux frameworks (React, Vue, Angular)
- Utilisable côté client ET côté serveur (avec Node.js)

## Les bases du JavaScript

### Configuration de l'environnement

Pour commencer à coder en JavaScript, vous avez besoin de :

1. Un navigateur web (Chrome, Firefox, etc.)
2. Un éditeur de code (VS Code, Sublime Text, etc.)

### Insérer du JavaScript dans une page HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Ma première page JavaScript</title>
    <!-- JavaScript interne -->
    <script>
      // Votre code JavaScript ici
    </script>
  </head>
  <body>
    <h1>Bonjour</h1>

    <!-- JavaScript externe -->
    <script src="monscript.js"></script>

    <!-- JavaScript en ligne -->
    <button onclick="alert('Bonjour!')">Cliquez-moi</button>
  </body>
</html>
```

### Afficher des données

```javascript
// Dans la console
console.log("Bonjour depuis la console!");

// Dans une boîte de dialogue
alert("Bonjour!");

// Dans la page HTML
document.write("Bonjour sur la page!");

// Modifier un élément HTML
document.getElementById("monElement").innerHTML = "Nouveau texte";
```

## Les variables et types de données

### Déclaration de variables

```javascript
// Méthodes modernes (recommandées)
let nom = "Marie"; // Variable pouvant être modifiée
const age = 25; // Constante (ne peut pas être modifiée)

// Ancienne méthode (évitez si possible)
var ville = "Paris";
```

### Types de données principaux

```javascript
// Chaîne de caractères (string)
let prenom = "Jean";

// Nombres (number)
let age = 25;
let prix = 19.99;

// Booléens (boolean)
let estVrai = true;
let estFaux = false;

// Tableau (array)
let couleurs = ["rouge", "vert", "bleu"];

// Objet (object)
let personne = {
  nom: "Dupont",
  prenom: "Marie",
  age: 30,
};

// Valeurs spéciales
let vide = null;
let indefini = undefined;
```

### Opérations sur les variables

```javascript
// Opérations arithmétiques
let somme = 5 + 3; // 8
let difference = 10 - 4; // 6
let produit = 3 * 4; // 12
let quotient = 20 / 5; // 4
let reste = 10 % 3; // 1 (reste de la division)

// Incrémentation/décrémentation
let compteur = 1;
compteur++; // compteur = 2
compteur--; // compteur = 1

// Concaténation de chaînes
let prenom = "Jean";
let nom = "Dupont";
let nomComplet = prenom + " " + nom; // "Jean Dupont"

// Template literals (modernes et recommandés)
let presentation = `Je m'appelle ${prenom} ${nom} et j'ai ${age} ans.`;
```

## Les structures de contrôle

### Conditions

```javascript
// If, else if, else
let age = 18;

if (age < 18) {
  console.log("Vous êtes mineur");
} else if (age === 18) {
  console.log("Vous venez tout juste d'être majeur");
} else {
  console.log("Vous êtes majeur");
}

// Opérateur ternaire
let statut = age >= 18 ? "Majeur" : "Mineur";

// Switch
let jour = 2;
switch (jour) {
  case 1:
    console.log("Lundi");
    break;
  case 2:
    console.log("Mardi");
    break;
  default:
    console.log("Autre jour");
}
```

### Boucles

```javascript
// For
for (let i = 0; i < 5; i++) {
  console.log(`Itération ${i}`);
}

// While
let compteur = 0;
while (compteur < 5) {
  console.log(`Compteur: ${compteur}`);
  compteur++;
}

// Do While
let num = 0;
do {
  console.log(`Numéro: ${num}`);
  num++;
} while (num < 3);

// For...of (pour les tableaux)
let fruits = ["pomme", "banane", "orange"];
for (let fruit of fruits) {
  console.log(fruit);
}

// For...in (pour les objets)
let personne = { nom: "Dupont", prenom: "Marie", age: 30 };
for (let propriete in personne) {
  console.log(`${propriete}: ${personne[propriete]}`);
}
```

## Les fonctions

### Déclaration de fonctions

```javascript
// Fonction classique
function direBonjour(nom) {
  return `Bonjour ${nom} !`;
}

// Fonction anonyme
let auRevoir = function (nom) {
  return `Au revoir ${nom} !`;
};

// Fonction fléchée (ES6+)
const saluer = (nom) => {
  return `Salut ${nom} !`;
};

// Version courte des fonctions fléchées
const saluerCourt = (nom) => `Hey ${nom} !`;
```

### Appeler une fonction

```javascript
let message = direBonjour("Marie");
console.log(message); // Affiche: "Bonjour Marie !"

console.log(auRevoir("Pierre")); // Affiche: "Au revoir Pierre !"
```

### Portée des variables

```javascript
// Variables globales vs locales
let globale = "Je suis globale";

function maFonction() {
  let locale = "Je suis locale";
  console.log(globale); // Accessible
  console.log(locale); // Accessible
}

maFonction();
console.log(globale); // Accessible
// console.log(locale);    // Erreur! Non accessible
```

## Tableaux et objets

### Manipulation des tableaux

```javascript
// Créer un tableau
let fruits = ["pomme", "banane", "orange"];

// Accéder aux éléments
console.log(fruits[0]); // "pomme"

// Modifier un élément
fruits[1] = "fraise";

// Longueur du tableau
console.log(fruits.length); // 3

// Ajouter des éléments
fruits.push("kiwi"); // Ajoute à la fin
fruits.unshift("mangue"); // Ajoute au début

// Supprimer des éléments
fruits.pop(); // Supprime le dernier
fruits.shift(); // Supprime le premier

// Trouver un élément
let position = fruits.indexOf("orange"); // 2

// Découper un tableau
let selection = fruits.slice(1, 3);

// Fusionner des tableaux
let legumes = ["carotte", "poivron"];
let aliments = fruits.concat(legumes);
```

### Méthodes modernes de tableau (ES6+)

```javascript
let nombres = [1, 2, 3, 4, 5];

// forEach - parcourir chaque élément
nombres.forEach((nombre) => console.log(nombre * 2));

// map - transformer chaque élément
let doubles = nombres.map((nombre) => nombre * 2);

// filter - filtrer les éléments
let supA3 = nombres.filter((nombre) => nombre > 3);

// reduce - réduire à une seule valeur
let somme = nombres.reduce((total, nombre) => total + nombre, 0);

// find - trouver le premier élément correspondant
let premier = nombres.find((nombre) => nombre > 3);
```

### Objets

```javascript
// Créer un objet
let personne = {
  nom: "Dupont",
  prenom: "Marie",
  age: 30,
  adresse: {
    rue: "123 Avenue des Champs-Élysées",
    ville: "Paris",
  },
  hobbies: ["lecture", "voyages", "cuisine"],
  saluer: function () {
    return `Bonjour, je m'appelle ${this.prenom} ${this.nom}`;
  },
};

// Accéder aux propriétés
console.log(personne.nom); // "Dupont"
console.log(personne["prenom"]); // "Marie"
console.log(personne.adresse.ville); // "Paris"
console.log(personne.hobbies[0]); // "lecture"

// Appeler une méthode
console.log(personne.saluer()); // "Bonjour, je m'appelle Marie Dupont"

// Ajouter/modifier des propriétés
personne.email = "marie.dupont@exemple.fr";
personne.age = 31;

// Supprimer une propriété
delete personne.hobbies;
```

## DOM (Document Object Model)

### Sélectionner des éléments

```javascript
// Par ID
let titre = document.getElementById("monTitre");

// Par classe
let paragraphes = document.getElementsByClassName("para");

// Par balise
let boutons = document.getElementsByTagName("button");

// Avec les sélecteurs CSS (méthodes modernes)
let element = document.querySelector(".classe"); // Premier élément
let elements = document.querySelectorAll("p.special"); // Tous les éléments
```

### Modifier le contenu HTML

```javascript
// Changer le texte
element.textContent = "Nouveau texte";

// Changer le HTML
element.innerHTML = "<strong>Texte en gras</strong>";

// Modifier les attributs
element.setAttribute("class", "highlight");
element.id = "nouveauId";

// Modifier le style
element.style.color = "red";
element.style.fontSize = "20px";
element.style.display = "none"; // Cacher l'élément
```

### Manipuler les classes CSS

```javascript
// Ajouter une classe
element.classList.add("active");

// Supprimer une classe
element.classList.remove("old");

// Basculer une classe (ajouter si absente, retirer si présente)
element.classList.toggle("visible");

// Vérifier si une classe existe
if (element.classList.contains("important")) {
  console.log("L'élément est important!");
}
```

### Naviguer dans le DOM

```javascript
// Accéder aux parents, enfants, voisins
let parent = element.parentNode;
let enfant = element.children[0];
let suivant = element.nextElementSibling;
let precedent = element.previousElementSibling;
```

### Créer et supprimer des éléments

```javascript
// Créer un élément
let nouveauPara = document.createElement("p");
nouveauPara.textContent = "Nouveau paragraphe";

// Ajouter l'élément au DOM
document.body.appendChild(nouveauPara); // À la fin
parent.insertBefore(nouveauPara, reference); // Avant un élément

// Supprimer un élément
element.remove(); // Méthode moderne
// OU
parent.removeChild(element); // Méthode ancienne
```

## Événements

### Ajouter des écouteurs d'événements

```javascript
// Méthode moderne (recommandée)
let bouton = document.getElementById("monBouton");

bouton.addEventListener("click", function (event) {
  console.log("Bouton cliqué!");
  console.log(event); // Objet événement
});

// Avec une fonction fléchée
bouton.addEventListener("click", (e) => {
  console.log("Clic avec fonction fléchée");
});

// Avec une fonction nommée
function gererClic(e) {
  console.log("Fonction nommée");
}
bouton.addEventListener("click", gererClic);

// Supprimer un écouteur
bouton.removeEventListener("click", gererClic);
```

### Types d'événements courants

```javascript
// Événements de souris
element.addEventListener("click", handler); // Clic
element.addEventListener("dblclick", handler); // Double-clic
element.addEventListener("mouseover", handler); // Souris entre
element.addEventListener("mouseout", handler); // Souris sort
element.addEventListener("mousedown", handler); // Souris appuyée
element.addEventListener("mouseup", handler); // Souris relâchée

// Événements de clavier
document.addEventListener("keydown", handler); // Touche appuyée
document.addEventListener("keyup", handler); // Touche relâchée
document.addEventListener("keypress", handler); // Touche pressée (caractère)

// Événements de formulaire
form.addEventListener("submit", handler); // Soumission
input.addEventListener("focus", handler); // Focus sur élément
input.addEventListener("blur", handler); // Perte de focus
input.addEventListener("change", handler); // Valeur changée
input.addEventListener("input", handler); // Saisie en cours

// Événements de fenêtre
window.addEventListener("load", handler); // Page chargée
window.addEventListener("resize", handler); // Redimensionnement
window.addEventListener("scroll", handler); // Défilement
```

### Propagation des événements

```javascript
// La propagation des événements se fait en deux phases :
// 1. Phase de capture (du haut vers le bas)
// 2. Phase de bouillonnement (du bas vers le haut)

// Par défaut, les écouteurs sont activés pendant la phase de bouillonnement
element.addEventListener("click", handler); // Troisième argument par défaut: false

// Pour capturer pendant la phase de capture
element.addEventListener("click", handler, true);

// Arrêter la propagation
function handler(e) {
  e.stopPropagation(); // Empêche l'événement de continuer
}

// Empêcher le comportement par défaut
function submitHandler(e) {
  e.preventDefault(); // Empêche la soumission du formulaire
}
form.addEventListener("submit", submitHandler);
```

## Requêtes AJAX et Fetch API

### Fetch API (méthode moderne)

```javascript
// Requête GET simple
fetch("https://api.exemple.com/donnees")
  .then((response) => {
    if (!response.ok) {
      throw new Error("Erreur réseau");
    }
    return response.json(); // Convertit la réponse en JSON
  })
  .then((data) => {
    console.log(data); // Utilise les données
  })
  .catch((error) => {
    console.error("Problème avec la requête:", error);
  });

// Requête POST
fetch("https://api.exemple.com/envoyer", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    nom: "Jean",
    age: 25,
  }),
})
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error(error));
```

### Async/Await (ES8+)

```javascript
// Version moderne avec async/await
async function obtenirDonnees() {
  try {
    const response = await fetch("https://api.exemple.com/donnees");

    if (!response.ok) {
      throw new Error("Erreur réseau");
    }

    const data = await response.json();
    console.log(data);
    return data;
  } catch (error) {
    console.error("Erreur:", error);
  }
}

// Utilisation
obtenirDonnees();
```

## JavaScript moderne (ES6+)

### Let et Const

```javascript
// let: portée de bloc, peut être modifié
// const: portée de bloc, ne peut pas être modifié
```

### Template Literals

```javascript
const nom = "Marie";
const message = `Bonjour ${nom}, bienvenue!`;
```

### Fonctions fléchées

```javascript
const somme = (a, b) => a + b;
```

### Paramètres par défaut

```javascript
function saluer(nom = "visiteur") {
  return `Bonjour ${nom}`;
}
```

### Déstructuration

```javascript
// Pour les tableaux
const [a, b] = [1, 2];

// Pour les objets
const { nom, age } = personne;
```

### Opérateur de propagation (Spread)

```javascript
// Copier un tableau
const copie = [...original];

// Fusionner des tableaux
const fusion = [...tableau1, ...tableau2];

// Copier un objet
const copieObj = { ...original };

// Fusionner des objets
const fusionObj = { ...obj1, ...obj2 };
```

### Classes

```javascript
class Personne {
  constructor(nom, age) {
    this.nom = nom;
    this.age = age;
  }

  saluer() {
    return `Bonjour, je m'appelle ${this.nom}`;
  }

  static creerAnonyme() {
    return new Personne("Anonyme", 0);
  }
}

// Héritage
class Employe extends Personne {
  constructor(nom, age, poste) {
    super(nom, age);
    this.poste = poste;
  }

  sePresenter() {
    return `${super.saluer()}. Je suis ${this.poste}.`;
  }
}
```

### Modules (Import/Export)

```javascript
// Dans utils.js
export function sum(a, b) {
  return a + b;
}
export const PI = 3.14159;

// Dans main.js
import { sum, PI } from "./utils.js";
// OU
import * as Utils from "./utils.js";
```

### Promesses

```javascript
const maPromesse = new Promise((resolve, reject) => {
  setTimeout(() => {
    if (Math.random() > 0.5) {
      resolve("Succès!");
    } else {
      reject("Échec!");
    }
  }, 1000);
});

maPromesse.then((resultat) => console.log(resultat)).catch((erreur) => console.error(erreur));
```

## Projets pratiques pour débutants

1. **Calculatrice simple**
   - Créer une calculatrice avec les 4 opérations de base
   - Interface utilisateur avec boutons et affichage
2. **Liste de tâches (Todo List)**
   - Ajouter/supprimer des tâches
   - Marquer les tâches comme terminées
   - Stocker les tâches dans le localStorage
3. **Quiz interactif**
   - Questions à choix multiples
   - Calcul du score
   - Affichage des résultats
4. **Horloge numérique**

   - Afficher l'heure actuelle
   - Mise à jour en temps réel
   - Possibilité d'ajouter chronomètre/minuteur

5. **Météo simple**
   - Utiliser une API météo
   - Afficher les conditions pour une ville
   - Interface utilisateur attrayante

## Ressources d'apprentissage

### Sites web

- MDN Web Docs (Mozilla Developer Network)
- JavaScript.info
- W3Schools JavaScript
- FreeCodeCamp
- Codecademy

### Livres

- "Eloquent JavaScript" par Marijn Haverbeke
- "JavaScript: The Good Parts" par Douglas Crockford
- "You Don't Know JS" par Kyle Simpson

### Outils

- JSFiddle
- CodePen
- VS Code avec extensions JavaScript
- Chrome DevTools

## Conclusion

JavaScript est un langage puissant qui peut sembler intimidant au début, mais qui devient très gratifiant une fois que vous maîtrisez les bases. La pratique régulière est la clé pour progresser. Commencez par de petits projets et augmentez progressivement la complexité.

Bonne programmation!
