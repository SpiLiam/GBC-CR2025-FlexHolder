# GBC-CR2025-FlexHolder

> Removable CR2025 battery holder for Game Boy Color cartridges — flexible PCB mod, no desoldering required for battery swaps.

[![License: CERN-OHL-S v2](https://img.shields.io/badge/License-CERN--OHL--S%20v2-blue.svg)](LICENSE)
[![KiCad](https://img.shields.io/badge/EDA-KiCad-brightgreen)](https://www.kicad.org/)
[![PCB: Flex](https://img.shields.io/badge/PCB-Flexible-orange)]()

---

## The Problem

Original Game Boy Color cartridges use a CR2025 battery with **soldered tabs** welded to the cell. When the battery dies, you need a hot air station or careful iron work to replace it — risky for the PCB and the cartridge chip.

Standard CR2025 batteries (without tabs) are cheap, available everywhere, and last just as long. The only thing missing was a proper holder.

## The Solution

A **flexible PCB battery holder** that:
- Drops into the original footprint with 2 solder joints (positive + negative)
- Accepts any standard CR2025 coin cell (no tabs, no soldering)
- Uses a metal clip (MY-2032-12) for reliable, repeated swaps
- Adds a polyimide stiffener under the clip for mechanical strength

📰 **Full article (FR):** [JLCPCB Blog — Support CR2025 amovible, PCB flexible, Game Boy Color](https://jlcpcb.com/fr/blog/support-cr2025-amovible-pcb-flexible-game-boy-color)

![Finished mod installed in cartridge](image/photo-finished.png)

---

## Features

- Standard CR2025 coin cell — buy anywhere, no tabs needed
- Single solder joint installation on the cartridge PCB
- Flexible PCB conforms to cartridge shell geometry
- Polyimide stiffener for rigidity under the battery clip
- Fully open source — KiCad source files included

---

## PCB Design

| Schematic | PCB Layout | 3D Top | 3D Bottom |
|-----------|-----------|--------|-----------|
| ![schematic](image/schematic.png) | ![pcb layout](image/pcb-layout.png) | ![3d top](image/3d-render-top.png) | ![3d bottom](image/3d-render-bottom.png) |

## Bill of Materials

| Ref | Component | JLCPCB Part # | Qty |
|-----|-----------|---------------|-----|
| BT1 | MY-2032-12 battery clip (CR2025 compatible) | C964833 | 1 |
| — | Flexible PCB (this design) | — | 1 |

> The MY-2032-12 clip is designed for CR2032 but fits CR2025 with good contact pressure.

![JLCPCB component page for MY-2032-12](image/jlcpcb-component-my2032-12.png)

---

## Real Build Photos

| Parts | Flex soldered | Clip installed | Close-up |
|-------|--------------|----------------|----------|
| ![parts](image/photo-parts.png) | ![flex](image/photo-flex-installed.png) | ![clip](image/photo-clip-installed.png) | ![closeup](image/photo-clip-closeup.png) |

## Manufacturing Notes (JLCPCB)

This is a **flexible PCB** with a **polyimide stiffener**.

When ordering:
1. Select **Flex PCB** as board type
2. Upload `GERBERS-GBC-CR2025-FlexHolder.zip`
3. Select **Polyimide** stiffener in advanced options
4. In the PCB remark field, write: **"Pouvez-vous utiliser la couche (User.9) pour le stiffener en polyimide"**

| Order settings | Advanced options | Stiffener note | User.9 layer in KiCad |
|----------------|-----------------|----------------|-----------------------|
| ![order](image/jlcpcb-order-settings.png) | ![advanced](image/jlcpcb-advanced-settings.png) | ![note](image/jlcpcb-order-note.png) | ![user9](image/kicad-user9-layer.png) |

The stiffener layer (`User.9` in KiCad) defines the area that needs rigidity under the battery clip. Without this note, JLCPCB will not apply the stiffener correctly.

---

## Files

```
/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── supports de pile cr2025 GBC.kicad_pro     ← KiCad project
├── supports de pile cr2025 GBC.kicad_pcb     ← PCB layout
├── supports de pile cr2025 GBC.kicad_sch     ← Schematic
├── GERBERS-GBC-CR2025-FlexHolder/            ← Gerber files (ready to order)
│   ├── *.gbr                                 ← Gerber layers
│   ├── *.drl                                 ← Drill files
│   └── *-job.gbrjob                          ← Gerber job file
└── GERBERS-GBC-CR2025-FlexHolder.zip         ← Gerber archive (upload to JLCPCB)
```

---

## Assembly

1. Open the cartridge (Game Boy Color game)
2. Desolder the original CR2025 with tabs
3. Clean the pads
4. Position the flex PCB at the original battery pads
5. Solder the 1 or 2 contact points
6. Insert a standard CR2025 into the MY-2032-12 clip
7. Close the cartridge

No more desoldering for future battery replacements — just pop out the old CR2025 and clip in a new one.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## License

Hardware design files licensed under [CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S v2)](LICENSE).

You are free to use, study, modify and distribute this design. If you make modifications and distribute them, you must do so under the same license.

---

---

## FR — Documentation française

### Problème

Les cartouches Game Boy Color utilisent une pile CR2025 avec **languettes soudées** directement sur la pile. Pour la remplacer, il faut dessouder — opération risquée sans matériel adapté.

### Solution

Un **PCB flexible** qui :
- S'installe à la place de la pile d'origine avec 2 points de soudure (positif + négatif) — ce sont eux qui font le pont électrique entre le flex et la pile
- Accepte n'importe quelle CR2025 standard (sans languettes)
- Utilise un clip métal (MY-2032-12) pour les échanges répétés sans soudure
- Intègre un raidisseur en polyimide sous le clip pour la tenue mécanique

📰 **Article complet :** [JLCPCB Blog — Support CR2025 amovible, PCB flexible, Game Boy Color](https://jlcpcb.com/fr/blog/support-cr2025-amovible-pcb-flexible-game-boy-color)

### Fabrication (JLCPCB)

1. Choisir **Flex PCB** comme type de carte
2. Uploader `GERBERS-GBC-CR2025-FlexHolder.zip`
3. Dans les notes de commande : **"Polyimide stiffener on User.9 layer"**

### Montage

1. Ouvrir la cartouche
2. Dessouder la pile CR2025 d'origine (avec languettes)
3. Nettoyer les pastilles
4. Positionner le PCB flexible à l'emplacement d'origine
5. Souder les 2 points de contact (positif + négatif)
6. Insérer une CR2025 standard dans le clip
7. Refermer la cartouche

Les remplacements suivants ne nécessitent plus de fer à souder — juste clipser une nouvelle pile.

### Licence

Fichiers de conception sous [CERN-OHL-S v2](LICENSE). Modifications obligatoirement redistribuées sous la même licence.
