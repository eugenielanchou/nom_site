# Nature of Mind Retreat Site

## Objectif du projet

Ce projet est une **notice d'information en HTML** destinée aux participants de l'étude
scientifique *Nature of Mind* (recherche sur la méditation et la conscience de soi, coordonnée
par Antoine Lutz — CRNL / INSERM — avec l'EPFL, l'University of Virginia et l'University of
Wisconsin–Madison).

Il ne s'agit **pas** d'un site vitrine ou marketing : c'est un document pratique à visée
informative, envoyé/consulté par les participants pour comprendre le déroulement de l'étude et
préparer leur venue.

L'étude comporte deux phases :
- **Phase 1** — en ligne, questionnaires à distance, avant la retraite.
- **Phase 2** — la retraite en présentiel d'une semaine (le cœur du document). C'est la partie
  qui doit être la plus claire et la plus complète : lieu, dates, transport, horaires
  d'arrivée/départ, contact.

## Ce que la notice doit couvrir en priorité (Phase 2 — la retraite)

- Lieu exact et adresse du lieu de retraite
- Gare la plus proche et moyen de transport (navette, etc.)
- Dates des deux semaines de retraite (deux groupes distincts)
- Fenêtres d'arrivée et de départ par semaine, avec la logique de changeover entre groupes
- Recommandations pratiques (réserver les billets tôt, contact en cas de contrainte de voyage)
- Coordonnées de contact pour toute question

## Structure du repo

- [index.html](index.html) — **fichier unique**, bilingue FR/EN. Tout le contenu texte existe en
  double dans le HTML (paires d'éléments `.only-fr` / `.only-en`), affiché/masqué en CSS selon
  l'attribut `data-lang` sur `<body>`, avec un bouton FR/EN dans la barre de nav (préférence
  mémorisée en `localStorage`). Langue par défaut : français.
- [assets/README.md](assets/README.md) — liste des images attendues (logos institutionnels,
  photos du lieu) et leurs noms de fichiers exacts. Les `<img>` ont un fallback `onerror` qui
  affiche un encart "Photo à venir / Photo coming soon" tant que le fichier n'est pas déposé.

Pas de framework, pas de build, pas de CSS externe : une seule page HTML autonome (styles et
script inline), à ouvrir directement dans un navigateur.

Un dossier `retreat_site/` (contenant uniquement d'anciens `assets/README.md` et `assets/style.css`,
pas de HTML) traîne à la racine — probablement un résidu d'un essai précédent, à vérifier avec
l'utilisateur avant suppression.

## Ton et contraintes de contenu

- **Clarté et praticité avant tout** : un participant doit pouvoir trouver en quelques secondes
  où aller, quand arriver, et qui contacter en cas de problème.
- Ton chaleureux mais factuel, cohérent avec un document destiné à des participants de recherche
  (pas de jargon scientifique inutile).
- **Un seul fichier HTML à maintenir** : ne pas recréer de variante/brouillon séparé
  (`index_bis.html`, `fr/index.html`, etc.) — toute nouvelle langue ou variante doit rester dans
  `index.html` via le mécanisme `.only-fr` / `.only-en`.
- Toute info logistique (dates, adresses, horaires, tarifs) doit être ajoutée/modifiée **dans les
  deux langues à la fois** pour éviter que FR et EN divergent.
- La section "venue" (Phase 2 : comment s'y rendre, le lieu, hébergement/tarifs, repas, infos
  pratiques) est la partie la plus dense du document — voir `index.html#travel`, `#venue`,
  `#costs`, `#meals`, `#practical`. Le contenu source détaillé (trajets avion/train, tarifs,
  éco-lieu, repas) vient du livret PDF fourni par l'utilisateur ("Retraite Méditation.pdf") ; s'y
  référer en priorité pour vérifier l'exactitude avant de modifier ces sections.
