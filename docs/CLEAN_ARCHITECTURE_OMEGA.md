# Architecture du projet — Clean Architecture

Ce document explique comment le projet est organisé, pourquoi cette organisation a été choisie, et ce que contient chaque dossier. Il s’adresse aussi bien à un visiteur qui souhaite comprendre le fonctionnement général qu’à un développeur qui veut contribuer ou maintenir l’application.

L’application suit une **Clean Architecture** : le cœur du logiciel est isolé des détails techniques, des interfaces utilisateur et des dépendances externes. Cette séparation rend le projet plus lisible, plus testable, plus maintenable et plus facile à faire évoluer.

---

## 1. Principe général

L’application est découpée en couches ayant chacune un rôle précis.

L’idée centrale est simple :

```text
L’interface demande une action.
L’application orchestre cette action.
Le domaine applique les règles métier.
Les ports définissent ce dont l’application a besoin.
L’infrastructure fournit les implémentations concrètes.
```

Ainsi, la logique importante du projet ne dépend pas directement :

- du terminal ;
- de l’interface graphique ;
- d’une base de données ;
- du réseau ;
- du système de fichiers ;
- d’une bibliothèque externe ;
- d’un outil système.

Cette indépendance permet de remplacer une partie du logiciel sans réécrire tout le reste.

---

## 2. Vue d’ensemble

```text
[NOM_DU_PROJET]/
└── src/
    └── [nom_du_projet]/
        ├── app/              Bootstrap, cycle de vie et injection de dépendances
        ├── core/             Capacités, énumérations et exceptions transverses
        ├── domain/           Logique métier pure
        ├── application/      Cas d’usage : commands et queries
        ├── infrastructure/   Backends, stockage, exports, logs, sondes système…
        ├── ports/            Contrats Protocol / ABC
        ├── interfaces/       CLI et TUI
        ├── plugins/          Extensions intégrées
        └── shared/           Parsing, réseau, formatage et utilitaires transverses
```

---

## 3. Schéma des dépendances

Les dépendances doivent toujours aller dans le même sens :

```text
interfaces
    ↓
application
    ↓
domain
    ↑
ports
    ↑
infrastructure
```

En pratique :

- `interfaces/` peut appeler `application/`.
- `application/` peut appeler `domain/` et utiliser les contrats de `ports/`.
- `domain/` ne dépend ni de `application/`, ni de `infrastructure/`, ni de `interfaces/`.
- `infrastructure/` implémente les contrats définis dans `ports/`.
- `app/` assemble les couches et fournit les dépendances nécessaires.

Règle essentielle :

> Le domaine ne connaît jamais l’infrastructure.  
> L’infrastructure connaît les ports, mais le domaine ne connaît pas l’infrastructure.

---

## 4. Dossier `app/`

### Rôle

Le dossier `app/` est le **point d’assemblage** de l’application.

Il contient :

- le démarrage du programme ;
- le cycle de vie ;
- le conteneur d’injection de dépendances ;
- la construction des objets nécessaires au fonctionnement ;
- le choix des implémentations concrètes ;
- l’initialisation de la configuration ;
- la mise en relation des couches.

### Exemple de responsabilités

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Fichier | Rôle |
|---|---|
| `bootstrap.py` | Démarre l’application et choisit l’interface à lancer |
| `container.py` | Crée et relie les dépendances |
| `lifecycle.py` | Gère le démarrage, l’arrêt et le nettoyage |

### Règle

`app/` ne contient pas de logique métier.

Il ne décide pas :

- ce qu’est une règle métier ;
- comment une donnée doit être calculée ;
- comment une requête doit être analysée ;
- comment un fichier doit être exporté.

Il assemble uniquement les composants existants.

---

## 5. Dossier `core/`

### Rôle

Le dossier `core/` contient le **vocabulaire transverse** du projet.

Il regroupe les éléments partagés par plusieurs couches, mais qui ne constituent pas une règle métier en soi.

Il peut contenir :

- des capacités ;
- des énumérations ;
- des constantes ;
- des exceptions transverses ;
- des types communs ;
- des informations sur la plateforme ;
- des définitions de niveaux ou d’états.

### Exemple

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Fichier | Rôle |
|---|---|
| `capabilities.py` | Décrit les capacités disponibles ou activables |
| `constants.py` | Contient les constantes du projet |
| `enums.py` | Définit les états, types ou niveaux possibles |
| `exceptions.py` | Définit les erreurs transverses |

