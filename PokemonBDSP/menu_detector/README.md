Menu detector screenshot tests

Run SerialPrograms.exe --command-line-test-mode from the application's output folder.
The Unit Test Runner can also select PokemonBDSP::MenuDetector screenshot tests.
Fixtures resolve through UNIT_TEST_RESOURCE_PATH() under PokemonBDSP/menu_detector
in the separate CommandLineTests repository.

Top-level PNG files are expected to show the main game menu. Files beginning with
non_menu_ are expected to be rejected. Each screenshot is tested at 1920x1080,
1280x720, and 960x540. Black and white frames must also be rejected.
Missing fixture folders fail the suite. No controller inputs are sent.
