# Problèmes connus

- Quand l'échelle de l'interface est supérieure à 2, ou dans le cas d'une fenêtre du jeu petite, l'écran de configuration peut ne pas montrer l'en-tête d'ancrage correctement.
- Redimensionner la fenêtre à 0x0 pixels sur l'écran de configuration peut faire planter le jeu.

## Problèmes connus sous Forge 1.17.1 à cause du manque de support des MixIn

- Empêcher le déplacement par swipe des emplacements verrouillés ne fonctionne pas.
- Empêcher la prise d'objets dans les emplacements verrouillées utilise la méthode du côté serveur: les objets sont pris dans l'inventaire puis jetés.

## Dites-nous !

Si vous rencontrez un problème, veuillez faire un ticker [ici](https://github.com/blackd/Inventory-Profiles/issues).

Si vous êtes un développeur et voulez aider à résoudre le problème, lire [contribuer](../contributing/index.md).
