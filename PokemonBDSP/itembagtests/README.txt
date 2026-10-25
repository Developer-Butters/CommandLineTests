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
For find_bag_item's live green-header confirmation, select the item in its
reference screenshot as described by BagItemTemplate.

The reference catalog bootstraps labels from the provided screenshots; these
are not independent accuracy tests by themselves. Three additional captures
after scrolling test the catalog against other screenshots. The suite also
checks 720p cursor detection, absent items, empty rows, all 49 cursor-to-item
movement combinations, paging counts, and unknown input handling.
Only items with reference templates are named. OCR is not used.
