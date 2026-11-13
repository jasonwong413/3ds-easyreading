# Project Sources and Credits / 项目来源

Easy Reading is a customized derivative reader. The references below identify the upstream application, the projects that informed its interface and transfer flow, and the components retained in the source distribution. Credits describe each project's role; they do not imply endorsement by upstream authors.

## Main reference projects

| Project | Role in Easy Reading | Where to find the retained material |
| --- | --- | --- |
| [RigleGit / 3dslibris](https://github.com/RigleGit/3dslibris) | Base reader: application structure, document handling and reading infrastructure. Easy Reading's source is based on upstream commit `73e4a7812ac7a10865733d9065f9f4c33bebbbbb`. | `source/`, `include/`, `Makefile`, original notices; GPL-2.0-or-later inheritance. |
| [Epic0522 / ClouDS Music FA](https://github.com/Epic0522/ClouDS-Music-FA/tree/clouds-music-fa) | Reference for the cover-carousel / dock presentation and animation approach; MIT skin/motion components. The supplied HOME banner kit also follows its banner-conversion pipeline. The final Easy Reading interface includes its own adaptations. | `third_party/aero/`, its `LICENSE`, and the skin resources. |
| [ZIXT233 / 3DS-FileBrowser](https://github.com/ZIXT233/3DS-FileBrowser) | Reference for QR-code / URL wireless transfer interaction. Its bundled QRCode and picohttpparser components are retained. Easy Reading's book-upload server and bilingual page are edition-specific. | `third_party/transfer/`, `source/library/book_transfer.cpp`, `include/library/transfer_page.h`. |

## Direct components and licenses

- **MuPDF / Artifex**: PDF opening, outlines and rendering in this branch. Vendored under `third_party/mupdf/`, with AGPL-3.0-or-later notices and dependency licenses.
- **QRCode / Richard Moore**, with parts derived from **Project Nayuki**: QR generation. The original links and MIT notices are retained in `third_party/transfer/qrcode.c` and `.h`: [ricmoo/QRCode](https://github.com/ricmoo/QRCode), [Nayuki QR Code generator](https://www.nayuki.io/page/qr-code-generator-library).
- **picohttpparser**: HTTP request parsing; original copyright and MIT notices remain in `third_party/transfer/picohttpparser.c` and `.h`.
- **utf8proc, libunibreak, stb, Expat**, and the bundled fonts: preserve the component notices listed in `THIRD_PARTY_NOTICES.md`, `LICENSES/` and the vendored source trees.
- **devkitPro / devkitARM, libctru, bannertool and makerom**: build / packaging toolchain. They are build prerequisites, not claims of authorship over this edition.

## Easy Reading design and assets

**jasonwong** is the displayed author of this edition and supplied its Easy Reading branding, UI design and HOME artwork/audio kits. Version 1.0.0 uses the supplied `easy-reading-banner-v15.zip` banner as-is. The exact original kit and its construction sources are retained in `assets/easy-reading/banner-v15/`.

The hardware photographs were supplied by the maintainer. Chinese Dark-theme screenshots were captured from the 1.0.0 build in Azahar. Shown books and cover art are demonstration content; those personal book files are not included in the release or source archive, and the application licenses do not grant rights to the depicted books or cover artwork.

## License documents

Read the repository's `LICENSE`, `THIRD_PARTY_NOTICES.md`, `LICENSES/`, the MuPDF `COPYING` file and component license headers. The project retains inherited GPL notices and includes AGPL-covered MuPDF; it should not be presented as a wholly original MIT-only application. The matching source archive is distributed with the binaries.

## 中文来源说明

- **3dslibris**：本项目的阅读器基础与上游源码，原作者和许可证均保留。
- **ClouDS Music FA**：书架轮播、底栏及动画的设计参考，使用其 MIT 组件；横幅制作参考同一工具链。
- **3DS-FileBrowser**：扫码与链接传书的交互参考，保留其携带的二维码与 HTTP 解析组件；本项目另外实现面向书籍的传书服务及中英文网页。
- **jasonwong**：易读定制版署名、品牌与界面设计，以及提供的横幅、图标、音频和实机照片。
- 实机照片和模拟器截图分开标注，画面中的个人书籍不随安装包或源码包分发。
