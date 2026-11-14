BDSP Bag screenshot tests
=========================

Run SerialPrograms.exe --command-line-test-mode from the application's output
folder. This suite is registered as PokemonBDSP::Bag screenshot tests.
The Unit Test Runner can also select this test by name.
Fixtures are resolved through UNIT_TEST_RESOURCE_PATH() under
PokemonBDSP/itembagtests in the separate CommandLineTests repository.

The log reports cursor row, each visible item, desired item row, and the next
planned movement. No controller context or controller commands are used.
Search moves are plans only: after scrolling in the game, detect again before
moving further. A static screenshot cannot determine the total rewind distance.

bag_tests.json contains the manually labelled expectations and template catalog.
To add an item template, add its label, reference image filename, and row (1-7).
To add a test, add image, cursor, seven items ("" for empty, "Unknown" for an item
without a template), and queries with expected item/action/presses.
Action names: Confirm, Up, Down, Page down, Rewind, Unknown.
Reference screenshots can show an item without selecting it for these tests.

The reference catalog bootstraps labels from the provided screenshots; these
are not independent accuracy tests by themselves. Three additional captures
after scrolling test the catalog against other screenshots. The suite also
checks 720p cursor detection, absent items, empty rows, all 49 cursor-to-item
movement combinations, paging counts, and unknown input handling.
The legacy template cases only name items with reference templates.
ocr_tests.json separately checks localized item-name OCR; its language field
defaults to eng and each case may override language (for example spa).
An optional cursor field also verifies the selected item row.
pocket_tests.json checks the shared Bag panel border, selected tab, and empty
state at 1080p, 720p, and 540p. Pocket 0 cases must reject the Bag screen.

2026-11-12 Spanish Potion regressions (developer-butters)
Source recording: 2026-11-12 20-35-02.mp4, 1920x1080.
Unmodified full frames: attempt1=1118s, attempt1-late=1120s,
attempt2=1247s, attempt2-late=1249s. All show Poción x10 selected
in the Medicine pocket; item-name OCR must return potion.
Negative screens: overworld=1114s, main-menu=1116s, Options=17.4s.
These reproduce an English Bag-heading match failing on Spanish Bolsa.
The current check uses the common panel border, not text or character icons.
