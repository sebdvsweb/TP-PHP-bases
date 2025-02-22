# 📌 TP : Gestionnaire de Contacts en PHP

## 🎯 Objectif  
Créer un programme PHP permettant de gérer une liste de contacts sous forme de tableau associatif.

---

## ✍️ Consignes  

### 1️⃣ Création du tableau des contacts  
- Crée un tableau `$contacts` contenant des contacts.  
- Chaque contact est un tableau associatif avec les clés :  
  - `'nom'`  
  - `'prenom'`  
  - `'telephone'`  
  - `'genre'` (valeurs possibles : `'fille'` ou `'garçon'`)  

**Exemple de structure d'un contact :**  
```php
$contacts = [
    ['nom' => 'Dupont', 'prenom' => 'Jean', 'telephone' => '0601020304', 'genre' => 'garçon']
];
```

**Exemple pour récupérer un champ du tableau :**
```php
echo $contacts[0]['nom']; // Affichera "Dupont"
```

**Boucles foreach :**
- Pour chcune des fonctions ci-dessous, vous devrez passer par une boucle foreach pour parcourir votre tableau de contacts.

```php
foreach ($contacts as $contact) {
  // code PHP
}
```

## 🔍 Explication du symbole `&` devant `&$contacts`  

Dans certaines fonctions, nous utilisons le symbole `&` devant le paramètre `$contacts`, comme dans :  

```php
function ajouterContact(&$contacts, $nom, $prenom, $telephone, $genre) {
    $contacts[] = ['nom' => $nom, 'prenom' => $prenom, 'telephone' => $telephone, 'genre' => $genre];
}
```

**📌 Que signifie &$contacts ?**

Le & permet de passer le tableau par référence, et non par valeur.
Si nous ne mettions pas &, la fonction travaillerait sur une copie du tableau, et les modifications ne seraient pas appliquées au tableau original.

## 2️⃣ Fonction d'affichage des contacts  
- Écrire une fonction `afficherContacts($contacts)` qui affiche tous les contacts sous forme de liste.  

---

## 3️⃣ Ajout d'un contact  
- Écrire une fonction `ajouterContact(&$contacts, $nom, $prenom, $telephone, $genre)` qui permet d'ajouter un contact.  

📌 **Explication de `$contacts[] = [...]` :**  
- Cette notation ajoute un nouvel élément à la fin du tableau `$contacts`.  
- En PHP, les tableaux sont dynamiques, donc pas besoin de préciser un index.  

---

## 4️⃣ Recherche d’un contact  
- Écrire une fonction `rechercherContact($contacts, $nom)` qui recherche un contact par son nom et affiche ses informations.  

---

## 5️⃣ Modification d’un contact  
- Écrire une fonction `modifierContact(&$contacts, $nom, $nouveauPrenom, $nouveauTelephone)` qui modifie le prénom et le numéro de téléphone d’un contact existant.  

---

## 6️⃣ Suppression d’un contact  
- Écrire une fonction `supprimerContact(&$contacts, $nom)` qui supprime un contact du tableau.  

📌 **Explication de `unset($contacts[$index])` :**  
- `unset()` est une fonction PHP qui permet de supprimer une variable ou un élément d’un tableau.  
- Dans notre cas, `unset($contacts[$index])` supprime l’entrée du tableau correspondant à l’index trouvé.  
- Comme la suppression crée un "trou" dans l'indexation du tableau, on utilise `array_values($contacts)` pour réorganiser les index du tableau.  

---

## 7️⃣ Affichage des contacts par genre  
- Écrire une fonction `afficherContactsParGenre($contacts)` qui affiche d’un côté les filles et de l’autre les garçons sous forme de listes.  

## 📋 Liste des Contacts (exemple)  
Voici une liste de contacts que vous devez intégrer sous forme d'un tableau associatif :  

### 👦 Garçons  
- **Dupont Jean** - 0601020304  
- **Elaaziz Abdel** - 0645678901  
- **Nguyen Bao** - 0656789012  
- **Garcia Hugo** - 0678901234   

### 👧 Filles  
- **Durand Sophie** - 0612345678  
- **Lemoine Claire** - 0667890123  
- **Rousseau Emma** - 0689012345
- **Da Silva Carla** - 0690123456  

📌 **À vous de transformer cette liste en un tableau PHP et de coder les différentes fonctionnalités demandées ! 🚀**  