### Règle

`core/` doit rester léger et stable.

Il ne doit pas contenir :

- de logique métier complexe ;
- d’appel réseau ;
- d’accès disque ;
- d’interface utilisateur ;
- de dépendance directe vers une bibliothèque externe.

---

## 6. Dossier `domain/`

### Rôle

Le dossier `domain/` est le **cœur du projet**.

Il contient la logique métier pure : les règles, les concepts et les calculs qui définissent réellement ce que fait l’application.

Il peut contenir :Document 1 non enregistré

- des entités ;
- des value objects ;
- des politiques ;
- des règles métier ;
- des services du domaine ;
- des calculs ;
- des validations métier ;
- des modèles de données métier.

### Exemple

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Élément | Rôle |
|---|---|
| Entité | Objet métier ayant une identité |
| Value object | Valeur immuable et validée |
| Politique | Règle métier réutilisable |
| Service du domaine | Logique métier qui ne appartient pas à une seule entité |

### Règles strictes

Le dossier `domain/` :

- ne fait aucun accès disque ;
- ne fait aucun appel réseau ;
- n’exécute pas de commande système ;
- n’accède pas à une base de données ;
- n’importe pas l’interface utilisateur ;
- n’importe pas l’infrastructure ;
- ne dépend pas d’une bibliothèque technique externe lorsque cela peut être évité.

Le domaine doit pouvoir être testé sans serveur, sans fichier, sans réseau et sans interface.

---

## 7. Dossier `application/`

### Rôle

Le dossier `application/` orchestre les cas d’usage.

Il répond à la question :

> « Que se passe-t-il lorsque l’utilisateur demande cette action ? »

Il contient :

- des commands ;
- des queries ;
- des cas d’usage ;
- des orchestrateurs ;
- des gestionnaires d’actions ;
- la coordination entre le domaine et les ports.

### Distinction commands / queries

| Type | Objectif | Modification des données |
|---|---|---|
| Command | Exécuter une action | Oui |
| Query | Lire ou calculer une information | Non |
Document 1 non enregistré
Exemples :

| Command | Query |
|---|---|
| Appliquer une configuration | Lire la configuration actuelle |
| Lancer une analyse | Obtenir le résultat d’une analyse |
| Exporter un rapport | Lister les éléments disponibles |
| Purger des données | Consulter un historique |

### Exemple

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Règle

`application/` ne contient pas :

- d’affichage terminal ;
- d’interface Textual ;
- de commande Rich ;
- d’accès direct à une base de données ;
- d’appel direct à un outil externe.

Il coordonne, mais n’implémente pas les détails techniques.

---

## 8. Dossier `ports/`

### Rôle

Le dossier `ports/` définit les **contrats** attendus par l’application.

Un port décrit **ce dont l’application a besoin**, sans imposer la manière dont cela est réalisé.

Il contient généralement :

- des `Protocol` ;Document 1 non enregistré
- des classes abstraites `ABC` ;
- des interfaces de dépôt ;
- des interfaces d’export ;
- des interfaces de sonde ;
- des interfaces de service externe ;
- des interfaces de stockage.

### Exemple

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Port | Rôle |
|---|---|
| `Repository` | Lire ou enregistrer des données |
| `Exporter` | Produire une sortie dans un format donné |
| `Probe` | Collecter une information système ou réseau |
| `Storage` | Gérer un support de persistance |

### Exemple conceptuel

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Ce contrat dit :

> « L’application a besoin d’un objet capable d’exporter un rapport. »

Il ne dit pas :

- si l’export se fera en Markdown ;
- si l’export se fera en JSON ;
- si le fichier sera écritDocument 1 non enregistré localement ;
- si l’export sera envoyé sur le réseau.

Ces choix appartiennent à `infrastructure/`.

### Règle

Les ports sont des contrats, pas des implémentations.

Ils ne doivent pas contenir :

- de logique métier complexe ;
- d’accès disque ;
- d’appel réseau ;
- d’implémentation concrète ;
- de dépendance directe à une bibliothèque externe.

---

## 9. Dossier `infrastructure/`

### Rôle

Le dossier `infrastructure/` contient les **implémentations concrètes** des ports.

C’est la couche qui dialogue avec le monde extérieur.

Elle peut contenir :

