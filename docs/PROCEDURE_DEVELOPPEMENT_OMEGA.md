# Procédure de développement OMEGA — [NOM_DU_PROJET]

| Champ | Valeur |
|---|---|
| Projet | [NOM_DU_PROJET] |
| Version visée | [VERSION_CIBLE] |
| Responsable | [NOM] |
| Date de création | [AAAA-MM-JJ] |
| Dernière mise à jour | [AAAA-MM-JJ] |
| Statut global | Brouillon / En cours / Validé / En production |
| Environnement cible | [Linux / Arch / Debian / Serveur / Poste] |
| Langage principal | [Python / Bash / Lua / Autre] |
| Dépôt | [URL_OU_CHEMIN] |

## Règles transversales

- [ ] Aucun code n’est écrit avant validation du plan définitif.
- [ ] Chaque décision importante est documentée.
- [ ] Chaque anomalie est journalisée.
- [ ] Chaque correction est testée.
- [ ] Chaque modification de comportement est documentée.
- [ ] Les sauvegardes précèdent toute intervention en production.
- [ ] L’IA analyse et propose ; l’humain décide, valide et met en production.
- [ ] Le code reste aligné avec la documentation définitive.

## Suivi global des phases

| Phase | Acteur | Livrable principal | Statut | Date de validation |
|---:|---|---|---|---|
| 1 | Humain | Besoin et conception | [ ] | [AAAA-MM-JJ] |
| 2 | Humain | Ébauche architecture et plan brouillon | [ ] | [AAAA-MM-JJ] |
| 3 | IA | Analyse, effets de bord, plan définitif | [ ] | [AAAA-MM-JJ] |
| 4 | Humain | Cœur du projet codé | [ ] | [AAAA-MM-JJ] |
| 5 | IA | Audit code, correctifs et tests | [ ] | [AAAA-MM-JJ] |
| 6 | Humain | Tests réels en production | [ ] | [AAAA-MM-JJ] |
| 7 | IA | Plan de correctifs et codage définitif | [ ] | [AAAA-MM-JJ] |
| 8 | Humain | Test définitif | [ ] | [AAAA-MM-JJ] |
| 9 | Humain | Ébauche de documentation | [ ] | [AAAA-MM-JJ] |
| 10 | IA | Documentation définitive | [ ] | [AAAA-MM-JJ] |
| 11 | Humain | Mise en production | [ ] | [AAAA-MM-JJ] |

---

# Phase 1 — Réflexion, besoin, usage et conception

**Acteur : Humain**  
**Objectif :** définir le problème, les utilisateurs, les usages réels, les contraintes et les limites du projet.

## 1. Problème initial

- Problème constaté : [À COMPLÉTER]
- Situation actuelle : [À COMPLÉTER]
- Conséquence du problème : [À COMPLÉTER]
- Objectif du projet : [À COMPLÉTER]

## 2. Utilisateurs cibles

| Utilisateur | Besoin principal | Niveau technique | Usage prévu |
|---|---|---|---|
| [Utilisateur 1] | [À COMPLÉTER] | [Débutant / Technique / Expert] | [À COMPLÉTER] |
| [Utilisateur 2] | [À COMPLÉTER] | [Débutant / Technique / Expert] | [À COMPLÉTER] |

## 3. Scénarios d’usage

### Scénario nominal

- Contexte : [À COMPLÉTER]
- Action de l’utilisateur : [À COMPLÉTER]
- Résultat attendu : [À COMPLÉTER]

### Scénario limite

- Contexte : [À COMPLÉTER]
- Action de l’utilisateur : [À COMPLÉTER]
- Résultat attendu : [À COMPLÉTER]

### Scénario d’erreur

- Contexte : [À COMPLÉTER]
- Action de l’utilisateur : [À COMPLÉTER]
- Résultat attendu : [À COMPLÉTER]

### Scénario interdit ou dangereux

