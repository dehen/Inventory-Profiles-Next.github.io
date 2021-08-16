# Installation

## Briefly

If you already have your mod loader and know how to install a mod, then you just need to install the following mods

=== "Fabric"

    - [Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api)
    - [Mod Menu](https://www.curseforge.com/minecraft/mc-mods/modmenu) (*optional*, to access the mod settings easily)
    - [This mod](../downloads/index.md)

=== "Forge"

    - [This mod](../downloads/index.md)

If you don't know how to install a mod, please follow the [tutorial](#tutorial).

## Tutorial

### 1. Install a mod loader

To run this mod, you need a mod loader. There are two: [Fabric](https://fabricmc.net/) and [Forge](https://files.minecraftforge.net/net/minecraftforge/forge/). If you don't know which to choose, we recommend Fabric.

=== "Fabric"

    1. [Download Fabric (Universal/.JAR)](https://fabricmc.net/use/)
    2. Start it
    3. Select your minecraft version
    4. Click "*Install*"

=== "Forge"

    1. [Download Forge (Recommended installer)](https://files.minecraftforge.net/net/minecraftforge/forge/)
    2. Start it
    3. Click "OK"

### 2. Install the mod

=== "Fabric"

    1. [Download Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api)
    2. [Download the mod](../downloads/index.md)
    3. *Optionally*, to access the mod settings more easily, [download Mod Menu](https://www.curseforge.com/minecraft/mc-mods/modmenu)
    4. Place them in the `.minecraft/mods` folder[^1]

=== "Forge"

    1. [Download the mod](../downloads/index.md)
    2. Place it in the `.minecraft/mods` folder[^1]

## Migrate

To Migrate from the old Inventory Profiles,

- Move `.minecraft/config/inventoryprofiles` somewhere
- Remove the old mod
- Install this mod
- Move back the `inventoryprofiles` folder from above
- Rename it to `inventoryprofilesnext`

[^1]:

    The default locations of the `.minecraft` folder are the following:

    - **Windows**: `%appdata%\.minecraft`, or `C:\Users\You\AppData\Roaming\.minecraft` 
    - **Linux**: `~/.minecraft`
    - **MacOS**: `~/Library/Application Support/minecraft`
