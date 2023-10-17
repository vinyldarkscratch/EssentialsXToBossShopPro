# queengooborg's Minecraft Toolkit
A Python toolkit to scan Minecraft source code and generate helper files for server owners and developers.

This toolkit is designed to perform two main tasks:
- Decompiles, deobfuscates and scans the Minecraft source code to generate a list of items and their associated recipes
- Using the generated item data, create an EssentialsX `worth.yml` and a BossShopPro + BS-ItemShops set of shops

Developed and tested for 1.13 through 1.20.

*Need a worth.yml with all the new items?  Check out my fork of [X00LA's file](https://github.com/X00LA/Bukkit-Essentials-worth.yml)!  https://gist.github.com/queengooborg/92d08120f0d6d25175f6c7a30e3ccac7*

## Requirements
 - Java 8+
 - Python 3.7+
 - PyYAML (`pip install pyyaml`)
 - [`DecompilerMC`](https://github.com/hube12/DecompilerMC) (added as a submodule)

## generate_items.py

This script generates an `items.json` file in the `output/` folder, which contains a structured list of all the items and their crafting recipes.

Note: the crafting recipes are pulled directly from Minecraft's source code, and may include useless recipes or ingredient names that aren't actual blocks.  This will be adjusted over time.

```sh
python3 generate_items.py [mc_version] (-n/--no_cache)
```

## generate_worth.py

This script generates a `worth.yml` for the [EssentialsX](https://www.spigotmc.org/resources/essentialsx.9089/) Bukkit/Spigot/Paper server plugin. This is used to generate https://gist.github.com/queengooborg/92d08120f0d6d25175f6c7a30e3ccac7.

```sh
python3 generate_worth.py [mc_version] (-n/--no_cache)
```

## generate_shops.py

This script uses the `worth.yml` file generated by the above script and generates a series of configuration files for the [BossShopPro](https://www.spigotmc.org/resources/bossshoppro-the-most-powerful-chest-gui-shop-menu-plugin.222/) + [BS-ItemShops](https://www.spigotmc.org/resources/itemshops-bsp-create-fancy-gui-shops-with-minimal-effort.26640/) Bukkit/Spigot/Paper server plugin.

```sh
python3 generate_shops.py [mc_version] (-n/--no_cache)
```