- Contexte : [À COMPLÉTER]
- Comportement attendu : [Refus / Avertissement / Blocage / Journalisation]
- Justification : [À COMPLÉTER]

## 4. Fonctionnalités

### Indispensables

- [ ] [Fonctionnalité 1]
- [ ] [Fonctionnalité 2]
- [ ] [Fonctionnalité 3]

### Utiles mais différables

- [ ] [Fonctionnalité 1]
- [ ] [Fonctionnalité 2]

### Optionnelles

- [ ] [Fonctionnalité 1]

### Exclues

- [ ] [Fonctionnalité exclue]
- Justification : [À COMPLÉTER]

## 5. Contraintes

| Domaine | Contrainte | Priorité |
|---|---|---|
| Système | [Linux / Debian / Version] | [Haute / Moyenne / Basse] |
| Langage | [Python / Bash / Lua] | [Haute / Moyenne / Basse] |
| Dépendances | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Performance | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Sécurité | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Compatibilité | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Maintenance | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Déploiement | [À COMPLÉTER] | [Haute / Moyenne / Basse] |

## 6. Risques identifiés

| Risque | Impact | Probabilité | Mesure de prévention |
|---|---|---|---|
| [Risque 1] | [Faible / Moyen / Élevé] | [Faible / Moyen / Élevé] | [À COMPLÉTER] |
| [Risque 2] | [Faible / Moyen / Élevé] | [Faible / Moyen / Élevé] | [À COMPLÉTER] |

## 7. Décisions prises

| ID | Décision | Justification | Date |
|---:|---|---|---|
| D-001 | [À COMPLÉTER] | [À COMPLÉTER] | [AAAA-MM-JJ] |
| D-002 | [À COMPLÉTER] | [À COMPLÉTER] | [AAAA-MM-JJ] |

## 8. Questions ouvertes

- [ ] [Question 1]
- [ ] [Question 2]

## Validation de la phase 1

- [ ] Le problème est clairement formulé.
- [ ] Les utilisateurs sont identifiés.
- [ ] Les usages principaux sont décrits.
- [ ] Les fonctionnalités indispensables sont listées.
- [ ] Les limites du projet sont explicites.
- [ ] Les contraintes techniques sont connues.
- [ ] Les risques principaux sont identifiés.

**Statut :** [ ] Brouillon / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 2 — Ébauche, organes principaux et plan de développement

**Acteur : Humain**  
**Objectif :** transformer le besoin en architecture logique et en plan de développement actionnable.

## 1. Organes principaux

| Organe | Responsabilité | Ne doit pas faire | Priorité |
|---|---|---|---|
| Interface / CLI | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Cœur métier | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Configuration | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Modèles de données | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Services | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Stockage | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Export | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Journalisation | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Sécurité | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| Tests | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |

## 2. Flux principal

```text
[Entrée utilisateur]
    → [Interface]
    → [Validation]
    → [Cœur métier]
    → [Services / Modules]
    → [Résultat]
    → [Sortie / Stockage / Logs]
```

## 3. Modules prévus

| Module | Rôle | Dépendances | Priorité |
|---|---|---|---|
| [module_1] | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| [module_2] | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |
| [module_3] | [À COMPLÉTER] | [À COMPLÉTER] | [Haute / Moyenne / Basse] |

## 4. Arborescence prévisionnelle

```text
[NOM_DU_PROJET]/
├── src/
│   └── [nom_du_projet]/
│       	├── app/              Bootstrap et conteneur d'injection de dépendances
│			├── core/             Capacités, énumérations et exceptions
│			├── domain/           Logique métier pure
│			├── application/      Orchestration : commands et queries
│			├── infrastructure/   Backends, stockage, exports, logs et sondes système...
│			├── ports/            Contrats Protocol/ABC
│			├── interfaces/       interfaces/tui/ (Textual, par défaut) + interfaces/cli/ (Rich, --legacy-cli)
│			├── plugins/          Extensions intégrées...
│			└── shared/			  Parsing, réseau, formatage et utilitaires transverses...
├── tests/
│   ├── unit/
│   └── integration/
├── docs/
├── scripts/
└── CHANGELOG.md
```

