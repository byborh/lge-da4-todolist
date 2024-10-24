# 📝 Todo List Backend - Java Spring Boot

Bienvenue dans le backend de mon application **Todo List** développée en **Java Spring Boot**. Ce projet implémente une architecture propre en suivant les principes **SOLID** et utilise des **Design Patterns** pour assurer une extensibilité et une maintenabilité exemplaires. 🚀

## 🧰 Technologies utilisées
- **Java 17** (version LTS recommandée)
- **Spring Boot** - Pour la rapidité du développement côté backend
- **Gradle (Groovy)** - Pour la gestion de dépendances
- **SQL** - Pour la base de données
- **JUnit** - Pour les tests unitaires et TDD

## 🎯 Fonctionnalités principales
- **Créer, Modifier, Supprimer et Valider** des notes.
- Support de différents **types de notes** via le **Pattern Strategy**.
- Utilisation du **Pattern Factory** pour créer dynamiquement des types de notes.

## 💡 Architecture du projet

J'ai utilisé une approche modulaire et respecté les principes **SOLID** :

- **S**ingle Responsibility: Chaque classe a une seule responsabilité bien définie.
- **O**pen/Closed: Le système est ouvert à l'extension avec de nouveaux types de notes sans toucher au code existant.
- **L**iskov Substitution: Toutes les classes qui implémentent `Note` sont interchangeables.
- **I**nterface Segregation: L'interface `Note` est précise et claire, sans méthode inutile.
- **D**ependency Inversion: Nous dépendons d'abstractions (interfaces), pas d'implémentations concrètes.

## 📦 Structure des classes

Voici un aperçu de la structure des principales classes dans ce backend :

### `User` 👤
- Variables :
    - `id` (Long)
    - `username` (String)
    - `listNote` (ListNote)

### `ListNote` 📋
- Variables :
    - `notes` (List<Note>)
- Méthodes :
    - `addNote()` : Ajouter une nouvelle note
    - `removeNote()` : Supprimer une note
    - `getNotes()` : Récupérer toutes les notes

### `Note` (Interface) 📝
- Méthodes :
    - `getTitle()` : Retourne le titre de la note
    - `?getContent()` : Retourne le contenu de la note
    - `getCreationDate()` : Retourne la date de création

### `TextNote` 📝✏️
- Variables :
    - `title` (String)
    - `creationDate` (LocalDateTime)

### `LongTextNote` 📝✅
- Variables :
    - `title` (String)
    - `content` (String)
    - `creationDate` (LocalDateTime)

### `NoteFactory` 🏭
- Méthode :
    - `createNote()` : Crée dynamiquement une nouvelle note en fonction du type

## ⚙️ Design Patterns utilisés

- **Strategy Pattern** : Pour permettre la création et l'utilisation de différents types de notes (`TextNote`, `ChecklistNote`).
- **Factory Pattern** : Pour gérer la création de notes via la classe `NoteFactory` sans exposer la logique interne.

## 🛠️ Test Driven Development (TDD)

J'utilise **JUnit** pour écrire des tests unitaires et vérifier que chaque fonctionnalité du backend fonctionne comme prévu. Cela permet de s'assurer que chaque module respecte bien son contrat.

- Test unitaire pour la création d'une `Note`
- Test pour la modification et la suppression d'une `Note`
- Test pour la validation des données de l'utilisateur

## 📂 Démarrage du projet

1. Clonez ce repository :
   ```bash
   git clone git@github.com:byborh/lge-da4-todolist-backend.git
   ```
2. Naviguez dans le dossier :
   ```bash
   cd todolist-backend
   ```
3. Lancez l'application avec **Gradle** :
   ```bash
   ./gradlew bootRun
   ```

## 📌 Conclusion

Ce backend a été conçu dans un souci de **propreté du code** et de **maintenabilité**. Grâce à l'application des **principes SOLID** et des **Design Patterns**, il est facile d'ajouter de nouvelles fonctionnalités sans toucher au code existant. 🎉

Contribuez et améliorez cette application pour l'adapter à vos besoins futurs ! 😎