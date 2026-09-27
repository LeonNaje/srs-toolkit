# Ton appli de révision perso — le guide sans prise de tête

Tu n'as jamais codé, jamais utilisé Claude, jamais rien "construit" ? Aucun
souci, ce guide est fait pour toi. 10 minutes, deux copier-coller, et t'as
ton appli de révision.

## Ce que tu vas obtenir

Une appli qui te montre chaque jour les leçons à réviser, te demande "tu t'en
souviens ?", et espace automatiquement les révisions dans le temps (les
leçons difficiles reviennent plus souvent, les faciles moins). C'est la
méthode utilisée par des applis comme Anki, en version faite pour *ta*
formation.

**Et oui, ça marche sur tous tes appareils, sans rien faire de plus.** Tu
révises sur ton téléphone dans le métro, tu retrouves exactement la même
progression le soir sur ton ordi. Pas de clé USB, pas de fichier à
transférer, pas de manip bizarre — ça se synchronise tout seul, en arrière
plan, parce que l'appli est liée à ton compte Claude (pas à un appareil en
particulier). "Cross-device", ça veut juste dire ça : plusieurs appareils,
une seule progression.

## Ce qu'il te faut avant de commencer

- Un compte Claude — sur [claude.ai](https://claude.ai). **Attention** :
  l'étape 1 (extraction automatique) demande un abonnement payant (Pro, Max
  ou Team) — l'extension "Claude in Chrome" n'est pas ouverte aux comptes
  gratuits pour l'instant. Si t'es en gratuit, deux options : demander à un
  camarade abonné de faire cette étape pour toi (le résultat, le JSON, se
  copie-colle ensuite chez toi sans problème), ou faire l'étape 1 à la main
  (copier les titres de leçons toi-même dans le format demandé, plus long
  mais gratuit).
- L'extension **Claude in Chrome** installée (cherche "Claude in Chrome"
  dans le Chrome Web Store) — uniquement sur **Chrome, sur ordinateur**
  pour le moment, pas sur mobile.
- Être connecté·e à ta plateforme de formation dans Chrome (login fait, tu
  dois voir tes cours quand tu ouvres le site)

## Étape 1 — Récupérer le contenu de ta formation

1. Ouvre Chrome, connecte-toi à ta plateforme de formation.
2. Clique sur l'icône Claude dans Chrome (en haut à droite du navigateur).
3. Colle ce texte tel quel (remplace juste `[coller le prompt 1 ici]` par le
   contenu du fichier `README-srs-toolkit.md`, section 1) :

   *(Le prompt exact est dans le fichier `README-srs-toolkit.md` fourni à
   côté — copie tout le bloc de code sous "1. Extraire le sommaire".)*

4. Appuie sur Entrée. Claude va parcourir ta formation tout seul, ça prend
   entre 1 et 5 minutes selon le nombre de leçons. Ne ferme pas l'onglet.
5. À la fin, Claude t'affiche un gros bloc de texte qui commence par `[` et
   finit par `]`. C'est normal, c'est le "sommaire" de ta formation dans un
   format que l'ordinateur comprend. **Copie tout ce bloc** (sélectionne
   tout, Ctrl+C ou Cmd+C).

## Étape 2 — Construire ton appli

1. Ouvre un nouvel onglet sur [claude.ai](https://claude.ai) (le site normal,
   pas l'extension Chrome).
2. Colle le **prompt 2** du fichier `README-srs-toolkit.md`, puis colle à la
   suite le texte que tu as copié à l'étape précédente (le bloc qui commence
   par `[`).
3. Envoie le message. Claude va construire ton appli — ça prend 1 à 3
   minutes. Tu vas le voir écrire du code, c'est normal, laisse-le faire.
4. À la fin, un lien ou un bouton apparaît pour ouvrir ton appli. Clique
   dessus.

**C'est tout. Ton appli existe.**

## Étape 3 — L'utiliser sur ton téléphone aussi

1. Sur ton téléphone, installe l'appli **Claude** (App Store / Play Store),
   connecte-toi avec le **même compte** que sur ton ordi.
2. Retourne dans ta conversation où tu as créé l'appli (elle est dans ton
   historique de conversations Claude).
3. Rouvre le lien de ton appli. Elle s'affiche pareil, avec la même
   progression — même si tu n'as encore rien fait dessus sur ton téléphone.

Tu peux répéter cette étape sur autant d'appareils que tu veux (tablette,
ordi du bureau, etc.), tant que c'est le même compte Claude.

## Comment s'en servir au quotidien

- Ouvre l'appli, elle te montre directement la carte du jour.
- Tu essaies de te souvenir de ce que couvrait la leçon, *avant* de cliquer
  sur un bouton.
- Tu cliques "Su" si tu t'en souvenais, "Pas su" sinon. L'appli calcule
  toute seule quand te la reproposer.
- Pas de carte affichée ? C'est que t'as tout révisé pour aujourd'hui. 🎉
- Pour ajouter une nouvelle leçon à réviser (quand tu l'as terminée dans ta
  formation), va dans la liste par chapitre en bas et clique "✓ Apprise".

## Si ça bloque

- **"Claude in Chrome" n'apparaît pas / n'est pas utilisable** → vérifie
  que tu es sur un abonnement payant (Pro, Max ou Team) — c'est requis pour
  cette extension depuis son ouverture officielle fin août 2026, les comptes
  gratuits n'y ont pas accès. Solution de secours : demande à un·e
  camarade abonné·e de te faire l'étape 1, ou fais-la à la main.
- **Le prompt 1 renvoie une erreur ou un texte bizarre** → redonne à Claude
  l'URL exacte de la page d'accueil de ta formation, il te la redemandera
  probablement de toute façon.
- **Rien ne se synchronise entre mes appareils** → vérifie que c'est bien le
  **même compte Claude** connecté partout (pas juste le même email, le même
  login utilisé pour se connecter).
