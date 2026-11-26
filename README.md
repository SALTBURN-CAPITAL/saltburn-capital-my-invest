# My Invest. — SALTBURN CAPITAL

## Contenu
- `index.html` : application autonome
- `manifest.webmanifest` et `sw.js` : installation PWA et cache hors ligne
- `assets/` : icônes dérivées du visuel de coffre fourni

## Démarrage
Ouvrir `index.html` pour une utilisation locale. Pour l'installation PWA et le mode hors ligne, publier le dossier sur un hébergement HTTPS statique (par exemple GitHub Pages), puis ouvrir l'URL et utiliser le menu Installer / Ajouter à l'écran d'accueil.

## Données
Les données sont stockées dans `localStorage` du navigateur. Elles ne sont pas synchronisées entre appareils. Utiliser régulièrement l'export JSON pour sauvegarder et l'import JSON pour restaurer.

## Fonctionnement de l'historique
Chaque opération est conservée avec sa date. Les valorisations sont recalculées chronologiquement. Une opération de type « Définir la valorisation totale » fixe le montant de la catégorie à cette date. Le graphique global est reconstruit à partir de ces points.

## Limites de cette V1
- EUR uniquement.
- Valorisation manuelle : pas de connexion bancaire ou de cours de marché.
- Le patrimoine net correspond à la somme des huit catégories ; les dettes ne sont pas suivies séparément.
- Les données restent propres à un navigateur / appareil.
## Allocations personnalisées
La section « Mes placements » permet d'ajouter une allocation avec un nom personnalisé. Chaque carte peut être supprimée ; la suppression demande confirmation et efface également les opérations et valorisations de cette allocation. Les allocations sont incluses dans les sauvegardes JSON. Les anciennes sauvegardes sans liste d'allocations restent compatibles et retrouvent les huit catégories initiales.

## Graphiques de valorisation
- Le graphique global adapte automatiquement son axe vertical aux valeurs observées, afin de rendre visibles les variations sans commencer systématiquement à zéro.
- Chaque allocation dispose d'un détail accessible depuis sa carte : valeur actuelle, variation sur la période choisie, courbe dédiée et historique des opérations propres à cette allocation.
- Les graphiques individuels réutilisent les opérations déjà enregistrées ; aucune migration ou remise à zéro des données n'est nécessaire.
