# HOME selection freeze: observed results

The real target is the user's Japanese New 3DS. File parsing is not a substitute for this target. No local HOME Menu hardware test is available.

| Package | HOME resources | User-reported result |
| --- | --- | --- |
| v5 | Standard static PNG template, short stereo silence | Unwraps, displays banner and enters Easy Reading |
| v6 | Original animated EN/common + ZH/JPN scenes, original user stereo audio | Freezes when selected |
| v7 | Original ZH animation in common only, original user stereo audio | Still freezes |
| v8 | Supplied replacement kit's final bilingual BNR, separated body/sheet meshes | Still freezes |
| v9 | Supplied kit's ClouDS reference BNR, actual ClouDS model and audio | User confirms normal display, no problems |
| v10 | v9 graphics/header unchanged, original user jingle replaces reference audio | User confirms normal display and original audio playback |
| v11 | Newly supplied kit-v3 Chinese common scene, 72-frame loop and new kit audio | User reports freeze |
| v12 | Latest-kit Chinese static 3D model, complete known-working v10 CWAV | User reports freeze |
| v13 | New user-supplied kit-v5 Chinese animated BNR, unchanged | User confirms normal display; top partially obscured |
| v14 | Newly supplied universal bilingual v7, original scale, COMMON root translated down 0.6 units | Pending hardware placement check |

The user separately confirms ClouDS-Music-FA's own installed application plays animation and sound on this same console. We have not extracted that installed application's exact banner/version; the v9 control is the kit's reference asset, verified against the locally available reference project model/audio.

## What is and is not established

- v7 shows that removing the optional language scene alone does not resolve the original failure.
- v8 fixes a real exporter artifact (body positions: 3960 duplicated vertices reduced to 1980) but does not resolve the reported HOME freeze. Do not describe that exporter artifact as the proven crash cause.
- v5 changes both graphics and sound. Its success does not isolate either component independently.
- The old bannertool and ClouDS's pinned newer version produce byte-identical single-scene BNR output for the tested original inputs. Do not attribute the crash to the tool version without new evidence.
- v9 must differ from v8 only in the ExeFS banner. Verify identical code, icon/SMDH, other ExeFS files, ExHeader and RomFS before delivering it.
- User confirms v9 works normally. The reference model/audio combination loads through Easy Reading's current container. This disproves a blanket inability of that container to play animated sound-enabled banners; it does not show the custom audio or custom model is safe. v10 changes only the audio to isolate the original jingle.
- A failed v9 should prioritize installed metadata/loading/installation state and the exact working ClouDS binary. It does not, on its own, prove a particular SMDH flag or RSF field is wrong.

## Build control

`HOME_BANNER_LANGUAGE=reference` selects v9 and copies `assets/easy-reading/diagnostic-reference/home-reference.bnr` unchanged. It is a visibly marked temporary control, not the user's final artwork. The application still opens Easy Reading and retains its Title ID and book directory. No automatic uninstall or HOME data deletion is performed.

The user wants one final CIA using their artwork, audio, Chinese in the Japanese slot and English elsewhere. That goal remains unverified and incomplete until hardware testing succeeds. Restore the user-designed banner after isolation; do not silently treat the reference artwork as the final product.

The v10 default is `HOME_BANNER_LANGUAGE=reference-user-audio`. It uses `diagnostic-reference/home-user-audio.bnr`, keeping every CBMD byte before the CWAV boundary identical to working v9, and verifying every resulting audio sample against the original user WAV. Same app, metadata and ROMFS; only the banner audio differs. No claim of hardware success until the user reports it.

The user confirms v10 works and the original audio plays normally. A static Easy Reading control was prepared but never delivered or hardware tested: the user supplied easy-reading-banner-kit-v3.zip before delivery. Do not interpret the retained static control assets or tests as a v11 hardware result.

Delivered v11 uses `HOME_BANNER_LANGUAGE=kit-v3`, copying the newly supplied `1_easy_reading_zh.bnr` verbatim. This newer candidate changes the CGFX animation to frame_size 72 (1.2 seconds), uses a single Chinese common slot, and also supplies a different 130002-frame stereo jingle. Both graphics and audio differ from v10: it is a user-supplied replacement candidate, not the former single-variable static control. It temporarily displays Chinese on all HOME locales. App code, SMDH, ExHeader and RomFS remain unchanged. The kit author explicitly reports no hardware/emulator tests. Prior single-scene v7 failure means the kit's language-slot hypothesis alone is not a proven root cause.

User reports v11 freezes. v12 selects `HOME_BANNER_LANGUAGE=easy-static-v3` and tests the supplied latest-kit static Chinese model with known-working v10 audio. It preserves all bytes before the CWAV boundary from kit-v3 `2_diag_zh_static.bnr`, and replaces the entire CWAV with v10's verified user-audio block. No authored skeletal CANM exists. This is a static-model control, not a final release; all HOME locales temporarily show Chinese. A passing result prioritizes the animation path; a failed result prioritizes static model/material/loading investigation. Since v11 also changed audio, do not infer that its animation duration alone is the crash cause. Compare actual v10/v12 CIA audio blocks and non-banner content, not only intermediate assets.

User reports v12 freezes. Authored flip animation is therefore not required to trigger the problem in the older user model. An investigation of static materials/geometry began, but the user explicitly interrupted it and supplied easy-reading-banner-kit-v5.zip, requesting a trial of that new package. v13 follows that request and embeds easy_reading_zh.bnr byte-for-byte. The new kit uses Blender scene assembly/export and a thin wrapper around the reference converter, with a different logo mesh (8 position vertices instead of 12), material/node layout and animated scale. The kit README's 201448-byte CGFX figure does not match its actual supplied 203896-byte CGFX; use parsed file data, not the prose value. No local execution of the new Blender pipeline or hardware proof is claimed. The supplied author explicitly says it is not hardware tested.

v13 remains Chinese-only in HOME temporarily, and uses the new kit audio; the app code, icon/SMDH, ExHeader and RomFS remain identical to working v10. The original goal of a working custom animated bilingual banner remains incomplete until hardware verification succeeds.

The user confirms v13 works and asks for the scene to fit below HOME's top curved mask. Before a scale-down candidate was delivered, the user supplied easy-reading-banner-v7.zip, explicitly saying it is already resized and only needs a downward move. The abandoned scale-down candidate was moved outside the release source and is not active. v14 preserves all v7 scales and translates COMMON down by 0.6 model units (about 6 screen pixels under the reference camera). Re-converting the unedited v7 glTF first reproduced its supplied CGFX byte-for-byte. Re-converting the edited glTF changes exactly five CGFX bytes: COMMON's zero-translation/identity hints and Y position. Scale, geometry, animation, material, texture and remaining bytes are identical. Complete CWAV is identical to supplied v7. The provided plate is universal bilingual (Easy Reading + 易读) in the common slot, rather than separate regional plates. Placement still needs the user's HOME display check.
