Flashing the Keebio Iris LM k1 with QMK

  VIA remaps are temporary. This guide makes your keymap permanent using QMK.

  ---
  Prerequisites

  - https://msys.qmk.fm/ — for compiling
  - https://github.com/qmk/qmk_toolbox/releases — for flashing

  ---
  Steps

  1. Create your keymap

  Open QMK MSYS and run:
  qmk new-keymap -kb keebio/iris_lm/k1 -km mykeymap
  This creates a keymaps/mykeymap/ folder with a keymap.c and rules.mk you can edit.

  2. Enable features

  In rules.mk, add:
  TRI_LAYER_ENABLE = yes
  VIA_ENABLE = yes
  RGB_MATRIX_ENABLE = yes

  3. Compile

  qmk compile -kb keebio/iris_lm/k1 -km mykeymap
  This produces a .bin file in your qmk_firmware/ folder.

  4. Flash

  1. Open QMK Toolbox and load the .bin file
  2. Put the left half into bootloader mode — press the reset button through the hole in the bottom plate
  3. Click Flash
  4. Repeat for the right half

  ▎ Flash both halves any time you make changes.
