# GitHub publication checklist — 1.0.0

## Repository

- Suggested repository name: `easy-reading-3ds`.
- Suggested description: `Landscape ebook reader for Nintendo 3DS with English/Chinese UI and local Wi-Fi book uploads.`
- Suggested topics: `3ds`, `nintendo-3ds`, `homebrew`, `ebook-reader`, `epub`, `devkitpro`.
- Extract `easy-reading-1.0.0-source.tar.gz` and use its contents as the repository root. It contains the English-first README, bilingual guides, build instructions and license notices.
- Preserve upstream authorship, all component licenses and vendored source.
- Review inherited `.github/workflows/` before enabling Actions; this release was not built through those workflows.
- Do not upload the emulator SD card, personal books, emulator configuration, local SDK, screenshots containing private book data or build caches.

## Release

1. Commit the corresponding source snapshot to your repository.
2. Create tag **`v1.0.0`** at that commit. App and CIA versions are also 1.0.0.
3. Title: **Easy Reading 1.0.0 — Landscape reader & wireless book transfer**.
4. Paste `RELEASE-1.0.0.md` into the release description.
5. Publish as a **stable release**; leave **Set as a pre-release** unchecked.
6. Attach all six files from `assets/`: CIA, 3DSX, source archive, two user guides and SHA256SUMS.txt.
7. Preview the README links, confirm the source archive downloads, and verify the checksums before publishing.

No repository or release has been created or published by this preparation task.

## Hardware status

The maintainer has confirmed successful application testing on a Japanese New Nintendo 3DS. The supplied gallery now includes the HOME banner and English application screens on hardware. Do not imply all device models have been tested.

## Suggested short announcement

> Easy Reading 1.0.0 is a landscape ebook reader for Nintendo 3DS. It features an English/Simplified Chinese interface, a cover bookshelf, reading tools and QR-code/URL book uploads over local Wi-Fi. CIA, 3DSX and corresponding source are included. See the release notes for installation and current limitations.

## 中文发布提示

推荐仓库名 `easy-reading-3ds`，标签 `v1.0.0`。将源码包解压后的内容上传到仓库根目录，Release 粘贴 `RELEASE-1.0.0.md`，附上 `assets/` 下六个文件。按正式版本发布，不勾选 Pre-release。应用已由维护者确认实机运行正常；实机照片和中文深色模拟器截图均已加入材料。本任务只准备材料，没有替你发布。

## Included introductions and images

Upload the source tree with `docs/APP_OVERVIEW.md`, `docs/SD_CARD_PATHS.md`, `docs/PROJECT_SOURCES.md`, `docs/SCREENSHOTS.md` and `docs/images/` intact so the README gallery works. The same documentation is available directly in this materials folder.