## 5. Dépendances prévues

| Dépendance | Usage | Version minimale | Justification |
|---|---|---|---|
| [Dépendance 1] | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |
| [Dépendance 2] | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |

## 6. Découpage du développement

| Phase | Contenu | Priorité | Estimation |
|---:|---|---|---|
| 1 | Fondations : structure, configuration, erreurs, logs | [Haute / Moyenne] | [Durée] |
| 2 | Modèles et contrats | [Haute / Moyenne] | [Durée] |
| 3 | Cœur métier | [Haute / Moyenne] | [Durée] |
| 4 | Interface / CLI | [Haute / Moyenne] | [Durée] |
| 5 | Stockage / export | [Haute / Moyenne] | [Durée] |
| 6 | Tests | [Haute / Moyenne] | [Durée] |
| 7 | Documentation et packaging | [Haute / Moyenne] | [Durée] |

## Validation de la phase 2

- [ ] Les organes principaux sont identifiés.
- [ ] Chaque module a une responsabilité claire.
- [ ] Les flux principaux sont décrits.
- [ ] L’arborescence prévisionnelle est définie.
- [ ] Les dépendances principales sont identifiées.
- [ ] L’ordre de développement est défini.
- [ ] Aucun développement n’a commencé.

**Statut :** [ ] Brouillon / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 3 — Analyse IA, effets de bord et plan définitif

**Acteur : IA**  
**Objectif :** analyser les documents humains, détecter les risques et produire un plan définitif exploitable.

## 1. Documents analysés

- [ ] `PROJECT_00_BESOIN_ET_CONCEPTION.md`
- [ ] `PROJECT_01_EBAUCHE_ARCHITECTURE.md`
- [ ] `PROJECT_02_PLAN_DEVELOPPEMENT_BROUILLON.md`
- [ ] [Autre document]

## 2. Prompt d’analyse IA

```text
Analyse ce projet sans écrire de code.

1. Détecte les incohérences.
2. Détecte les fonctions manquantes.
3. Détecte les responsabilités mal placées.
4. Identifie les effets de bord possibles.
5. Identifie les cas d’échec.
6. Identifie les risques de sécurité.
7. Identifie les problèmes de compatibilité.
8. Propose une structure de projet plus robuste.
9. Propose un plan de développement définitif.
10. Indique les points qui doivent rester sous décision humaine.
```

## 3. Incohérences détectées

| ID | Description | Impact | Proposition | Décision humaine |
|---:|---|---|---|---|
| A-001 | [À COMPLÉTER] | [Faible / Moyen / Élevé] | [À COMPLÉTER] | [Acceptée / Refusée / Reportée] |
| A-002 | [À COMPLÉTER] | [Faible / Moyen / Élevé] | [À COMPLÉTER] | [Acceptée / Refusée / Reportée] |

## 4. Effets de bord identifiés

| ID | Effet de bord | Déclencheur | Impact | Prévention | Statut |
|---:|---|---|---|---|---|
| EB-001 | [À COMPLÉTER] | [À COMPLÉTER] | [Faible / Moyen / Élevé] | [À COMPLÉTER] | [Ouvert / Traité / Accepté] |
| EB-002 | [À COMPLÉTER] | [À COMPLÉTER] | [Faible / Moyen / Élevé] | [À COMPLÉTER] | [Ouvert / Traité / Accepté] |

## 5. Cas d’échec à prévoir

| Cas | Comportement attendu | Message / log attendu | Test associé |
|---|---|---|---|
| Fichier absent | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |
| Permission refusée | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |
| Réseau indisponible | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |
| Entrée invalide | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |
| Interruption utilisateur | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |
| Données corrompues | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] |

## 6. Risques de sécurité

