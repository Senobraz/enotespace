# Installation

Latest release: [GitHub Releases](https://github.com/Senobraz/enotespace/releases/latest).

Available files:

- `EnoteSpace-Linux-<version>.AppImage`
- `EnoteSpace-Linux-<version>.snap`

## Linux (AppImage)

1. Download the latest `AppImage` from [GitHub Releases](https://github.com/Senobraz/enotespace/releases/latest).

2. Make the file executable:

```bash
chmod +x EnoteSpace-Linux-<version>.AppImage
```

3. Run the application:

```bash
./EnoteSpace-Linux-<version>.AppImage
```

### Creating a Desktop Application Shortcut

1. Open the following directory:

```text
~/.local/share/applications/
```

2. Create the file `enotespace-appimage.desktop`:

```ini
[Desktop Entry]

Name=EnoteSpace (AppImage)

Exec=/<path_to_app_image>/EnoteSpace-Linux-<version>.AppImage

Terminal=false

Type=Application

Icon=/<path_to_icon>/enotespace.png

StartupWMClass=enotespace-appimage

Categories=Office;
```

Where:

- `<path_to_app_image>` is the full path to the AppImage.
- `<path_to_icon>` is the full path to the icon file.

3. Update the `.desktop` file cache:

```bash
update-desktop-database ~/.local/share/applications/
```

After that, EnoteSpace should appear in your application menu.

**Download icons:**

[Light](images/enotespace.png)

[Dark](images/enotespace-dark.svg)

### Application Data

Application data is stored in:

```text
~/.config/EnoteSpace/
```

## Snap

### Installing from the Snap Store

Install EnoteSpace from the Snap Store:

```bash
sudo snap install enotespace
```

### Installing from a Snap Package

1. Download the latest `.snap` package from [GitHub Releases](https://github.com/Senobraz/enotespace/releases/latest).

2. Install the Snap package:

```bash
sudo snap install --dangerous EnoteSpace-Linux-<version>.snap
```

3. Connect EnoteSpace to the host system's keyring:

```bash
sudo snap connect enotespace:password-manager-service
```

4. Run the application:

```bash
enotespace
```

The `snap connect enotespace:password-manager-service` command allows EnoteSpace to access the host system's keyring. We
recommend enabling this connection to improve database encryption.

**Do not install the application with `--classic`.**

### Updating from a Snap Package

Do not remove the currently installed Snap. Download the new `.snap` package and update the existing installation:

```bash
sudo snap install --dangerous EnoteSpace-Linux-<version>.snap
```

Your database and settings will be preserved.

### Uninstalling

```bash
sudo snap remove enotespace
```

**Important:** Uninstalling the application removes the application's local data, including the database stored at:

```text
~/snap/enotespace/current/.config/EnoteSpace/Data
```

and files stored at:

```text
~/snap/enotespace/current/.config/EnoteSpace/Files
```

If you need to keep your notes and files, back up these directories before uninstalling the application.

### Application Data

Application data is stored in:

```text
~/snap/enotespace/current/
```
