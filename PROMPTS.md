# srs-toolkit

Kit de 3 prompts pour te construire un outil de révision espacée (SRS) à
partir du sommaire de n'importe quelle formation en ligne à laquelle tu es
inscrit·e, avec ton propre accès personnel.

---

## 1. Extraire le sommaire de ta formation (Claude in Chrome)

À exécuter sur **ton** compte, **ton** navigateur, **ta** session connectée
à ta plateforme de formation.

```
Je suis connecté sur Chrome à mon compte sur ma plateforme de formation en
ligne. Je veux extraire, pour mon usage strictement personnel, la structure
de mon programme.

1. Va sur l'espace membre de ma formation (précise l'URL de la page d'accueil
   de mon programme si tu la connais, sinon demande-la moi).
2. Pour chaque chapitre et chaque leçon qu'il contient, relève :
   - le nom du chapitre
   - le titre exact de la leçon (copie-le tel quel, ne reformule pas)
   - son type si identifiable : théorie/cours, exercice/mise en pratique,
     quiz, projet fil rouge, ressource, ou simple note/transition
   - l'URL complète de l'élément
   - si elle est déjà marquée comme terminée par moi
3. Restitue uniquement un JSON dans ce format exact, rien d'autre en sortie :

[
  {"c": "Nom du chapitre", "items": [
    {"t": "Titre exact", "ty": "L|E|Q|F|R|N", "d": 0, "u": "URL complète"}
  ]}
]

où ty = L (théorie), E (exercice), Q (quiz), F (fil rouge), R (ressource),
N (note sans contenu pédagogique) ; d = 1 si déjà terminée, sinon 0.

Rappel : contenu à usage strictement personnel (accès payant légitime),
ne jamais le partager avec un tiers ni le publier.
```

---

## 2. Construire l'artefact Claude (avec synchro cross-device)

```
Voici le JSON du sommaire de ma formation (format ci-dessous), obtenu par
mon propre accès personnel — garde-le uniquement dans le fichier que tu me
donnes, ne le republie nulle part d'autre :

[coller le JSON ici]

Construis-moi une appli web de révision espacée (SRS), publiée comme
artefact Claude, avec :
- Deux modes au choix : Leitner (5 boîtes, intervalles 1/2/4/7/14 jours) et
  SM-2 façon Anki (ease factor, boutons Again/Hard/Good/Easy).
- Une file de révision du jour tirée des cartes dues, avec notation du rappel.
- Titre de leçon cliquable → ouvre l'URL d'origine dans un nouvel onglet.
- Liste par chapitre avec barre de progression et bouton "Apprise" pour
  activer une carte pas encore commencée.
- Synchronisation automatique de ma progression entre mes appareils : utilise
  la capability `db` de l'artefact (capabilities: {db:{}}), avec un document
  par carte dans une collection "cards", mis à jour à chaque notation et
  suivi en temps réel via onSnapshot. Prévois un repli local (localStorage)
  si le stockage partagé est indisponible, pour que l'app ne soit jamais vide.
- Export/import JSON en secours manuel, en plus de la synchro automatique.
- Thème sombre/clair automatique, sobre et lisible.
```

⚠️ La synchro cross-device via `db` ne fonctionne qu'à l'intérieur de **ton
propre compte/organisation Claude** — un artefact déclarant `db` ne peut pas
être partagé publiquement avec des tiers en gardant cette fonctionnalité
active pour eux.

---

## 3. Alternative — Airtable + Softr

```
J'ai un JSON décrivant le sommaire de ma formation (même format que
ci-dessus). Aide-moi à construire un système de révision espacée avec
Airtable + Softr :

1. Dans Airtable, crée une base avec une table "Lecons" : Chapitre (texte),
   Titre (texte), Type (sélection unique : Théorie/Exercice/Quiz/Fil
   rouge/Ressource/Note), URL (lien), Statut (sélection : À apprendre/
   Apprise), Boîte Leitner (nombre, 1 à 5), Prochaine révision (date).
   Explique-moi comment importer mon JSON dans cette table.
2. Donne-moi, étape par étape, comment construire dans Softr :
   - une vue "Aujourd'hui" filtrée sur Prochaine révision <= aujourd'hui
   - un bouton "Su / Pas su" qui met à jour Boîte Leitner et Prochaine
     révision selon la logique 1/2/4/7/14 jours
   - une vue par chapitre avec barre de progression
3. Précise bien les endroits où je dois cliquer dans Softr, puisque tu n'as
   pas d'accès direct à l'outil.
```

---

## Manuel d'utilisation de l'appli générée

- **Deux modes** en haut à droite : *Leitner* (5 boîtes, intervalle fixe par
  boîte) ou *SM-2* (intervalle qui s'ajuste à ta difficulté ressentie via
  4 boutons : Again / Hard / Good / Easy). Le choix de mode reste propre à
  chaque appareil, il n'est pas synchronisé.
- **Session du jour** : la carte affichée est celle qui est due. Note ton
  rappel ; la carte suivante due apparaît automatiquement.
- **À apprendre** : liste par chapitre. Clique sur "✓ Apprise" pour activer
  une carte pas encore intégrée à la révision.
- **Export / Import** : bouton en bas de page. Utile en secours si jamais la
  synchro automatique est indisponible, ou pour garder une sauvegarde locale.
- **Réinitialiser** : remet toute la progression à zéro (irréversible),
  demande confirmation.

---

## ⚠️ Avant de diffuser le contenu généré

Le JSON produit à l'étape 1 et l'artefact/l'appli remplie à l'étape 2 ou 3
contiennent le sommaire réel de *ta* formation — titres, structure, liens.
Ce contenu appartient à l'organisme qui édite la formation, pas à toi : la
plupart des CGU de plateformes de formation en ligne interdisent la
reproduction ou la diffusion de leur contenu pédagogique à des tiers, même à
des camarades de promo déjà inscrits. Par exemple, le simple sommaire des
leçons (titres et structure, sans même le contenu des vidéos) suffit déjà à
tomber sous ce type de clause.

Avant de partager quoi que ce soit de rempli avec quelqu'un d'autre :
- Relis les CGU/CGV de ta propre formation (souvent une clause "propriété
  intellectuelle" et une clause "comportements interdits").
- Si tu veux partager l'outil avec d'autres, donne-leur seulement les 3
  prompts ci-dessus (ils ne contiennent aucun contenu protégé) pour qu'ils
  se construisent leur propre version avec leur propre accès — plutôt que de
  leur transmettre ton JSON ou ton artefact rempli.
- Pour diffuser une version remplie telle quelle, obtiens une autorisation
  écrite de l'organisme de formation au préalable.
