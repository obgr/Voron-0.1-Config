# Work in progress!
# Voron Trident To be serialized

## Repo layout
printer.cfg includes subconfig and submacros from config.d and macros.d respectively.

## Hardware
- Voron 0.1
  - LDO Kit

## Software
- [Klipper](https://github.com/Klipper3d/klipper)
  - [KIAUH](https://github.com/th33xitus/kiauh)
  - [Fluidd](https://github.com/fluidd-core/fluidd)

## Mods


## Planned changes
- [Klicky probe](https://github.com/jlas1/Klicky-Probe)
- [Tri-Zero](https://github.com/zruncho3d/tri-zero)

# How do i use a git repo as config dir?
When you clone a repo, the name of the repository will most likely not be klipper_config.

There is a way to link your config repo to be read from a standard configured klipper install.

*This is done with <mark>Symbolic links</mark>*.

## Preparation

Generate and add an ssh key to github to upload config changes direct to github.

## Symbolic link magic

Clone a repo
```
cd
git clone git@github.com:USER/Voron-0.1-config.git
```
Remove klipper_config folder.
```
rm -rf klipper_config/
```
Create a symbolic link named klipper_config that points to your repository
```
ln -s Voron-0.1-config/ klipper_config
```

Klipper will now read config from your repository via the symbolic link.

If you want, you can also create a link to your newly generated klipper.bin to always have it available in your config directory.
```
ln -s ~/klipper/out/klipper.bin ~/klipper_config/klipper.bin
```
