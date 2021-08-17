# <span class="twemoji"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M507.73 109.1c-2.24-9.03-13.54-12.09-20.12-5.51l-74.36 74.36-67.88-11.31-11.31-67.88 74.36-74.36c6.62-6.62 3.43-17.9-5.66-20.16-47.38-11.74-99.55.91-136.58 37.93-39.64 39.64-50.55 97.1-34.05 147.2L18.74 402.76c-24.99 24.99-24.99 65.51 0 90.5 24.99 24.99 65.51 24.99 90.5 0l213.21-213.21c50.12 16.71 107.47 5.68 147.37-34.22 37.07-37.07 49.7-89.32 37.91-136.73zM64 472c-13.25 0-24-10.75-24-24 0-13.26 10.75-24 24-24s24 10.74 24 24c0 13.25-10.75 24-24 24z"></path></svg></span> Installation

## Briefly

If you already have your mod loader and know how to install a mod, then you just need to install the following mods:

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
