# Open Camera Snap (HONOR)

Open Camera 1.56.2 recompilé sous le nom de paquet `org.codeaurora.snapcam`, qui figure dans `ro.camera.aux.packagelist` sur HONOR / MagicOS. Le but : accéder aux caméras auxiliaires (téléobjectif) en Camera2 + RAW.

**Télécharger :** [OpenCamera-Snap-HONOR.apk](https://github.com/xppenTC/OpenCamera-Snap/raw/main/OpenCamera-Snap-HONOR.apk)

Version : **1.56.2-snap3**  
SHA-256 : `54d397275b48f39db7187548b9c8b7f9ef908167fb849e53bbf3f6d497f90218`

## Modifications par rapport à l'original
- `applicationId` → `org.codeaurora.snapcam`
- Nom affiché → « Open Camera Snap »
- Compilation en Java 17 (le bloc toolchain a été retiré)
- ~~**snap2** : RAW multi-résolution (`MultiResolutionImageReader`) sur les caméras logiques. Sur la caméra 2, le DNG vient de l'objectif réellement actif selon le zoom (téléobjectif au-delà de ~3x).~~ Désactivé en snap3 : le module caméra HONOR plante au déclenchement (« Serious camera error »).
- **snap2** : l'écran affiche l'objectif actif et le dernier RAW enregistré (`Zoom: 3.0x | Obj 4 | RAW cam 4 7296x5472`).
- **snap2** : si la session échoue avec le RAW multi-résolution, l'app le désactive automatiquement pour cette caméra. Pour réessayer, vide les données de l'app.

Code source d'origine (GPL-3.0) : https://sourceforge.net/p/opencamera/code/ (commit 0dd4cbe).
APK signé avec une clé de debug.

## snap3
- Active le **zoom dans le capteur** (in-sensor zoom) de Qualcomm sur les caméras qui le proposent (clés `org.codeaurora.qcamera3.sessionParameters.EnableInsensorZoom` / `inSensorZoomEnable`). Au-delà de 2x sur le téléobjectif, le capteur doit envoyer un recadrage central en pleine résolution au lieu d'une image binnée.
- Diagnostic à l'écran : `bin:oui/NON`, `crop:` (zone RAW lue sur le capteur), `isz:` (état du zoom dans le capteur), et en jaune le mode du dernier RAW enregistré.
- Si le module caméra plante avec ces réglages, ils sont désactivés automatiquement pour cette caméra. Pour réessayer, vide les données de l'app.