| Risque | Scénario | Mesure | Priorité |
|---|---|---|---|
| [Risque 1] | [À COMPLÉTER] | [À COMPLÉTER] | [P0 / P1 / P2] |
| [Risque 2] | [À COMPLÉTER] | [À COMPLÉTER] | [P0 / P1 / P2] |

## 7. Plan de développement définitif

| Phase | Objectif | Livrables | Critère de fin | Dépendances |
|---:|---|---|---|---|
| 1 | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] | [Aucune] |
| 2 | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] | [Phase 1] |
| 3 | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] | [Phase 2] |

## Validation de la phase 3

- [ ] Les incohérences sont traitées ou documentées.
- [ ] Les effets de bord sont identifiés.
- [ ] Les cas d’échec sont prévus.
- [ ] Les risques de sécurité sont traités.
- [ ] Le plan définitif est validé par l’humain.
- [ ] Les décisions finales sont enregistrées.

**Statut :** [ ] Brouillon / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 4 — Codage du cœur du projet

**Acteur : Humain**  
**Objectif :** développer le cœur fonctionnel sans ajouter de fonctionnalité hors périmètre.

## 1. Périmètre de codage

- [ ] Structure du projet
- [ ] Environnement virtuel
- [ ] Dépendances
- [ ] Configuration
- [ ] Modèles de données
- [ ] Exceptions
- [ ] Journalisation
- [ ] Services métier
- [ ] Cœur métier
- [ ] Tests unitaires
- [ ] CLI / interface
- [ ] Intégration

## 2. Ordre d’implémentation

| Ordre | Élément | Fichier / module | Statut | Commit |
|---:|---|---|---|---|
| 1 | [Élément] | [chemin] | [ ] | [hash] |
| 2 | [Élément] | [chemin] | [ ] | [hash] |
| 3 | [Élément] | [chemin] | [ ] | [hash] |

## 3. Règles de commit

- Un commit = une intention unique.
- Ne pas mélanger fonctionnalité, correction et refactoring.
- Message recommandé :

```text
[type]: [description courte]

[type] = feat, fix, refactor, test, docs, chore
```

Exemple :

```text
feat: ajout du chargement et de la validation de la configuration
```

## 4. Tests initiaux

| Test | Objectif | Commande | Résultat attendu | Statut |
|---|---|---|---|---|
| [Test 1] | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [ ] |
| [Test 2] | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [ ] |

## Validation de la phase 4

- [ ] Le cœur métier fonctionne.
- [ ] Les entrées principales sont validées.
- [ ] Les erreurs principales sont gérées.
- [ ] Les tests unitaires passent.
- [ ] Le projet démarre en mode basique.
- [ ] Aucune fonctionnalité hors périmètre n’a été ajoutée.

**Statut :** [ ] En cours / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 5 — Analyse du code, rectification et tests IA

**Acteur : IA**  
**Objectif :** détecter les défauts, effets de bord et risques avant les tests réels.

## 1. Prompt d’audit IA

```text
Analyse le code sans le réécrire intégralement.

1. Vérifie la conformité au plan de développement.
2. Détecte les bugs probables.
3. Détecte les effets de bord.
4. Détecte les fuites de ressources.
5. Détecte les erreurs non gérées.
6. Détecte les entrées non validées.
7. Détecte les problèmes de sécurité.
8. Détecte les problèmes de performance.
9. Détecte le code mort.
10. Détecte les responsabilités mal placées.
11. Propose des correctifs ciblés.
12. Propose les tests manquants.
```

## 2. Constats d’audit

| ID | Fichier / fonction | Constat | Gravité | Correctif proposé | Statut |
|---:|---|---|---|---|---|
| C-001 | [chemin] | [À COMPLÉTER] | [Critique / Majeure / Mineure] | [À COMPLÉTER] | [Ouvert / Corrigé / Validé] |
| C-002 | [chemin] | [À COMPLÉTER] | [Critique / Majeure / Mineure] | [À COMPLÉTER] | [Ouvert / Corrigé / Validé] |

## 3. Tests ajoutés

