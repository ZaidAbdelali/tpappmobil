# TP Flutter Widgets — ZAID ABDELALI

**Module :** Développement Mobile · **Filière :** 2ACINFO · **Université Mundiapolis**  
Application Flutter Material 3 présentant `Icon`, `CircleAvatar`, `Card`, `ListTile` et l’annuaire de synthèse.

## Lancer le projet

Avec Flutter installé, depuis ce dossier :

```bash
flutter pub get
flutter run
```

L’application démarre sur le menu du TP. Chaque atelier s’ouvre en touchant sa ligne. L’image locale du campus est déclarée dans `pubspec.yaml` et utilisée comme exemple `AssetImage`.

## Contenu livré

- `lib/pages/icon_page.dart` : tailles 24/40/64, grille de 8 services avec `semanticLabel`, icône Cupertino et `IconButton` avec SnackBar.
- `lib/pages/avatar_page.dart` : initiales, photo réseau et locale, icône de secours, cinq avatars colorés, bordure et statut en ligne.
- `lib/pages/card_page.dart` : `Card`, `Card.filled`, `Card.outlined`, carte de cours avec image et boutons, liste de quatre cours cliquables.
- `lib/pages/listtile_page.dart` : écran paramètres, sélection unique, `SwitchListTile`, `CheckboxListTile`, sous-titre long et confirmation de déconnexion.
- `lib/pages/contacts_page.dart` : modèle `Etudiant`, huit contacts fictifs, favoris, recherche, suppression glissée avec annulation, page de détail et bascule du thème clair/sombre.
- `Support_TP_Widgets_ZAID_ABDELALI.pdf` : support oral en 8 diapositives.

## Réponses aux questions de réflexion

### Icon et IconButton

`Icon` est un widget d’affichage : il peint un pictogramme et ne définit aucun geste. `IconButton` est un contrôle interactif qui enveloppe une icône, reçoit une action (`onPressed`), fournit une zone tactile adaptée, un état de focus/clavier et une info-bulle. Une icône seule ne réagit pas car elle n’a ni callback ni comportement de bouton.

### URL d’image invalide dans CircleAvatar

Sans `child`, le cercle ne peut plus afficher de contenu utile si l’image échoue; il ne montre que son fond. Il faut traiter l’erreur avec `onBackgroundImageError` et prévoir une solution locale, par exemple les initiales ou une icône `person` comme enfant de secours.

### clipBehavior sur Card

Avec `Clip.antiAlias`, les pixels de l’image sont coupés selon la forme arrondie de la carte, y compris aux coins. Sans découpe, l’image peut conserver des angles carrés et dépasser visuellement des coins arrondis.

### Pourquoi placer InkWell dans Card ?

`Card` fournit la surface Material et son décor; `InkWell` à l’intérieur dessine l’onde d’encre sur cette surface. Un `InkWell` autour de la carte peut peindre l’onde derrière la surface opaque, ce qui la rend invisible. `clipBehavior` maintient l’onde dans les coins arrondis.

### ListTile par rapport à un Row construit à la main

`ListTile` aligne et espace de façon cohérente `leading`, `title`, `subtitle` et `trailing`, gère les zones tactiles, les états sélectionnés, le focus, le thème et les interactions d’accessibilité. Un `Row` exige de reconstruire ces comportements et de gérer soi-même les contraintes et les petits écrans.

## Vérifications avant remise

- Exécuter `flutter pub get`, puis `flutter analyze` et `flutter run` sur l’émulateur ou Chrome.
- Deux captures réelles de l’application (menu et atelier Icône) sont jointes ci-dessous. Les autres ateliers sont accessibles depuis le menu pour la démonstration.
- Les noms et coordonnées de l’annuaire sont fictifs, à l’exception du nom fourni pour personnaliser le TP.

## Captures de l’application

### Menu du TP

![Menu principal de l’application Flutter](screenshots/00-menu.png)

### Atelier Icon

![Atelier Icon dans l’application Flutter](screenshots/01-icon.png)

## Références officielles

- [`Icon`](https://api.flutter.dev/flutter/widgets/Icon-class.html) · [`IconButton`](https://api.flutter.dev/flutter/material/IconButton-class.html)
- [`CircleAvatar`](https://api.flutter.dev/flutter/material/CircleAvatar-class.html) · [`Card`](https://api.flutter.dev/flutter/material/Card-class.html)
- [`ListTile`](https://api.flutter.dev/flutter/material/ListTile-class.html) · [`SwitchListTile`](https://api.flutter.dev/flutter/material/SwitchListTile-class.html)
