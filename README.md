# Blackwing 20 — The Puzzle

In 2025, Blackwing turned 20. To celebrate, we threw a party in Las Vegas during Black Hat and DEF CON. Every guest walked away with a 3.5" floppy disk and a USB stick.

- The **floppy** booted into a custom loader with a puzzle hidden inside.
- The **USB stick** carried some additional goodies — plus a copy of the floppy image, for anyone who couldn't track down a floppy drive in Vegas.

We're now releasing both images publicly so anyone who wants to play can.

## Download

Grab the images from the [latest release](../../releases/latest):

- `floppy.img` — bootable 1.44 MB floppy (start here)
- `usb.img` — FAT USB image with the rest

## Writing to physical media

If you want the full original experience, write the images to real hardware.

**Floppy** (1.44 MB, 3.5"):

```bash
# macOS / Linux — find your floppy device with `diskutil list` or `lsblk`
sudo dd if=floppy.img of=/dev/diskN bs=512
```

**USB stick** (any size ≥ 64 MB):

```bash
# macOS
diskutil unmountDisk /dev/diskN
sudo dd if=usb.img of=/dev/rdiskN bs=1m

# Linux
sudo dd if=usb.img of=/dev/sdX bs=1M status=progress
```

On Windows, use [Rufus](https://rufus.ie/) or [balenaEtcher](https://etcher.balena.io/) and point it at the image file.

> Double-check the device path. `dd` to the wrong disk will erase it.

## Playing without hardware

The floppy is bootable in any PC emulator. The USB image is a plain FAT filesystem and can be mounted directly to browse its contents.

Have fun!

— Blackwing Crew
