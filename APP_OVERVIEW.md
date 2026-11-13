# About Easy Reading / 应用介绍

**Easy Reading / 易读 1.0.0** is a homebrew ebook reader for the Nintendo 3DS family. It turns the console's two displays into a landscape reading space, with a cover-based bookshelf and controls designed for both physical buttons and the touch screen.

This edition is customized by **jasonwong** and built on **RigleGit's 3dslibris**. It keeps the upstream reading foundation while introducing the Easy Reading identity, a redesigned shelf and menus, English / Simplified Chinese interfaces, and local wireless book uploads.

## What you can do

### Browse your library

The lower screen presents a cover carousel; the upper screen enlarges the selected cover and shows the title. Navigate with Circle Pad, D-pad, L/R or a swipe, then press A or tap the selected book to open it. The dock provides Import, Settings and Delete. Delete mode dims covers and adds a central trash icon, with confirmation before removing the file.

### Read and customize

Read in landscape orientation. Turn pages with A/B, L/R, ZL/ZR or the left/right touch areas. Open tools with X or the lower-right icon to access contents, theme and supported font/spacing/margin controls. Light mode uses gold tones; Dark mode uses cool blue tones. Fixed-layout documents use a different set of controls and cannot apply every reflow setting.

### Add books without removing the SD card

Open Import, scan the QR code or enter its full URL on a phone or computer connected to the same LAN, and upload one or more books. The web interface follows the language selected in Easy Reading. Each book may be up to 256 MiB, and duplicate filenames are retained as separate copies. Exit transfer on the 3DS to refresh the library.

### Use English or Simplified Chinese

Language switching is the first setting. English mode deliberately displays `语言 / 转换为中文` for the action that returns to Chinese. Chinese mode displays `language / switch to English` for the reverse action.

## Formats and distribution

The application recognizes EPUB, TXT, PDF, CBZ, MOBI, FB2, Markdown, RTF, ODT and XPS extensions. Exact compatibility depends on the file. The release includes a CIA for HOME Menu installation and a 3DSX for Homebrew Launcher. The CIA contains the custom animated bilingual banner and audio.

Version 1.0.0 is a stable release. The maintainer reports successful testing on a Japanese New Nintendo 3DS; photographs supplied by the maintainer show the HOME banner, English shelf, settings, reading tools and transfer screen. Chinese demonstration images are captured from the 1.0.0 build in Azahar with the Dark theme.

See [Screenshots](SCREENSHOTS.md), [SD card paths](SD_CARD_PATHS.md), [User guide](USER_GUIDE.md) and [Project sources](PROJECT_SOURCES.md).

## 中文简介

易读 1.0.0 是一款基于 3dslibris 定制的任天堂 3DS 横屏电子书阅读器，由 jasonwong 设计和定制。它提供封面书架、双屏横向阅读、中英文切换、深浅主题、阅读工具与扫码无线传书，可通过按键、左摇杆和触摸操作。正式版提供 CIA 和 3DSX，书籍及数据统一使用 `/3ds/easy reading/`。中文演示使用深色主题模拟器画面，英文演示使用维护者提供的实机照片。