| Test | Objectif | Fichier de test | Statut |
|---|---|---|---|
| [Test 1] | [À COMPLÉTER] | [chemin] | [ ] |
| [Test 2] | [À COMPLÉTER] | [chemin] | [ ] |

## Validation de la phase 5

- [ ] Les bugs critiques sont corrigés.
- [ ] Les effets de bord sont traités ou documentés.
- [ ] Les tests unitaires passent.
- [ ] Les tests d’intégration passent.
- [ ] Le code respecte le plan définitif.
- [ ] Les correctifs ont été appliqués progressivement.

**Statut :** [ ] En cours / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 6 — Étude et test réel en production

**Acteur : Humain**  
**Objectif :** valider le logiciel dans des conditions réelles et consigner toutes les anomalies.

## 1. Environnement de test

| Élément | Valeur |
|---|---|
| Machine | [À COMPLÉTER] |
| Système | [À COMPLÉTER] |
| Version du logiciel | [À COMPLÉTER] |
| Environnement | [Production contrôlée / Staging / Serveur réel] |
| Sauvegarde effectuée | [Oui / Non] |
| Date de sauvegarde | [AAAA-MM-JJ] |
| Méthode de rollback | [À COMPLÉTER] |

## 2. Scénarios testés

| ID | Scénario | Commande | Résultat attendu | Résultat obtenu | Statut |
|---:|---|---|---|---|---|
| T-001 | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [OK / KO / Partiel] |
| T-002 | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [OK / KO / Partiel] |

## 3. Grille d’observation

| Domaine | Élément observé | Résultat | Commentaire |
|---|---|---|---|
| Fonctionnel | Fonction attendue | [OK / KO] | [À COMPLÉTER] |
| Interface | Clarté des commandes | [OK / KO] | [À COMPLÉTER] |
| Performance | Temps d’exécution | [OK / KO] | [À COMPLÉTER] |
| Stabilité | Absence de crash | [OK / KO] | [À COMPLÉTER] |
| Erreurs | Compréhensibilité des messages | [OK / KO] | [À COMPLÉTER] |
| Logs | Qualité et utilité | [OK / KO] | [À COMPLÉTER] |
| Sécurité | Comportement sûr | [OK / KO] | [À COMPLÉTER] |
| Compatibilité | Fonctionnement sur cible réelle | [OK / KO] | [À COMPLÉTER] |
| Esthétique | Lisibilité de la sortie | [OK / KO] | [À COMPLÉTER] |
| Usage réel | Fluidité du parcours | [OK / KO] | [À COMPLÉTER] |

## 4. Journal des anomalies

| ID | Date | Gravité | Description | Logs | Hypothèse | Correctif proposé | Statut |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [AAAA-MM-JJ] | [Critique / Majeure / Mineure / Esthétique] | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] | [Ouvert / Corrigé / Validé] |
| BUG-002 | [AAAA-MM-JJ] | [Critique / Majeure / Mineure / Esthétique] | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] | [À COMPLÉTER] | [Ouvert / Corrigé / Validé] |

## Validation de la phase 6

- [ ] Tous les scénarios critiques ont été testés.
- [ ] Les bugs sont consignés.
- [ ] Les problèmes d’usage sont consignés.
- [ ] Les problèmes esthétiques sont consignés.
- [ ] Aucun bug critique bloquant n’est ignoré.

**Statut :** [ ] En cours / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 7 — Plan d’amélioration, correctifs et codage définitif

**Acteur : IA**  
**Objectif :** transformer les anomalies en correctifs priorisés, puis appliquer les modifications nécessaires.

## 1. Prompt d’analyse des anomalies

```text
Voici le journal des tests en production.

1. Classe les anomalies par gravité.
2. Regroupe les anomalies liées.
3. Identifie les causes probables.
4. Propose un correctif minimal pour chaque anomalie.
5. Indique les risques de régression.
6. Propose les tests à ajouter.
7. Propose les améliorations d’usage.
8. Propose les améliorations esthétiques.
9. Ne modifie que ce qui est nécessaire.
10. Conserve les comportements validés.
```

