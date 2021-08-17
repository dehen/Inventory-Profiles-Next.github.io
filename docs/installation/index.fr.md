# <span class="twemoji"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M507.73 109.1c-2.24-9.03-13.54-12.09-20.12-5.51l-74.36 74.36-67.88-11.31-11.31-67.88 74.36-74.36c6.62-6.62 3.43-17.9-5.66-20.16-47.38-11.74-99.55.91-136.58 37.93-39.64 39.64-50.55 97.1-34.05 147.2L18.74 402.76c-24.99 24.99-24.99 65.51 0 90.5 24.99 24.99 65.51 24.99 90.5 0l213.21-213.21c50.12 16.71 107.47 5.68 147.37-34.22 37.07-37.07 49.7-89.32 37.91-136.73zM64 472c-13.25 0-24-10.75-24-24 0-13.26 10.75-24 24-24s24 10.74 24 24c0 13.25-10.75 24-24 24z"></path></svg></span> Installation

## Brièvement

Si vous avez déjà un chargeur de mods et savez déjà comment en installer, il vous faudra simplement installer les mods suivants:

=== "Fabric"

    - [Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api)
    - [Mod Menu](https://www.curseforge.com/minecraft/mc-mods/modmenu) (*optionnel*, pour accéder aux paramètres du mod facilement)
    - [Ce mod](../downloads/index.md)

=== "Forge"

    - [Ce mod](../downloads/index.md)

Si vous ne savez pas comment installer un mod, veuillez suivre le [tutoriel](#tutoriel).

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
