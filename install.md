# Installation

Latest release: [Releases](https://github.com/senobraz/enotespace/releases/latest).

Files:

- `EnoteSpace-Linux-<version>.AppImage`
- `EnoteSpace-Linux-<version>.snap`

## AppImage

```bash
chmod +x EnoteSpace-Linux-<version>.AppImage
./EnoteSpace-Linux-<version>.AppImage
```

Application data: `~/.config/EnoteSpace/`.

## Flatpak

Install:

```bash
flatpak install flathub io.github.senobraz_hub.enotespace
```

Application data: `~/.var/app/io.github.senobraz_hub.enotespace/`.

### Uninstall

```bash
flatpak uninstall io.github.senobraz_hub.enotespace
```

To delete the database as well:

```bash
flatpak uninstall --delete-data io.github.senobraz_hub.enotespace
```

## Snap

Install from Snap Store:

```bash
sudo snap install enotespace
```

Local install:

```bash
sudo snap install --dangerous EnoteSpace-Linux-<version>.snap
snap connect enotespace:password-manager-service
enotespace
```

Application data: `~/snap/enotespace/current/`.

`password-manager-service` gives access to the host keyring. Optional.

Do not install with `--classic`.

### Update

Do not remove the installed snap. Download the new `.snap` and install over the existing one:

```bash
sudo snap install --dangerous EnoteSpace-Linux-<version>.snap
```

The database and settings are kept.

### Uninstall

```bash
sudo snap remove enotespace
```

Removing the app also deletes the database (`~/snap/enotespace/`). Copy that directory first if you need the notes.

### If you already uninstalled

Install again the same way as the first time:

```bash
sudo snap install --dangerous EnoteSpace-Linux-<version>.snap
snap connect enotespace:password-manager-service
enotespace
```

This is a new empty database. Old notes will not come back unless you saved `~/snap/enotespace/` beforehand.
