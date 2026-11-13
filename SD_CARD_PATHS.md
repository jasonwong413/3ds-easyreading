# SD Card Paths / 路径说明

## Path notation

`/` means the root of the **3DS SD card**, not the root of your computer's disk. In internal messages and source, `sdmc:/3ds/easy reading/book/` refers to the same location as `/3ds/easy reading/book/` on the SD card. Keep the space in **easy reading** and the singular directory name **book**.

## Directory layout

```text
SD card root/
└── 3ds/
    └── easy reading/
        ├── easy reading.3dsx    # Homebrew Launcher only
        ├── book/               # Your books
        ├── easy reading.xml    # Application settings and stored book state
        ├── cache/              # Generated data, created as needed
        │   ├── covers/         # Cover cache and its manifest
        │   ├── meta/           # Book metadata / index cache
        │   ├── epub/           # EPUB preparation cache
        │   ├── mobi/           # MOBI preparation cache
        │   ├── fb2/            # FB2 preparation cache
        │   └── mobi-cover/     # MOBI cover metadata cache
        ├── font/               # SD font directory, when used
        ├── resources/          # SD resources, when used
        └── easy reading.log    # Diagnostic log, when generated
```

This is a logical layout, not a list of folders you must create manually. The distributed CIA and 3DSX embed runtime resources; `font/` and `resources/` do not have to be copied separately for a normal installation. Cache subdirectories and logs appear only when needed by the current operation/build.

## What belongs where?

| Item | Location / purpose |
| --- | --- |
| Books copied from a computer | `/3ds/easy reading/book/` by default. Use this folder for EPUB, TXT and other supported files. |
| Wireless uploads | Saved into the currently configured writable library folder, normally `book/`. If the library points to bundled read-only help, uploads use the SD `book/` folder. |
| Homebrew Launcher executable | `/3ds/easy reading/easy reading.3dsx`. Rename the release 3DSX to this filename when copying it. |
| CIA installer file | Copy anywhere convenient on SD for FBI to open; the CIA is installed by the system and is not the live book-data directory. |
| Preferences / book state | `/3ds/easy reading/easy reading.xml`, managed by the app. Temporary and backup variants may also appear. |
| Generated caches | `/3ds/easy reading/cache/`. Use the app's Clear cache control rather than deleting the whole data directory. |
| Custom SD fonts/resources | `font/` and `resources/`, if you choose to use SD overrides. Embedded resources are available in the supplied release. |

Books may be browsed from a configured folder, so a customized setup can use a different library path. The table describes a default installation.

## Upgrading from earlier builds

The application migrates older edition data from `/3ds/3dslibris/`, `/config/3dslibris/` and `/config/easy reading/` into `/3ds/easy reading/`. When files conflict, it retains the older copy using `.legacy`, `.legacy2`, etc. Earlier 3DSX executables become backups rather than duplicate launcher entries. The previous `3dslibris.xml` filename is migrated to `easy reading.xml` when the destination is available.

Back up the whole `/3ds/easy reading/` directory before moving to a different SD card or reinstalling your environment. Book progress is not a substitute for backing up the actual book files.

## Internal source paths

The source tree still contains `sdmc/3ds/3dslibris/` and internal `romfs:/3ds/3dslibris/` references for bundled-resource compatibility. These are packaging / read-only paths and do **not** mean that users should create a new `3dslibris` data folder.

## 中文说明

- `/` 指 3DS 的 SD 卡根目录，`sdmc:/` 是程序对同一张 SD 卡的内部写法。
- 默认书籍目录：`/3ds/easy reading/book/`，`easy reading` 中保留空格，`book` 不带 s。
- 3DSX 路径：`/3ds/easy reading/easy reading.3dsx`；CIA 可放在 SD 卡方便安装的位置，再由 FBI 安装。
- 设置和书籍状态由 `easy reading.xml` 管理；缓存位于 `cache/`，建议通过软件中的清除缓存功能处理。
- 发行包已内嵌运行资源，普通安装不需要另外准备字体和 resources 目录。
- 旧数据目录会迁移，同名冲突保留 `.legacy` 备份；升级和换卡前备份整个数据目录。
