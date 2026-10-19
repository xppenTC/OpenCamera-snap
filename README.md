# Open Camera Snap (HONOR)

Open Camera 1.56.2 recompilé sous le nom de paquet `org.codeaurora.snapcam`, qui figure dans `ro.camera.aux.packagelist` sur HONOR / MagicOS. Le but : accéder aux caméras auxiliaires (téléobjectif) en Camera2 + RAW.

**Télécharger :** [OpenCamera-Snap-HONOR.apk](https://github.com/xppenTC/OpenCamera-Snap/raw/main/OpenCamera-Snap-HONOR.apk)

SHA-256 : `2edd831bce170c7eebc9fd09d93efffb4ea9c51f2c0d0728637ca59a7f7cb51f`

## Modifications par rapport à l'original
- `applicationId` → `org.codeaurora.snapcam`
- Nom affiché → « Open Camera Snap »
- Compilation en Java 17 (le bloc toolchain a été retiré)

Code source d'origine (GPL-3.0) : https://sourceforge.net/p/opencamera/code/ (commit 0dd4cbe).
APK signé avec une clé de debug.