- l’accès aux fichiers ;
- l’accès à une base de données ;
- les exports Markdown, JSON, CSV ou autres ;
- la journalisation ;
- les appels réseau ;
- les sondes système ;
- l’exécution contrôlée d’outils externes ;
- les adaptateurs vers des bibliothèques tierces ;
- les implémentations de dépôts ;
- les implémentations de stockage.

### Exemple

```text
infrastructure/
├── storage/
│   ├── sqlite_repository.py
│   └── json_file_repository.py
├── export/
│   ├── markdown_exporter.py
│   └── json_exporter.py
├── system/
│   ├── process_probe.py
│   └── filesystem_probe.py
└── logging/
    └── structured_logger.py
```

| Élément | Rôle |
|---|---|
| `sqlite_repository.py` | Implémente un dépôt avec SQLite |
| `json_file_repository.py` | Implémente un dépôt avec des fichiers JSON |
| `markdown_exporter.py` | Exporte un rapport en Markdown |
| `json_exporter.py` | Exporte un rapport en JSON |
| `process_probe.py` | Collecte des informations sur les processus |
| `filesystem_probe.py` | Collecte des informations sur le système de fichiers |
| `structured_logger.py` | Produit des logs structurés |

### Règle

`infrastructure/` est la seule couche autorisée à appeler directement :

- le système de fichiers ;
- le réseau ;
- SQLite ;
- des bibliothèques externes ;
- des outils système ;
- des sous-processus, lorsque cela est nécessaire et contrôlé.

Cette centralisation facilite :

- les tests ;
- l’audit de sécurité ;
- le remplacement d’un backend ;
- la limitation des effets de bord.

---

## 10. Dossier `interfaces/`

### Rôle

Le dossier `interfaces/` contient les points d’entrée visibles par l’utilisateur.

Il sépare clairement :

- la CLI ;
- la TUI ;
- les éventuelles futures interfaces web ou API.

### Structure

```text
interfaces/
├── cli/
│   ├── main.py
│   ├── commands/
│   └── rendering/
└── tui/
    ├── app.py
    ├── screens/
    └── widgets/
```

| Interface | Technologie | Rôle |
|---|---|---|
| `cli/` | Rich | Interface en ligne de commande |
| `tui/` | Textual | Interface terminal interactive |

### CLI

La CLI est l’interface en ligne de commande.

Elle permet :

- de lancer l’application ;
- d’exécuter une action précise ;
- d’afficher un résultat ;
- d’automatiser une tâche ;
- d’intégrer l’outil dans un script ;
- d’utiliser l’application à distance via SSH.

### TUI

La TUI est l’interface interactive dans le terminal.

Elle permet :

- de naviguer dans les fonctionnalités ;
- de visualiser des informations ;
- d’exécuter des actions ;
- de consulter des résultats ;
- d’utiliser l’application sans mémoriser toutes les commandes.

### Règle

Les interfaces ne contiennent pas la logique métier.

Elles :

- reçoivent une intention utilisateur ;
- appellent un cas d’usage dans `application/` ;
- affichent le résultat ;
- traduisent les erreurs en messages compréhensibles.

Elles ne doivent pas :

- appeler directement l’infrastructure ;
- exécuter des sous-processus ;
- accéder directement aux fichiers ;
- contenir des règles métier ;
- dupliquer la logique de `application/`.

---

## 11. Dossier `plugins/`

### Rôle

Le dossier `plugins/` est réservé aux **extensions intégrées**.

Il permet d’ajouter des fonctionnalités sans surcharger le cœur du projet.

Un plugin peut par exemple :

- ajouter un type d’export ;
- ajouter une sonde ;
- ajouter une commande ;
- ajouter un écran dans la TUI ;
- ajouter un intégrateur externe ;
- ajouter une capacité optionnelle.

### Principe

Un plugin doit respecter les mêmes règles que le reste du projet :

- il ne contourne pas les ports ;
- il ne modifie pas directement le domaine ;
- il expose ses fonctionnalités via des contrats clairs ;
- il reste désactivable sans casser l’application.

### Structure possible

