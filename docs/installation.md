# Installation

You must have [downloaded the mod](download.md)

=== "Fabric"

    **Requirements:**

    - [Fabric Loader >= 0.11.6](https://fabricmc.net/use/)
    - [Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api)
    - [Mod Menu >= 2.0.2](https://www.curseforge.com/minecraft/mc-mods/modmenu) (*optional*, to access settings easily)

    Make sure you have [Fabric](https://fabricmc.net/) installed, and place the mod .jar in the `.minecraft/mods` folder. This mod requires [Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api).

=== "Forge"

    **Requirements:**
    
    - 1.17.x: [Forge >= 37.0.17](https://files.minecraftforge.net/net/minecraftforge/forge/index_1.17.1.html)
    - 1.16.5: [Forge >= 36.1.32](https://files.minecraftforge.net/net/minecraftforge/forge/index_1.16.5.html)
    
    Place the mod .jar in the `.minecraft/mods` folder.

## Migrate

To Migrate from the old Inventory Profiles,

- Move `.minecraft/config/inventoryprofiles` somewhere
- Remove the old mod
- Install this mod
- Move back the `inventoryprofiles` folder from above
- Rename it to `inventoryprofilesnext`

## Default .minecraft locations

- **Windows**: `%appdata%\.minecraft`, or `C:\Users\You\AppData\Roaming\.minecraft` 
- **Linux**: `~/.minecraft`
- **MacOS**: `~/Library/Application Support/minecraft`
