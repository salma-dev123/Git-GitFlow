## Contexte
Le moteur de recherche actuel n’a pas de filtres par tags ou mots-clés.

## User Story
En tant qu’utilisateur, je veux pouvoir filtrer les articles par tags ou mots-clés afin de trouver rapidement ce que je cherche.

## Critères d’acceptation
- Given : un utilisateur sur la page de recherche
- When : il sélectionne un filtre
- Then : seuls les articles correspondant apparaissent

## Portée
- In scope : filtrage par tags, mots-clés et tri
- Out of scope : recherche avancée par date

## Notes techniques
- Endpoint API : /articles?tag=...&q=...&sort=...
- Risque : performance si beaucoup d’articles

## Tests
- Vérifier que les filtres fonctionnent (unitaires + HTTP)

## Pièces jointes
- Wireframe avec les filtres
