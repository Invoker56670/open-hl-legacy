# ☢️ Open Half-Life: The Black Mesa Trinity (Linux Portable)

Welcome to the Black Mesa Research Facility. No D-Mail required to jump back to the 1998 timeline—this project provides a pre-configured, ready-to-play, completely portable Linux package of the classic Black Mesa incident trilogy: **Half-Life**, **Opposing Force**, and **Blue Shift**.

Built entirely upon the legendary work of the [Open Half-Life](https://github.com/osen/openhl) project and the Xash3D engine, this repository skips the tedious build and extraction process. Because honestly, piecing together ancient Windows extraction tools and compiling C dependencies on modern Linux is almost as painful as debugging a neural network at 3 AM. 

I did the heavy lifting. Everything has been pre-compiled, extracted, converted to standard formats (looking at you, Blue Shift `.bsp` files), and packaged up for easy, portable play on POSIX/Linux platforms.

---

## 🎮 How to Play

Because GitHub gets a little nervous around large files, the complete game package has been split into four `.rar` archive parts. Like gathering all the pieces of Exodia, you need all four for this to work.

1. **Download** all four `.rar` files to the exact same directory on your Linux machine.
2. **Extract** the first archive. Your extraction tool is smart enough to automatically stitch the four parts together into a single, complete folder(probably).
3. **Launch it!** Open your terminal, navigate to your freshly extracted directory, and run the launch script for the game you want to play (dont forget to **$chmod -R +x export/** it!!!!!!):

**To play Half-Life:**
    $ export/bin/hl

**To play Opposing Force:**
    $ export/bin/opfor

**To play Blue Shift:**
    $ export/bin/bshift

> **💡 Pro-Tip:** The `export` folder is 100% portable. It contains absolutely zero hard-coded paths. You can rename it, chuck it on a USB thumb drive, or bury it in your file system. It will still run.

>If you want to play it in android.. install termux , zarchiver and xash3d FWGS. After the usual updation, install git in turmux,gitclone this repo and extract the four rar with zarchiver..then paste the export/share/xash3d/* into the dedicated folder of xash3d FWGS (probably storage/emulated/0/xash or create one) [don't forget to enable touch in configuration/touch]
---

## 🛠️ Troubleshooting

### The Infamous "Mouse Cursor Not Locking" Bug (Click-to-Look)
If you launch the game and find that your mouse cursor is just chilling on the screen, and you have to click-and-drag to look around like it's a 1995 point-and-click adventure, don't panic. The engine just hasn't captured your mouse.

**The Fix:**
1. Open the developer console by smashing the **`~` (tilde)** key.
2. Type exactly this: `+mlook`
3. Hit **Enter** and close the console. Boom. Camera fixed.
*(Alternatively, you can go to Configuration -> Controls -> Advanced, and check the box for "Mouse look" if you prefer clicking boxes).*

---

## 💽 Game Data and Preservation

Let's clear the air: **This is digital preservation, not piracy.** The game data provided here is strictly the publicly distributable cache files originally made public by Valve and shared on popular services like FilePlanet and magazine demo disks back in the day. 

Valve's original intention was likely just a Trojan horse to popularize their newfangled "Steam DRM" platform in the early 2000s, but regardless, the data was made public. There has been **zero cracking involved**. All files were ethically extracted using standard GCF tools (straight from Valve's Developer Wiki) and untouched, WON-era `.pak` archives. 

---

## 🙌 Acknowledgements and Credits

This portable release stands on the shoulders of giants. Massive thanks to the true heroes who made this possible:

* **[Open Half-Life (osen/openhl)](https://github.com/osen/openhl):** The absolute core of this digital preservation attempt. Huge shoutout to `osen` for writing a brilliantly maintainable codebase focused on open, sane POSIX platforms rather than chasing app store trends.
* **[Flying with Gauss (Xash3D)](https://xash.su/):** An open-source, from-scratch re-implementation of the Half-Life GoldSrc engine. An outstanding technical feat.
* **Matt Nadareski:** For writing the open-source unpacker for self-extracting win32 Wise executables. It's a ridiculously cool project in its own right, and the only way we got this game data out cleanly.
* **Ryan Freeman:** For providing the initial OpenBSD port that helped shape the OpenHL project.
* **Valve & Gearbox Software:** For creating one of the greatest FPS trilogies of all time (even if we are all still a little bitter about the whole Steam DRM thing).
