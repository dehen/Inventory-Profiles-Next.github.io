# Installation

## Brièvement

Si vous avez déjà un chargeur de mods et savez déjà comment en installer, il vous faudra simplement installer les mods suivant.

=== "Fabric"

    - [Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api)
    - [Mod Menu](https://www.curseforge.com/minecraft/mc-mods/modmenu) (*optionnel*, pour accéder aux paramètres du mod facilement)
    - [Ce mod](../downloads/index.md)

=== "Forge"

    - [Ce mod](../downloads/index.md)

Si vous ne savez pas comment installer un mod, veuillez suivre le [tutoriel](#tutoriel)

## Tutoriel

### 1. Installer un chargeur de mods

Pour installer ce mod, vous aurez besoin d'un chargeur de mods. Il y en a deux: [Fabric](https://fabricmc.net/) et [Forge](https://files.minecraftforge.net/net/minecraftforge/forge/). Si vous ne savez pas lequel choisir, nous recommandons Fabric.

=== "Fabric"

    1. [Téléchargez Fabric (Universal/.JAR)](https://fabricmc.net/use/)
    2. Lancez-le
    3. Sélectionnez votre version de Minecraft
    4. Cliquez sur "Install"

=== "Forge"

    1. [Téléchargez Forge (Recommended installer)](https://files.minecraftforge.net/net/minecraftforge/forge/)
    2. Lancez-le
    3. Cliquez sur "OK"

### 2. Installer le mod

=== "Fabric"

    1. [Télécharger Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api)
    2. [Téléchargez le mod](../downloads/index.md)
    3. *Optionnellement*, pour accéder aux paramètres du mod plus facilement, [téléchargez Mod Menu](https://www.curseforge.com/minecraft/mc-mods/modmenu)
    4. Placez-les dans le dossier `.minecraft/mods`

=== "Forge"

    1. [Téléchargez le mod](../downloads/index.md)
    2. PLacez-le dans le dossier `.minecraft/mods`[^1]

## Migrer

Pour migrer depuis l'ancien Inventory Profiles,

- Déplacez `.minecraft/config/inventoryprofiles` quelque part
- Supprimez l'ancien mod
- Installez ce mod
- Remettez `inventoryprofiles` à son emplacement
- Renommez-le `inventoryprofilesnext`

[^1]:

    Les emplacements par défaut du dossier `.minecraft` sont les suivants:

    - **Windows**: `%appdata%\.minecraft`, ou `C:\Users\You\AppData\Roaming\.minecraft` 
    - **Linux**: `~/.minecraft`
    - **MacOS**: `~/Library/Application Support/minecraft`
