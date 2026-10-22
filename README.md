# Open Camera Snap (HONOR)

Open Camera 1.56.2 recompilé sous le nom de paquet `org.codeaurora.snapcam`, qui figure dans `ro.camera.aux.packagelist` sur HONOR / MagicOS. Le but : accéder aux caméras auxiliaires (téléobjectif) en Camera2 + RAW.

**Télécharger :** [OpenCamera-Snap-HONOR.apk](https://github.com/xppenTC/OpenCamera-Snap/raw/main/OpenCamera-Snap-HONOR.apk)

Version : **1.56.2-snap2**  
SHA-256 : `13362aaf9ede5f5042756891a7d32775aeb7dd196f09c7bd34709ec5536507dd`

## Modifications par rapport à l'original
- `applicationId` → `org.codeaurora.snapcam`
- Nom affiché → « Open Camera Snap »
- Compilation en Java 17 (le bloc toolchain a été retiré)
- **snap2** : RAW multi-résolution (`MultiResolutionImageReader`) sur les caméras logiques. Sur la caméra 2, le DNG vient de l'objectif réellement actif selon le zoom (téléobjectif au-delà de ~3x).
- **snap2** : l'écran affiche l'objectif actif et le dernier RAW enregistré (`Zoom: 3.0x | Obj 4 | RAW cam 4 7296x5472`).
- **snap2** : si la session échoue avec le RAW multi-résolution, l'app le désactive automatiquement pour cette caméra. Pour réessayer, vide les données de l'app.

Code source d'origine (GPL-3.0) : https://sourceforge.net/p/opencamera/code/ (commit 0dd4cbe).
APK signé avec une clé de debug.
