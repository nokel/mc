# Midnight Commander for Steam Deck

A Flatpak package of [Midnight Commander](https://midnight-commander.org/), a visual file manager for the terminal, packaged for the Steam Deck.

## Installation

1. Switch your Steam Deck to Desktop Mode
2. Open Konsole
3. Run the following commands:
```bash
flatpak install --user https://github.com/nokel/mc/releases/download/v4.8.33/mc.flatpak
ln -s ~/.local/share/flatpak/exports/bin/org.gnu.mc ~/.local/share/flatpak/exports/bin/mc
echo 'export PATH="$HOME/.local/share/flatpak/exports/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Midnight Commander will now appear in the KDE application menu and you can also launch it by typing `mc` in a terminal.

## Usage

Launch from the KDE application menu, or type `mc` in a terminal.

## Building from source

If you want to build it yourself you will need a Linux desktop with Flatpak and flatpak-builder installed.
```bash
sudo apt install flatpak flatpak-builder
flatpak install flathub org.freedesktop.Platform//24.08 org.freedesktop.Sdk//24.08
git clone https://github.com/nokel/mc.git
cd mc
flatpak-builder --force-clean --install --user build-dir org.gnu.mc.yml
```

## Notes

- This Flatpak will persist through SteamOS updates
- Midnight Commander will appear in the KDE application menu after installation
