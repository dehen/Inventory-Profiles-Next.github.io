# Installation

Il faut avoir [téléchargé le mod](download.md)

=== "Fabric"

    **Prérequis:**

    - [Fabric Loader >= 0.11.6](https://fabricmc.net/use/)
    - [Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api)
    - [Mod Menu >= 2.0.2](https://www.curseforge.com/minecraft/mc-mods/modmenu) (*facultatif*)

    Assurez-vous d'avoir installé [Fabric](https://fabricmc.net/) et placez le .jar du mod et de l'API dans le dossier `.minecraft/mods`.

=== "Forge"

    **Prérequis:**
    
    - 1.17.x: [Forge >= 37.0.17](https://files.minecraftforge.net/net/minecraftforge/forge/index_1.17.1.html)
    - 1.16.5: [Forge >= 36.1.32](https://files.minecraftforge.net/net/minecraftforge/forge/index_1.16.5.html)
    
    Placez le .jar du mod dans le dossier `.minecraft/mods`.

## Migrer

Pour migrer depuis l'ancien Inventory Profiles,

- Déplacez `.minecraft/config/inventoryprofiles` quelque part
- Supprimez l'ancien mod
- Installez ce mod
- Remettez `inventoryprofiles` à son emplacement
- Renommez-le `inventoryprofilesnext`

## Emplacements par défaut de .minecraft

- **Windows**: `%appdata%\.minecraft`, or `C:\Users\You\AppData\Roaming\.minecraft` 
- **Linux**: `~/.minecraft`
- **MacOS**: `~/Library/Application Support/minecraft`
