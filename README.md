# Portfolio — David Toti

Portfolio de David Toti, développeur mobile et web à Abidjan.
Une seule page, sans framework ni dépendance de build : un `index.html` et des images.

**En ligne :** https://david-toti.vercel.app *(à remplacer par l'URL réelle après le premier déploiement)*

## Ce que contient la page

- Un héros, un diptyque *designer / `<coder>`*, les chiffres du projet Pharma Connect.
- Une pile de cartes parcourable au geste, au clavier et aux boutons, présentant **5 projets**.
- Un parcours, des compétences, une démonstration du design system, et un formulaire de contact.

## Structure

```
index.html          toute la page : balisage, styles et script
assets/             les 5 aperçus de projets + l'image de partage
assets/reserve/     aperçus non utilisés et originaux haute résolution (non déployés)
vercel.json         cache des images, en-têtes de sécurité
robots.txt          indexation
sitemap.xml         plan du site
```

## Modifier le contenu

Tout le contenu personnel vit dans **un seul objet `ME`**, au début du `<script>` : nom, rôle,
e-mail, disponibilité, teinte de marque, réseaux, stack, chiffres, projets, parcours, compétences.
Changez une valeur et elle se propage au titre de l'onglet, au héros, aux cartes et au pied de page.

Un projet se décrit ainsi :

```js
{ title: 'SLM Market', kind: 'web', meta: 'E-commerce de luxe',
  img: 'assets/slmmarket.png',       // aperçu ; 'logo: true' pour un logo centré
  text: "Phrase affichée sur la carte.",
  long: "Texte complet, affiché dans le dossier.",
  stack: ['Express', 'MongoDB'],
  live: 'https://…',                 // bouton vert « Visiter le site » ; '' pour le masquer
  repo: 'https://github.com/…',      // bouton « Code source »
  weight: 0.7, h: 55 }               // weight : ordre d'apparition ; h : teinte de repli
```

## Développer

Aucune installation. Ouvrez `index.html` dans un navigateur, ou servez le dossier :

```sh
npx serve .
```

## Déployer

Poussez sur GitHub, puis importez le dépôt dans Vercel : aucun réglage de build,
c'est un site statique. Après le premier déploiement, remplacez `david-toti.vercel.app`
par l'URL réelle dans `index.html` (canonical, `og:url`, `og:image`, `twitter:image`),
`robots.txt` et `sitemap.xml`.

## Accessibilité

Navigation clavier complète (`→` projet suivant, `←` précédent, `↑` dossier, `/` recherche),
cibles tactiles de 44 px, contrastes vérifiés en thème clair comme sombre, `prefers-reduced-motion`
respecté, et un repli en liste pour les cartes qui demandent un geste.

## À faire

- [ ] Déposer `cv.pdf` à la racine — le bouton « Télécharger le CV » pointe dessus.
- [ ] Renseigner l'URL LinkedIn dans `ME.socials.linkedin`.
- [ ] Renseigner le lien en ligne de Maison Bob dans `ME.projects`.
- [ ] Remplacer le domaine d'exemple après le déploiement.
