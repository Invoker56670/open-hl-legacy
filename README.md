# ☢️ Open Half-Life: The Black Mesa Trinity (Linux Portable)

Welcome to the Black Mesa Research Facility. No D-Mail required to jump back to the 1998 timeline—this project provides a pre-configured, ready-to-play, completely portable Linux package of the classic Black Mesa incident trilogy: **Half-Life**, **Opposing Force**, and **Blue Shift**.

Built entirely upon the legendary work of the [Open Half-Life](https://github.com/osen/openhl) project and the Xash3D engine, this repository skips the tedious build and extraction process. Because honestly, piecing together ancient Windows extraction tools and compiling C dependencies on modern Linux is almost as painful as debugging a neural network at 3 AM. 

I did the heavy lifting. Everything has been pre-compiled, extracted, converted to standard formats (looking at you, Blue Shift `.bsp` files), and packaged up for easy, portable play on POSIX/Linux platforms.

---

## 🎮 How to Play

Forget the "Exodia" hunt; the complete game package is now available as a single consolidated archive in the **[Releases](../../releases)** section.

1.  **Download** the latest `OpenHL Legacy v1.0 (Linux Portable RAR Build)` from the Releases page.
2.  **Extract** the archive to your preferred location.
3.  **Permissions Check:** Open your terminal in the extracted directory and ensure the binaries are executable:
    ```bash
    chmod -R +x export/
    ```
4.  **Launch it!** Run the script for the specific flavor of resonance cascade you're feeling today:

    * **Half-Life:** `./export/bin/hl`
    * **Opposing Force:** `./export/bin/opfor`
    * **Blue Shift:** `./export/bin/bshift`

> [!TIP]
> The `export` folder is 100% portable. It contains absolutely zero hard-coded paths. You can rename it, chuck it on a USB thumb drive, or bury it in your file system. It will still run.

---

## 📱 Mobile (Android) Instructions

If you want to take the disaster on the go:

1.  Install **ZArchiver**, and **Xash3D FWGS**.
2.  **Download** and **Extract** the latest `OpenHL Legacy v1.0 (Linux Portable RAR Build)` from the **[Releases](../../releases)** page with ZArchiver.
3.  Move the contents of `export/share/xash3d/*` into your device's Xash folder (usually `storage/emulated/0/xash`).
4.  **Note:** Don't forget to enable **Touch Controls** in the Xash3D FWGS configuration menu!

---

## 💽 Game Data and Preservation

**This is digital preservation, not piracy.** The game data provided here consists of the publicly distributable cache files originally shared via FilePlanet and magazine demo disks. There has been **zero cracking involved**. All files were ethically extracted using standard GCF tools and untouched, WON-era `.pak` archives. 

---

## 🙌 Acknowledgements and Credits

* **[Open Half-Life (osen/openhl)](https://github.com/osen/openhl):** The core of this preservation attempt. Huge shoutout to `osen` for a sane, POSIX-focused codebase.
* **[Flying with Gauss (Xash3D)](https://xash.su/):** An outstanding open-source re-implementation of the GoldSrc engine.
* **Matt Nadareski:** For writing the open-source unpacker for self-extracting win32 Wise executables.
* **Valve & Gearbox Software:** For creating the legends.
