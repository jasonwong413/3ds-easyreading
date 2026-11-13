# Building Easy Reading 1.0.0

This edition is based on RigleGit/3dslibris commit `73e4a7812ac7a10865733d9065f9f4c33bebbbbb`. Easy Reading uses version **1.0.0** throughout the application and CIA package.

## Dependencies

The local release build used devkitARM r67 / GCC 16.1.0, libctru and the devkitPro ports for FreeType, zlib/minizip, PNG and bzip2. CIA packaging also uses bannertool 1.2.2, makerom 0.18.4 and Python 3. The exact SDK installation is external to this source archive.

MuPDF source and its third-party sources are included under `third_party/mupdf/`. `scripts/build_mupdf_minimal.sh` builds the libraries needed by the application. Fonts, artwork and runtime resources are included in the tree.

## Build

With the dependencies installed and tools available:

```sh
export DEVKITPRO=/path/to/devkitpro
export DEVKITARM="$DEVKITPRO/devkitARM"
export PATH="$DEVKITARM/bin:$DEVKITPRO/tools/bin:$PATH"
# Ensure bannertool and makerom are also in PATH.
make -j4
make -j4 cia
```

The build outputs retain inherited filenames `3dslibris.3dsx` and `3dslibris.cia`; release copies are named `easy-reading-1.0.0.3dsx` and `easy-reading-1.0.0.cia`. Embedded ROMFS paths retain the inherited directory name for compatibility. User SD data uses `/3ds/easy reading/`.

The default `HOME_BANNER_LANGUAGE=supplied-v15` selects the latest supplied bilingual HOME banner and its original audio without modifying the model, position, scale or animation. Do not replace this with the earlier diagnostic banner profiles when reproducing 1.0.0.

## Focused checks

These checks were used for the current release work:

```sh
c++ -std=c++11 -Iinclude tests/test_ui_language.cpp source/ui/ui_language.cpp -o /tmp/test_ui_language
/tmp/test_ui_language
c++ -std=c++11 -Iinclude tests/test_transfer_page.cpp -o /tmp/test_transfer_page
/tmp/test_transfer_page
c++ -std=c++17 -Iinclude tests/test_v15_interactions.cpp source/settings/prefs_button_context_utils.cpp -o /tmp/test_interactions
/tmp/test_interactions
```

The local packaging process also verified CIA ExeFS file hashes, its embedded SMDH/banner, and latest supplied model/audio integrity. The maintainer reports successful hardware testing of the application; hardware photographs of the current interface and HOME banner are included. These checks do not establish full compatibility with all devices or documents.

The inherited upstream test suite includes assumptions about the original UI and portrait settings; it is not a substitute for checking this edition's behavior. The existing Docker and CI workflows were inherited and have not been used to reproduce this release. A byte-for-byte clean-room reproduction is not claimed.
