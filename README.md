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

- [Refactor (armbian based, runs on the recore)](https://wiki.iagent.no/wiki/Refactor)
  - [Klipper](https://github.com/Klipper3d/klipper)

## Mods

- [Tri-Zero](https://github.com/zruncho3d/tri-zero)
- [ZeroClick](https://github.com/zruncho3d/ZeroClick)
- [Mini Stealth](https://www.teamfdm.com/files/file/616-mini-stealth-lgx-lite/)

## Planned changes

- [Klicky probe](https://github.com/jlas1/Klicky-Probe) or similar

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
git clone git@github.com:USER/Voron-0.1-config.git
```

Remove klipper_config folder.

```bash
rm -rf ~/printer_data/config/
```

Create a symbolic link named klipper_config that points to your repository

```bash
ln -s ~/Voron-0.1-config ~/printer_data/config
```

Klipper will now read config from your repository via the symbolic link.

If you want, you can also create a link to your newly generated klipper.bin to always have it available in your config directory.

```bash
ln -s ~/klipper/out/klipper.bin ~/klipper_config/klipper.bin
```
