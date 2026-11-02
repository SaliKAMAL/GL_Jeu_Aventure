# Jeu d’aventure

Projet universitaire de génie logiciel visant à analyser, concevoir et implémenter un jeu d’aventure orienté objet.

La première version sera développée en **Java avec Maven**, selon une architecture **Modèle–Vue–Contrôleur (MVC)**. Elle utilisera une interface textuelle, tout en conservant un modèle indépendant afin de permettre l’ajout ultérieur d’une interface graphique.

## Statut du projet

> Projet en phase d’analyse et de spécification.

Les règles principales du jeu ont été définies. Les cas d’utilisation, les diagrammes UML et le modèle d’analyse sont en cours d’élaboration.

## Objectif du jeu

Le joueur explore un monde composé de quatre salles reliées par des portes verrouillées. Pour atteindre le trésor, le joueur doit :

- se déplacer entre les salles ;
- observer son environnement ;
- dialoguer avec un personnage non joueur amical ;
- récupérer, transporter, utiliser et déposer des objets ;
- gérer un inventaire limité à cinq objets ;
- trouver et utiliser les clés associées aux portes ;
- éviter un personnage hostile ;
- utiliser éventuellement un objet d’étourdissement ;
- atteindre la salle finale et interagir avec le trésor.

La partie est gagnée lorsque le joueur interagit avec le trésor. Elle est perdue si le personnage hostile atteint la même position que le joueur.

## Périmètre de la version minimale

La première version comprendra :

- quatre salles créées manuellement ;
- un joueur ;
- un PNJ amical ;
- un PNJ hostile ;
- plusieurs portes verrouillées et leurs clés ;
- un inventaire de cinq emplacements ;
- un objet d’étourdissement consommable ;
- un trésor ;
- une interface textuelle ;
- une architecture MVC ;
- des tests portant sur les principales règles métier.

Les fonctionnalités suivantes sont considérées comme des extensions éventuelles :

- interface graphique en deux dimensions ;
- génération aléatoire des salles ;
- mode chronométré ;
- ennemis ou objets supplémentaires ;
- dialogues plus complexes ;
- plusieurs niveaux ;
- sauvegarde et chargement d’une partie.

## Règles principales

- Une seule salle est chargée à la fois.
- Le joueur peut revenir dans les salles déjà visitées.
- Chaque porte est initialement verrouillée et possède une clé correspondante.
- Une porte déverrouillée reste définitivement déverrouillée.
- Une clé disparaît après le déverrouillage réussi de la porte correspondante.
- Le joueur peut transporter au maximum cinq objets.
- Le joueur peut déposer un objet puis le récupérer ultérieurement.
- Le PNJ hostile se déplace après chaque déplacement valide du joueur.
- Le contact avec le PNJ hostile provoque une défaite immédiate.
- L’objet d’étourdissement est consommé immédiatement après son utilisation et empêche le PNJ hostile d’effectuer ses deux prochains déplacements.
- Le joueur doit interagir explicitement avec le trésor pour gagner.

## Progression prévue

Le monde est organisé autour de quatre salles :

1. **Salle d’entrée** : point de départ et présence du PNJ amical ;
2. **Bibliothèque abandonnée** : exploration et récupération d’une clé ;
3. **Donjon** : présence du PNJ hostile et de l’objet d’étourdissement ;
4. **Salle du trésor** : objectif final du jeu.

Le PNJ amical propose initialement au joueur une clé permettant d’explorer en premier la bibliothèque ou le donjon. Ce choix modifie l’ordre d’exploration, sans empêcher l’accès ultérieur aux autres salles.

Après la visite des deux salles d’exploration, le joueur peut obtenir la clé finale, ouvrir la salle du trésor et terminer le jeu.

## Technologies envisagées

- **Langage** : Java ;
- **Gestion du projet et compilation** : Maven ;
- **Architecture** : MVC ;
- **Tests** : JUnit ;
- **Modélisation UML** : PlantUML et/ou Visual Paradigm ;
- **Gestion de versions et collaboration** : Git et GitHub.

Les versions exactes du JDK, de Maven et des dépendances seront précisées au début de l’implémentation.

## Architecture prévue

L’application sera organisée selon l’architecture MVC :

- **Modèle** : monde, salles, joueur, PNJ, objets, inventaire, portes, trésor et règles métier ;
- **Vue** : affichage textuel et récupération des commandes ;
- **Contrôleur** : interprétation des commandes et coordination des échanges entre le modèle et la vue.

Le modèle ne devra dépendre ni du terminal ni d’une future interface graphique.

## Commandes prévues

La première interface textuelle devrait proposer les commandes suivantes :

```text
demarrer
aller nord
aller sud
aller est
aller ouest
observer
inventaire
ramasser <objet>
deposer <objet>
utiliser <objet>
interagir
aide
quitter
```

La liste définitive sera précisée pendant la conception.

## Organisation envisagée du dépôt

```text
GL_Jeu_Aventure/
├── README.md
├── pom.xml
├── docs/
│   ├── game-specification.md
│   ├── domain-glossary.md
│   ├── analyse/
│   ├── conception/
│   └── uml/
├── src/
│   ├── main/
│   │   ├── java/
│   │   └── resources/
│   └── test/
│       └── java/
└── rapport/
    └── rapport.pdf
```

Cette arborescence pourra évoluer pendant le projet.

## Documentation

La documentation du projet sera progressivement ajoutée dans le répertoire `docs/` :

- spécification fonctionnelle ;
- glossaire du domaine ;
- cas d’utilisation et descriptions détaillées ;
- diagrammes de séquence système ;
- diagramme de classes d’analyse ;
- architecture MVC ;
- diagramme de classes logicielles ;
- diagrammes de séquence de conception ;
- manuel utilisateur ;
- bilan du projet.

## Compilation et exécution

Les instructions définitives seront ajoutées lorsque le squelette Maven sera disponible.

Commandes prévues :

```bash
mvn clean test
mvn clean package
java -jar target/jeu-aventure.jar
```

Ces commandes sont provisoires et pourront changer selon la configuration finale du fichier `pom.xml`.

## Méthode de travail

Le projet suit les étapes suivantes :

1. définition du périmètre et des règles ;
2. analyse des besoins ;
3. création des diagrammes UML d’analyse ;
4. conception de l’architecture MVC ;
5. création du squelette Java/Maven ;
6. implémentation de la version minimale ;
7. tests et corrections ;
8. mise en cohérence des diagrammes avec le code ;
9. rédaction du rapport et du manuel utilisateur ;
10. préparation de l’archive finale.

## Équipe

Projet réalisé en groupe dans le cadre du module de génie logiciel.

Les noms des membres et la répartition définitive des responsabilités seront ajoutés après validation par l’équipe.

## Licence

Ce dépôt est destiné à un projet universitaire. Aucune licence de réutilisation n’est actuellement définie.
