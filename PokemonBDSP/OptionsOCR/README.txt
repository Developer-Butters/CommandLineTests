Synthetic fixtures assembled from existing captured Options label/value resource crops. Full-screen layout and challenge cases are synthetic; these test recognition, not live navigation.
Source: Packages/Resources/PokemonBDSP/Autostory/Options/*_label.png and *_value.png.
16 cases cover eleven desired settings, Autosave On, missing value, different row, absent selection outline, and competing On/Off highlights.
Production checks: each case at 1920x1080, 1280x720 and 960x540, with PaddleOCR and Tesseract; 96 passed on 2026-11-12. Non-English screenshot recognition and live navigation still need validation.
Settings.json exact localized text comes from BDSP 1.3.0 *_ss_option.json, linked at https://bulbapedia.bulbagarden.net/wiki/User:Abcboy#Text_dumps .

Spanish_20261112_* are unmodified full frames from stopped 2026-11-12 20-35-02.mp4; the filename suffix is recording time in seconds (decimal replaced by hyphen). Labels and highlighted values were visually checked against the run log. These include all eleven settings, before/after corrections, the persisted Autosave Off check, save dialog, icon menu, and overworld negatives.