## 2. Priorisation des anomalies

| Priorité | Type | Anomalies concernées | Traitement |
|---|---|---|---|
| P0 | Crash, perte de données, faille | [BUG-XXX] | Correction immédiate |
| P1 | Fonctionnalité incorrecte | [BUG-XXX] | Correction avant validation finale |
| P2 | Mauvaise expérience d’usage | [BUG-XXX] | Correction si raisonnable |
| P3 | Esthétique, message, format | [BUG-XXX] | Correction ou report |
| P4 | Amélioration future | [BUG-XXX] | Backlog |

## 3. Correctifs appliqués

| ID | Anomalie | Correctif | Fichiers modifiés | Tests ajoutés | Risque de régression | Statut |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [À COMPLÉTER] | [chemin] | [chemin] | [Faible / Moyen / Élevé] | [Appliqué / Validé] |
| FIX-002 | [BUG-XXX] | [À COMPLÉTER] | [chemin] | [chemin] | [Faible / Moyen / Élevé] | [Appliqué / Validé] |

## Validation de la phase 7

- [ ] Chaque anomalie a un statut clair.
- [ ] Les correctifs sont appliqués par priorité.
- [ ] Les tests de non-régression passent.
- [ ] Les comportements validés sont préservés.
- [ ] Chaque correction est documentée.

**Statut :** [ ] En cours / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 8 — Test définitif

**Acteur : Humain**  
**Objectif :** valider la version candidate avant documentation finale et mise en production stable.

## 1. Tests de validation

| Test | Objectif | Commande | Résultat attendu | Résultat obtenu | Statut |
|---|---|---|---|---|---|
| Scénario nominal | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [ ] |
| Scénario d’erreur | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [ ] |
| Options CLI | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [ ] |
| Configuration | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [ ] |
| Permissions | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [ ] |
| Interruption | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [ ] |
| Non-régression | [À COMPLÉTER] | [commande] | [À COMPLÉTER] | [À COMPLÉTER] | [ ] |

## 2. Checklist finale

- [ ] Le projet démarre correctement.
- [ ] Les commandes principales fonctionnent.
- [ ] Les erreurs sont compréhensibles.
- [ ] Les logs sont exploitables.
- [ ] Aucun bug critique n’est présent.
- [ ] Aucune régression n’est détectée.
- [ ] Les performances sont acceptables.
- [ ] La sécurité est conforme aux exigences.
- [ ] La version est identifiable.
- [ ] Le rollback est possible.

## Validation de la phase 8

**Décision :** [ ] Version candidate / [ ] Retour en correction  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 9 — Ébauche de la documentation

**Acteur : Humain**  
**Objectif :** documenter le logiciel tel qu’il fonctionne réellement.

## 1. Documents à produire

| Document | Objectif | Statut |
|---|---|---|
| `README.md` | Présentation et démarrage rapide | [ ] |
| `GUIDE_UTILISATEUR.md` | Usage détaillé et vulgarisé | [ ] |
| `GUIDE_TECHNIQUE.md` | Architecture et fonctionnement interne | [ ] |
| `GUIDE_DEVELOPPEMENT.md` | Environnement, tests, conventions | [ ] |
| `INSTALLATION.md` | Prérequis et installation | [ ] |
| `SECURITE.md` | Risques, permissions, bonnes pratiques | [ ] |
| `DEPANNAGE.md` | Erreurs fréquentes et solutions | [ ] |
| `CHANGELOG.md` | Historique des versions | [ ] |

## 2. Contenu à vérifier

- [ ] Chaque commande est documentée.
- [ ] Chaque option est documentée.
- [ ] Chaque fichier de configuration est documenté.
- [ ] Chaque dépendance est documentée.
- [ ] Chaque erreur fréquente est expliquée.
- [ ] Les limites sont explicites.
- [ ] Les exemples sont testables.

## Validation de la phase 9

