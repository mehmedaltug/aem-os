# AEM OS

AEM OS is a custom, developer-focused Linux distribution built on top of a rock-solid Debian foundation. It is designed to strike the perfect balance between a lightweight, minimal system and a fully functional, ready-to-work desktop environment.

By leveraging a traditional mutable base with modern package management paradigms, AEM OS gives you the stability you expect from Debian with the fresh software availability of Flatpak and Homebrew.

## Key Features

* **Solid yet Mutable Base:** Built on Debian Trixie, AEM OS provides a robust and familiar `apt` package manager environment. You have full root access to modify your core system as you see fit.
* **Modern App Sandboxing (Flatpak):** The system comes pre-configured with Flatpak and the Flathub repository out of the box. Bloatware is purged, and essential GUI applications (like Firefox) are cleanly isolated. Flatseal is automatically provided to give the user the best experience possible with flatpak apps.
* **Developer Ready (Homebrew):** Linuxbrew (Homebrew) is pre-installed and configured for all system users natively, bypassing the usual tedious setup. It comes pre-loaded with developer essentials like `node`, `npm`, `gcc`, `openjdk`, `git`, and the GitHub CLI (`gh`).
* **Minimal GNOME Desktop:** AEM OS avoids the bloat of standard desktop environments. It ships with `gnome-core` and essential tweaks, stripping out unnecessary tours, contacts apps, and games to keep your system fast and responsive.
* **Hardware & Printing Ready:** Networking (Wi-Fi/Realtek firmware) and printing are fully pre-configured. CUPS and `system-config-printer` are baked in, meaning your printers should "just work" without hours of troubleshooting.
* **Streamlined Installation:** Powered by the modern Calamares installer, getting AEM OS onto your hardware is fast and graphical, complete with LUKS encryption support.

## Under the Hood

| Component | Technology |
| --- | --- |
| **Base System** | Debian Trixie (slim) |
| **Architecture** | `amd64` |
| **Desktop Environment** | Minimal GNOME (`gdm3`, `gnome-core`) |
| **Package Managers** | `apt`, `flatpak`, `brew` |
| **Bootloader** | GRUB (EFI and Legacy PC support) |
| **Installer** | Calamares (Custom AEM OS Branding) |

## Installation

1. **Download and Extract:** Head to the [Releases](https://github.com/mehmedaltug/aem-os/releases) page and download the highly compressed .7z archive, it is about 2.4GB. (Note: If the release contains multiple parts like .7z.001 and .7z.002, download all parts into the same folder). Extract the archive using a tool like  or Peazip to get your .iso file. Be sure to also download the .sha256 checksum to verify the extracted ISO's integrity!
2. **Flash to a USB:** Use a tool like BalenaEtcher, Rufus, or `dd` to write the ISO to a USB flash drive.
3. **Boot & Install:** Boot from the USB. You will enter a Live Environment where you can test the OS. Double-click the **"Install System"** icon on the desktop to launch the Calamares installer and follow the on-screen prompts.

## Build It Yourself

AEM OS is built using Debian's `live-build` system, automated entirely through GitHub Actions. If you want to create your own flavor or test modifications:

1. Fork this repository.
2. Modify the package lists in `config/package-lists/` or tweak the installation hooks in `config/hooks/normal/`.
3. Navigate to your repository's **Actions** tab.
4. Select the **Build ISO Image** workflow and click **Run workflow**.
5. Once the build succeeds, download your custom `.iso` from the workflow artifacts.
