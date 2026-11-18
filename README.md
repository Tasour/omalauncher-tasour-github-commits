# omalauncher-tasour-github-commits

Widget OWL pour [omalauncher](https://github.com/SimonSchubert/omalauncher) affichant les derniers commits publics de @Tasour : projet, message et temps écoulé. Un tap ouvre le commit sur GitHub.

## Installation

```sh
cp github-commits.owl ~/.config/omalauncher/widgets/
owl-check ~/.config/omalauncher/widgets/github-commits.owl
```

Aucun paquet supplémentaire requis.

## Limite de requêtes

Le widget vérifie une seule fois que les deux pages de résultats sont à jour, affiche « Ce sont bien les dernières données », puis bloque le refresh manuel (bouton ↻ et tirer vers le bas) pendant 8 secondes. En cas de réponse 403/429, il conserve les dernières données connues et porte le verrou à 15 secondes : pas de rafale de requêtes après une limite GitHub.

## Données et confidentialité

Deux requêtes GET vers l'API publique de GitHub (`api.github.com/search/commits?q=author:Tasour`) toutes les 5 minutes, sans authentification, sans token et sans en-tête personnel. Le handle @Tasour est public et fait partie de la fonction du widget. Aucun email, localisation, identifiant d'appareil ou donnée du téléphone n'est envoyé. Audit de sécurité effectué avant publication : aucun secret ni donnée personnelle bloquante.

## Licence

MIT — voir [LICENSE](LICENSE).