**Statut :** [ ] Brouillon / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 10 — Mise en forme et documentation définitive

**Acteur : IA**  
**Objectif :** compléter, structurer et harmoniser la documentation sans inventer de comportement non présent dans le code.

## 1. Prompt de complétion documentaire

```text
Voici les ébauches de documentation.

1. Vérifie la cohérence avec le code réel.
2. Détecte les fonctions non documentées.
3. Détecte les options CLI non documentées.
4. Détecte les messages d’erreur non expliqués.
5. Détecte les dépendances manquantes.
6. Détecte les étapes d’installation manquantes.
7. Détecte les incohérences entre documents.
8. Améliore la structure et la lisibilité.
9. Complète les sections manquantes.
10. Ne modifie pas le comportement décrit sans preuve dans le code.
```

## 2. Contrôles documentaires

| Contrôle | Statut | Commentaire |
|---|---|---|
| Cohérence avec le code | [ ] | [À COMPLÉTER] |
| Commandes documentées | [ ] | [À COMPLÉTER] |
| Options documentées | [ ] | [À COMPLÉTER] |
| Codes de sortie documentés | [ ] | [À COMPLÉTER] |
| Configuration documentée | [ ] | [À COMPLÉTER] |
| Dépendances documentées | [ ] | [À COMPLÉTER] |
| Erreurs fréquentes documentées | [ ] | [À COMPLÉTER] |
| Exemples testables | [ ] | [À COMPLÉTER] |
| Structure harmonisée | [ ] | [À COMPLÉTER] |

## Validation de la phase 10

**Statut :** [ ] Brouillon / [ ] Validé  
**Validé par :** [NOM]  
**Date :** [AAAA-MM-JJ]

---

# Phase 11 — Mise en production définitive

**Acteur : Humain**  
**Objectif :** déployer la version validée, documentée et testée.

## 1. Préparation

- [ ] Version validée en phase 8.
- [ ] Documentation définitive validée en phase 10.
- [ ] Sauvegarde de l’environnement existant effectuée.
- [ ] Procédure de rollback disponible.
- [ ] Tag de version créé.

Commandes :

```bash
git tag -a v[VERSION] -m "Version stable [VERSION]"
git push origin v[VERSION]
```

## 2. Packaging

```bash
python -m build
```

Vérification :

```bash
sha256sum dist/*
```

## 3. Déploiement

| Étape | Commande / action | Statut | Commentaire |
|---:|---|---|---|
| 1 | Sauvegarde | [ ] | [À COMPLÉTER] |
| 2 | Déploiement de la version taguée | [ ] | [À COMPLÉTER] |
| 3 | Vérification du service | [ ] | [À COMPLÉTER] |
| 4 | Contrôle des logs | [ ] | [À COMPLÉTER] |
| 5 | Test de la commande principale | [ ] | [À COMPLÉTER] |
| 6 | Documentation de la version déployée | [ ] | [À COMPLÉTER] |

## 4. Vérifications post-déploiement

```bash
systemctl status [NOM_DU_SERVICE]
journalctl -u [NOM_DU_SERVICE] -n 100 --no-pager
```

- [ ] Le service est actif.
- [ ] Aucune erreur critique dans les logs.
- [ ] La commande principale répond.
- [ ] La version déployée correspond au tag validé.
- [ ] Le rollback est documenté et testable.

## Validation finale

| Champ | Valeur |
|---|---|
| Version déployée | [VERSION] |
| Date de mise en production | [AAAA-MM-JJ] |
| Environnement | [À COMPLÉTER] |
| Responsable | [NOM] |
| Rollback testé | [Oui / Non] |
| Statut final | [En production / Échec / Retour arrière] |

---

# Historique des modifications du document

| Date | Version | Auteur | Modification |
|---|---|---|---|
| [AAAA-MM-JJ] | 0.1 | [NOM] | Création du template |
| [AAAA-MM-JJ] | [VERSION] | [NOM] | [À COMPLÉTER] |