```text
plugins/
└── [nom_du_plugin]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Règle

Un plugin est une extension, pas une porte dérobée.

Il doit suivre l’architecture générale et ne pas créer de dépendance circulaire avec le cœur du projet.

---

## 12. Dossier `shared/`

### Rôle

Le dossier `shared/` contient les utilitaires transverses qui ne sont ni du domaine, ni de l’application, ni de l’infrastructure.

Il regroupe des fonctions génériques réutilisables.

Il peut contenir :

- du parsing ;
- des utilitaires réseau ;
- du formatage ;
- de la manipulation de texte ;
- des helpers de dates ;
- des helpers de chemins ;
- des utilitaires de validation générique ;
- des helpers de sérialisation.

### Exemple

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Dossier | Rôle |
|---|---|
| `parsing/` | Analyse de texte, JSON, YAML ou autres formats |
| `network/` | Utilitaires réseau génériques |
| `formatting/` | Mise en forme de valeurs, dates, tailles ou tableaux |
| `utils/` | Fonctions utilitaires transverses |

### Règle

`shared/` ne doit pas devenir un dossier fourre-tout.

Un utilitaire n’est placé dans `shared/` que s’il est :

- réutilisable ;
- générique ;
- indépendant d’un cas d’usage précis ;
- utile à plusieurs couches.

---

## 13. Résumé des responsabilités

| Dossier | Rôle principal | Peut dépendre de | Ne doit pas dépendre de |
|---|---|---|---|
| `app/` | Assembler et démarrer l’application | Toutes les couches | — |
| `core/` | Vocabulaire, constantes, énumérations et exceptions | `shared/` si nécessaire | `infrastructure/`, `interfaces/` |
| `domain/` | Logique métier pure | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Orchestrer les cas d’usage | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Définir les contrats | `domain/` si nécessaire | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Implémenter les ports et dialoguer avec l’extérieur | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Interagir avec l’utilisateur | `application/`, `core/` | `infrastructure/` directement |
| `plugins/` | Ajouter des extensions | Selon le type d’extension | Contourner l’architecture |
| `shared/` | Utilitaires transverses | Aucune couche métier | Logique métier spécifique |

---

## 14. Exemple de parcours d’une action

Prenons l’exemple d’un utilisateur qui demande l’export d’un rapport en Markdown.

```text
1. L’utilisateur lance une commande CLI.

2. interfaces/cli/
   Reçoit la commande et les options.

3. interfaces/cli/
   Appelle le cas d’usage correspondant dans application/.

4. application/
   Vérifie l’intention et prépare l’action.

5. application/
   Utilise le domaine pour construire ou valider le rapport.

6. application/
   Demande un export via le port ReportExporter.

7. infrastructure/
   Fournit l’implémentation MarkdownExporter.

8. infrastructure/
   Écrit le fichier Markdown sur le disque.

9. interfaces/cli/
   Affiche le résultat à l’utilisateur.
```

Schéma simplifié :

```text
CLI
 ↓
Application
 ↓
Domaine
 ↓
Port Exporter
 ↓
Infrastructure Markdown
 ↓
Fichier Markdown
```

---

## 15. Pourquoi cette architecture ?

### Lisibilité

Chaque dossier a un rôle unique. Il est donc plus facile de trouver où ajouter ou corriger une fonctionnalité.

### Testabilité

Le domaine peut être testé sans interface, sans base de données et sans accès réseau.

### Maintenance

Une modification de l’interface, du stockage ou d’un outil externe ne doit pas obliger à réécrire la logique métier.

### Sécurité

Les accès sensibles — fichiers, réseau, sous-processus, base de données — sont concentrés dans `infrastructure/`. Cela facilite leur audit et leur contrôle.

### Évolutivité

On peut ajouter :

- une nouvelle interface ;
- un nouveau format d’export ;
- un nouveau backend de stockage ;
- un nouveau plugin ;
- une nouvelle sonde système ;

sans modifier le cœur métier.

### Portabilité

L’application peut évoluer vers d’autres environnements, d’autres systèmes ou d’autres modes d’interaction sans être liée à une technologie précise.

---

## 16. Règles à retenir

- Le domaine est pur.
- L’application orchestre.
- Les ports déclarent les besoins.
- L’infrastructure implémente.
- Les interfaces affichent et collectent.
- `app/` assemble.
- `core/` et `shared/` fournissent le vocabulaire et les utilitaires transverses.
- Les plugins étendent sans contourner l’architecture.

En une phrase :

> **L’application sépare ce qu’elle fait, comment elle le fait, et comment l’utilisateur l’utilise.**
