# Easy Reading — User Guide

## Installation and upgrading

### CIA

1. Copy `easy-reading-1.0.0.cia` to your SD card.
2. Install it with FBI or the CIA installer you already use on your homebrew-enabled system.
3. Launch **Easy Reading / 易读** from the HOME Menu.

An earlier Easy Reading CIA can be overwritten by installing this build. Keep a backup of your books and settings. The 3DS HOME Menu banner and audio are part of the CIA; Homebrew Launcher does not present the same HOME Menu banner.

### Homebrew Launcher

1. Create `/3ds/easy reading/` on the SD card.
2. Copy `easy-reading-1.0.0.3dsx` into it and rename it `easy reading.3dsx`.
3. Open Homebrew Launcher and launch Easy Reading.

The supplied builds embed their runtime resources. Store your own books at:

```text
/3ds/easy reading/book/
```

The space in `easy reading` is intentional. Earlier edition folders named `3dslibris` are migrated automatically. Conflicting files are retained with `.legacy` suffixes rather than overwritten. Migration also preserves earlier executable files as backups instead of leaving duplicate launcher entries.

## Bookshelf

The upper screen shows the selected book's cover and title. The lower screen displays a carousel and three dock icons:

- **Import** — circled plus; starts wireless transfer.
- **Settings** — opens the settings pages.
- **Delete** — toggles delete mode.

Use Circle Pad left/right, D-pad left/right or L/R to change the selected book. Press A to read. You can also tap a cover to select it, then tap the selected cover again to open it. Swipe across the covers to browse; dragging is distinguished from tapping so a swipe should not open a book.

Use down to move focus to the dock, left/right to choose an icon and A to activate it. Use up to return focus to the books. The shelf stops at the first and last book; it does not wrap around.

### Delete a book

Choose Delete. The covers dim and show central trash icons. Select a trash icon and confirm the deletion. This removes the book file from the SD card. Press B to leave delete mode without deleting another book.

## Reading

With the tools menu closed:

| Action | Input |
| --- | --- |
| Next page | A, R or ZL |
| Previous page | B, L or ZR |
| Open reading tools | X, or the tools icon at the lower-right corner |
| Previous page by touch | Left third of the reading area |
| Next page by touch | Right third of the reading area |

Touching the middle of the page does not open the menu. The footer shows page information, time, battery and the tools shortcut.

### Reading tools

Open the menu with X or its icon. Use the Circle Pad / D-pad and A, or touch the controls. B or X closes the menu; START returns to the bookshelf.

Available controls include contents, theme, font size, line spacing, paragraph spacing, margins and more settings. Some controls depend on the file format. Fixed-layout documents use zoom rather than reflowed font sizing, and do not support all text styling options. A contents list requires chapter information in the book.

Opening large documents can take time. If a loading stage is blocking, wait until it completes before returning to the shelf; do not rely on B or START to cancel that stage.

## Settings and language

The first item on the first settings page switches language:

- In the Chinese interface: `language` — `switch to English`.
- In the English interface: `语言` — `转换为中文`.

Choose it and press A to switch. The Chinese labels in the English interface are intentional: they identify the route back to Chinese.

Use Circle Pad / D-pad to select options and A to activate them. L and R switch settings pages. The Light theme uses gold highlights; the Dark theme uses blue highlights. Delete feedback remains red in both themes.

## Wireless book upload

1. Connect your 3DS and phone or computer to the same local Wi-Fi network.
2. Open **Import** on the bookshelf.
3. Scan the QR code, or type the full displayed URL into a browser, including its port and session path.
4. Select one or more books and choose **Upload to library**.
5. Keep both the browser page and the 3DS transfer screen open until uploads finish.
6. On the 3DS, press B or START, or tap the bottom exit button. The shelf refreshes after transfer finishes.

The browser page uses the app's selected language. After changing language, leave and reopen Import, then scan the new QR code.

Supported extensions: `.epub`, `.txt`, `.pdf`, `.cbz`, `.mobi`, `.fb2`, `.md`, `.markdown`, `.rtf`, `.odt`, `.xps`. Each file must be nonempty and no larger than **256 MiB**. A file with an existing name is saved as another copy, without replacing the original. Upload acceptance does not guarantee that every document using that extension will render successfully.

This is a local HTTP transfer service. Use it on a trusted local network and close the transfer screen when finished.

## Troubleshooting

| Problem | What to check |
| --- | --- |
| No QR code / transfer cannot start | Confirm Wi-Fi is connected; exit and reopen Import. The app tries ports 8080–8095. A simulator may have additional network restrictions. |
| Browser cannot open the page | Use the same LAN, enter the entire URL and check for guest-network/client isolation. A new session has a new URL. |
| Upload rejected | Check extension, file size, free SD space and write access. |
| Uploaded book missing | Wait for the upload to finish, then exit transfer to refresh the shelf. |
| Book opens slowly | Large images and complex layouts can take longer; test a small EPUB or TXT first. |
| No chapter list | The file may not contain supported chapter navigation. |
| Final CIA behaves differently on hardware | Report the 3DS model, system region/language, release build, exact steps and a screenshot. |

Do not attach copyrighted books publicly when reporting a problem. A small self-created sample is preferable.


See also / 另见：[Directory layout / 路径](SD_CARD_PATHS.md) · [Project sources / 来源](PROJECT_SOURCES.md) · [Screenshots / 演示](SCREENSHOTS.md).
