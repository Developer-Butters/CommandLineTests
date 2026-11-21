BDSP menu cursor screenshot fixtures

The 25 numbered six-icon captures were taken on 21 November 2026 with
instance 2 on Switch 1, in English, at 1920x1080. They preserve the raw
PNG image bytes. The menu uses the default order and has a NEW Town Map tag.

Selected icons: Pokedex (3), Pokemon (4), Bag (4), TrainerCard (5),
TownMap (5), and Options (4). Only filenames were normalized: Bagg to Bag,
Trainer-Card to TrainerCard, and Town-Map to TownMap.

PokemonBDSP_MenuCursorDetector.cpp registers each numbered image with its
expected selected icon and six visible icons, at 1920, 1280 and 960 pixels
wide. PokemonBDSP_MenuDetector.cpp also registers each as a positive menu
screen in both column modes. Expected labels come from the selected icons
in the captures, not from the detector output.

Existing unnumbered fixtures cover other layouts, prior Trainer Card
failures, an ambiguous selection-animation frame and non-menu negatives.
Synthetic_* images are rejection tests, not real capture-card coverage.

No calibrated color profile is assigned to these captures. Do not infer
cross-card coverage from the resolution checks or synthetic rejection cases.
