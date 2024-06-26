# Tri Zero.1½ V0.2856

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
- [Dragon Burner v7](https://github.com/chirpy2605/voron/tree/main/V0/Dragon_Burner)

## Config and fun caveats
- Sensorless homing for X & Y
- 3 Point Print Bed Leveling
  - in a small formfactor

## How do i use a git repo as config dir?

Clone a repo

```bash
cd ~/printer_data/
# Delete old config directory
rm -rf config
# git clone
git clone https://github.com/obgr/voron-v0-config.git config
```

## Symbolic links

If you want, you can create a symbolic link to your newly generated klipper.bin to always have it available in your config directory.

```bash
ln -s ~/klipper/out/klipper.bin ~/klipper_config/klipper.bin
```
