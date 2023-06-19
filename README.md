# Tri Zero.1½ To be serialized

Work in progress! config is not finalized.

## Repo layout

printer.cfg includes subconfig and submacros from config.d and macros.d respectively.

## Hardware

- Tri Zero (Voron 0.1½)
  - Electronics
    - [Recore A7 Mainboard](https://www.iagent.no/product/recore/)
  - General
    - LDO Kit
    - [Bondtech LGX Lite](https://www.bondtech.se/product/lgx-lite-extruder-custom/)
    - [E3D Revo voron](https://e3d-online.com/products/revo-voron)

## Software

- [Rebuild (Armbian which runs on the recore)](https://github.com/intelligent-agent/Rebuild)
  - [Klipper](https://github.com/Klipper3d/klipper)
  - [Fluidd](https://github.com/fluidd-core/fluidd)

## Mods

- [Tri-Zero](https://github.com/zruncho3d/tri-zero)
- [ZeroClick](https://github.com/zruncho3d/ZeroClick)
- [Dragon Burner v6](https://github.com/chirpy2605/voron/tree/main/V0/Dragon_Burner)

## Config and fun caveats
- Sensorless homing for X & Y
- 3 Point Print Bed Leveling
  - in a small formfactor

## How do i use a git repo as config dir?

When you clone a repo, the name of the repository will most likely not be klipper_config.

There is a way to link your config repo to be read from a standard configured klipper install.

*This is done with <mark>Symbolic links</mark>*.

### Preparation

Generate and add an ssh key to github to upload config changes direct to github.

### Symbolic link magic

Clone a repo

```bash
cd
git clone https://github.com/obgr/voron-v0-config.git
```

Remove klipper_config folder.

```bash
# Move old config dir for backup
mv ~/printer_data/config/ ~/printer_data/config_bak/
# or remove the dir.
rm -rf ~/printer_data/config/
```

Create a symbolic link named klipper_config that points to your repository

```bash
ln -s ~/voron-v0-config/ ~/printer_data/config
```

Klipper will now read config from your repository via the symbolic link.

If you want, you can also create a link to your newly generated klipper.bin to always have it available in your config directory.

```bash
ln -s ~/klipper/out/klipper.bin ~/klipper_config/klipper.bin
```
