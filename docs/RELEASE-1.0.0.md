# Easy Reading 1.0.0 — Landscape reader & wireless book transfer

**Stable release — 1.0.0**

Easy Reading is a landscape ebook reader for the Nintendo 3DS, based on 3dslibris and customized by **jasonwong**. This release brings together the current Easy Reading interface, bilingual controls and wireless book transfer improvements.

## About the application

Easy Reading turns the two screens of a Nintendo 3DS into a landscape reading space, combining a cover carousel, physical-button and touch controls, adjustable reading tools and local Wi-Fi book uploads. It is a customized derivative of 3dslibris rather than a new unrelated reader.

## Screenshots and documentation

The repository includes `docs/SCREENSHOTS.md` and its image files: **English on real hardware**, **Chinese in Azahar with the Dark theme**, plus the English browser upload page. See `docs/APP_OVERVIEW.md` for the application introduction, `docs/SD_CARD_PATHS.md` for the full directory layout and `docs/PROJECT_SOURCES.md` for component-by-component credits.

## SD card paths

- Books: `/3ds/easy reading/book/`.
- Homebrew Launcher: `/3ds/easy reading/easy reading.3dsx`.
- Settings / stored book state: `/3ds/easy reading/easy reading.xml`.
- Generated caches: `/3ds/easy reading/cache/`.
- Optional SD font and resource directories: `font/` and `resources/` under the same base. The release embeds runtime resources.

## Highlights

- Landscape reading, a cover carousel and an enlarged upper-screen cover preview.
- English / Simplified Chinese interface switching, with language selection first in Settings.
- Gold Light theme and blue Dark theme; red delete-mode feedback in both themes.
- Reading tools for contents, theme and supported text layout settings.
- QR-code / URL uploads from a phone or computer on the same Wi-Fi network. The web page follows the app language; multiple files and duplicate filenames are supported.
- Local transfer port fallback from 8080 through 8095.
- CIA with the custom latest supplied animated bilingual HOME banner (asset kit v15) and its original audio, embedded unchanged.

## Fixes included

- Corrected English labels, including Wireless transfer, Contents, Landscape only and Touch.
- Preserved `语言 / 转换为中文` as the route back to Chinese in the English interface.
- Fixed translated upload percentage messages.
- Revised press feedback: dock icons scale gently around a fixed center, other options retain their size, and delete feedback keeps a stationary red circle.
- Updated the book-opening transition and separated swipe gestures from cover taps.
- Moved user data to `/3ds/easy reading/`, with migration of older edition data.

## Downloads

| Asset | Use |
| --- | --- |
| `easy-reading-1.0.0.cia` | Install through FBI or your CIA installer. |
| `easy-reading-1.0.0.3dsx` | Homebrew Launcher build. |
| `easy-reading-1.0.0-source.tar.gz` | Corresponding source and third-party components. |
| `SHA256SUMS.txt` | Verify downloaded assets. |

Books go in `/3ds/easy reading/book/`. For Homebrew Launcher, use `/3ds/easy reading/easy reading.3dsx`. Back up books/settings before upgrading; an existing Easy Reading CIA can be overwritten.

## Controls

- Bookshelf: Circle Pad, D-pad left/right or L/R to select; A to open.
- Reading: A/R/ZL next page; B/L/ZR previous page; X opens tools.
- Touch the left/right reading areas to turn pages; touch the bottom-right tools icon to open tools.
- Tools: B or X resumes reading; START returns to the shelf.
- Transfer: B, START or the bottom exit button closes transfer and refreshes the shelf.

Full instructions are in `USER_GUIDE.md` and `USER_GUIDE.zh-CN.md` in the release materials, and `docs/` in the source.

## Validation and limitations

The maintainer has confirmed successful testing on a physical Japanese New Nintendo 3DS. Compilation, selected interaction/language regression tests, local port-fallback testing, CIA ExeFS hashes and banner/audio resource validation have also passed. This release replaces the banner with the latest supplied kit v15, preserving its model, animation and audio unchanged. Maintainer-supplied photographs now document the HOME banner, English bookshelf, settings, reading tools and wireless transfer.

Large or complex documents may open slowly. Some loading stages cannot be cancelled. Fixed-layout files do not support all reflow settings. Format and animation behavior can vary by device and document.

The in-app version, CIA package version and release version are all **1.0.0**. Git tag: **v1.0.0**.

## Credits

Based on [RigleGit/3dslibris](https://github.com/RigleGit/3dslibris), with UI/animation references from [ClouDS Music FA](https://github.com/Epic0522/ClouDS-Music-FA/tree/clouds-music-fa) and wireless transfer inspiration from [3DS-FileBrowser](https://github.com/ZIXT233/3DS-FileBrowser). Original author and third-party notices are retained. See the source archive for GPL/AGPL and component licenses.

---

### 中文说明

易读 1.0.0 整合横屏阅读、封面书架、中英文界面、深浅主题、阅读工具及扫码无线传书。修正英文译名、语言切换入口和按压反馈，并增加传书端口占用时的回退处理。书籍目录为 `/3ds/easy reading/book/`，旧版数据自动迁移。

这是 1.0.0 正式版；维护者已确认应用实机测试正常，发布材料附有 HOME 横幅、书架、设置、阅读工具与传书的实机照片。加载大型书籍可能较慢，部分加载阶段不可取消。安装前请备份数据，详细操作见中文指南。
