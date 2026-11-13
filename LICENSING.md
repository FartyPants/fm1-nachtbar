# FM-1 NACHTBAR licensing

The FM-1 NACHTBAR is free software under the GNU General Public License, version 3 only (`GPL-3.0-only`, full text in
`LICENSE`). It is a fork of FM-1 TENOR SAX (FartyPants), itself a fork of the FM-1 Hybrid Piano (FartyPants), a fork of NACHTFAHRT (FartyPants), a fork of [DUB-1](https://github.com/sbegueria/fm1-dub),
itself a fork of [AMB-1](https://github.com/charlesvestal/fm1-amb) by Charles Vestal (GPL-3.0-only), which is built on
Felucca's platform layer (through X0X and FoMni), and keeps their licence. If you distribute the FM-1 NACHTBAR, or firmware
derived from it, you must give your recipients its complete corresponding source under the same licence.

The source is GPL-3.0-only and will be published in the repository <https://github.com/FartyPants/fm1-nachtbar> with
version 1.0; until then it is available on request (open an issue at <https://github.com/FartyPants/fm1-nachtbar/issues>).
The files named below are files of that source.

## Where the code comes from

| What | Origin | Licence |
| --- | --- | --- |
| Platform: `firmware/hal/`, `firmware/loader/`, `firmware/src/{libc,lcd,gfx,usb,storage,ota,midi_uart}.c`, `tools/` (build, package, install, rescue), `web/fm1*.js` | [Felucca](https://github.com/hugelton/Felucca), Copyright (C) 2026 Leo Kuroshita (@kurogedelic), Hügelton Instruments, as changed for [X0X](https://github.com/charlesvestal/fm1-x0x) and FoMni, then AMB-1, DUB-1, NACHTFAHRT, the FM-1 Hybrid Piano and the FM-1 NACHTBAR | GPL-3.0-only |
| `firmware/src/app/{panel,plat_fm1,main_fm1}.c`, `host/amb_host.c`, `web/emu/`, `tools/{make_pages,manual_html}.py`, `tools/publish_pages.sh` | adapted from X0X (itself from Felucca's `panel.c`, `main.c`, `audio.c`) | GPL-3.0-only |
| The saxophone samples: `MSax_tenor.wav`, a tenor saxophone recorded by Cranky Man (FartyPants), the author of this firmware, as encoded tables in `firmware/src/dsp/sx_data.c` (the recording itself is not in the repository) | Cranky Man's own recording | distributed with this firmware under GPL-3.0-only |
| The QOA audio codec the recordings are stored in (the sax's and the rhythm's; the decoder, `firmware/src/dsp/hp_qoa.c`, and the reference coder `tools/qoa/qoa.h` the encoder tools use) | [QOA](https://qoaformat.org/) by Dominic Szablewski | MIT (in this GPL-3.0-only work; © 2023 Dominic Szablewski; the notice is kept in `tools/qoa/LICENSE` and the decoder's header) |
| The keys' touch: `firmware/src/app/sense.c`, `tests/host/sense_test.c`, and the analog rows, the drive, the probe and the LED rule in `firmware/hal/fm1_input.h` / `fm1_adc.h` and the hooks in `firmware/src/app/plat_fm1.c` | [fm1-monk](https://github.com/charlesvestal/fm1-monk) by Charles Vestal, its port of [Velo](https://github.com/charlesvestal/fm1-velocity)'s sensing (Velo's README: "GPL-3.0-only"; its `LICENSE`: the GPL v3, checked 2026-11-04) | GPL-3.0-only |
| The idea of a browser emulator for FM-1 firmware (`web/emu/`) | [Groove OS](https://www.groove-os.com/) by Peter Gombos, whose site runs its firmware in the browser; no code from it | credit only |
| The strings (`firmware/src/dsp/ns_strings.c`) | NACHTFAHRT (FartyPants): its Drone's Strings voice and ensemble | GPL-3.0-only |
| The endless walk (`firmware/src/dsp/ns_walk.c`: After Hours' and Nightcap's chords) | NACHTFAHRT (FartyPants): its walk (`walk_from`: the Home and Wander styles, their weights and odds) and its stacking of a chord on a scale degree (`stack`); the JAZZ style (Nightcap's) is this firmware's own | GPL-3.0-only |
| The delay's time as a note value of the tempo, gliding to a new one (`firmware/src/dsp/hp_delay.c`: `DL_EASE`) | NACHTFAHRT (FartyPants): its echo's ease of its length (`echo_len`) | GPL-3.0-only |
| The slow arc (`firmware/src/dsp/ns_arc.c`: ARC) | NACHTFAHRT (FartyPants): the idea of its Density drift (`dd_tick_bar`: a target drawn now and then, eased toward once a bar), written again with its own numbers | GPL-3.0-only |
| The piano: two notes of a grand piano (C5 and C6) in `firmware/src/dsp/ns_pianodata.c`, copied from NACHTFAHRT's `pianosamp.c` by `tools/gen_piano_hi.py`, played by `firmware/src/dsp/ns_piano.c` | the Kawai grand piano ("Grand Piano, Kawai" in the source paths of Felucca's `ATTRIBUTION.txt`) of the Versilian Community Sample Library (VCSL, Versilian Studios), CC0, as in [Felucca](https://github.com/hugelton/Felucca)'s `assets/samples-cc0/PIANO` (two of its notes, shortened, normalised and faded out, by way of NACHTFAHRT) | CC0 (the samples) |
| The piano's SEA5 decoder and read head (`rl_group`, `rl_read` in `firmware/src/dsp/ns_piano.c`) and its quantiser table (`RL_DQT` in `firmware/src/dsp/ns_pianodata.c`), and the piano voice | SEA, [Daninet/sea-codec](https://github.com/Daninet/sea-codec) (Copyright (c) 2025 Dani Biró), as in M-VAVE's [fm1_open](https://github.com/m-vave/fm1_open) (its decoder and quantiser table, FM1 modifications Copyright (c) 2026 M-VAVE), by way of NACHTFAHRT (FartyPants), which wrote it again in integer arithmetic and wrote the piano voice | MIT (the SEA code and table, in this GPL-3.0-only work; the notice is kept in `tools/sea/LICENSE` and the decoder's header); GPL-3.0-only (the piano voice) |
| The rhythm's brush tap (`firmware/src/dsp/ns_drums.c`): noise under its own envelope through a state-variable band-pass, and a one-pole low-pass taking the edge off, modelled on the noise section of Skiff's `firmware/src/drumx_voice.c` (DRUM-X) and written again in float; the tap's grain and head thump are the FM-1 NACHTBAR's own | Skiff, Copyright (C) 2026 Leo Kuroshita (@kurogedelic), Hügelton Instruments, from [JIANT FM](https://github.com/juanjiant-bit/JIANT) by juanjiant-bit (as the file's header names them) | GPL-3.0-only (the file's SPDX header) |
| The rhythm's sampled sounds: a rimshot, a brush stroke on a snare, a ride cymbal, a stick on a snare and a hi-hat (`rimshot.wav`, `jazzsnarebrush.wav`, `jazzride.wav`, `stickysnare.wav`, `hihat.wav`) recorded by Cranky Man (FartyPants), the author of this firmware, as QOA streams in `firmware/src/dsp/ns_drumdata.c` (generated by `tools/gen_drums.py`: trimmed, faded and normalised; the recordings themselves are not in the repository) | Cranky Man's own recordings | distributed with this firmware under GPL-3.0-only |
| The NACHTBAR neon sign (`assets/nachtbar_neon_sign.png`; as tables in `firmware/src/app/neon_sign.h` made by `tools/gen_neon.py`: HOME's sign and the launch screen's; `docs/img/nachtbar-sign.png`) | a drawing supplied by Cranky Man (FartyPants), the author of this firmware | with the firmware, GPL-3.0-only |
| The screen reader's protocol (`firmware/src/announce.c`) | fm1-reader's `firmware/announce.c`, one copy shared by the FM-1 firmwares (the [FM-1 Screen Reader](https://charlesvestal.github.io/fm1-reader/)) | MIT (the file's SPDX header) |
| Everything else in `firmware/src/{app,dsp}`, `tests/` (the songs, the walk's JAZZ style, the drone, the key drift, the rhythm's patterns, HOME's pads) | AMB-1, as changed for DUB-1, NACHTFAHRT, the FM-1 Hybrid Piano and the FM-1 NACHTBAR | GPL-3.0-only |

The tunes' chords (`firmware/src/dsp/ns_song.c`): Neon Rain: after the chords of Love Theme (Vangelis, *Blade Runner*),
charted by Cranky Man. Six tunes play only the chords of pieces by others, read note by note from MIDI files Cranky Man
supplied (not in the repository); no melody is in the firmware (the player plays it): Unseen Man: after the chords of
To the Unknown Man (Vangelis; read from a transcription of the recording, a MusicXML file he supplied); First Light: after the chords of Songbird (Kenny G); Back Alley: after the chords of Lily
Was Here (David A. Stewart, featuring Candy Dulfer); Velvet Room: after the chords of Smooth Operator (Sade); Old Flame:
after the chords of Europa (Carlos Santana and Tom Coster; the file follows Gato Barbieri's version); Candlelight: after
the chords of Hymne (Vangelis). The tunes' names are the FM-1 NACHTBAR's own. The FM-1 NACHTBAR is not connected
with, endorsed by or supported by any of these artists. The other tunes are plain progressions of their styles.

Five more tunes play only the chords of pieces by Antonio Carlos Jobim, with the BOSSA rhythm: Beach Walk: after the
chords of The Girl from Ipanema; Low Tide: after the chords of Wave; Cold Shoulder: after the chords of How
Insensitive; Hilltop: after the chords of Corcovado; Once Before: after the chords of Once I Loved (all by Antonio
Carlos Jobim; read from chord charts Cranky Man supplied, not in the repository). The tunes' names are the FM-1
NACHTBAR's own; no melody is in the firmware. The FM-1 NACHTBAR is not connected with, endorsed by or supported by
him, his heirs or his publishers.

Test references: `tests/ref/midi/` holds MIDI test performances; the reference renders they were compared against
are kept outside the repository (`tests/ref/ptq/` is git-ignored) and are not distributed.

## Third-party material

| What | Licence | Where |
| --- | --- | --- |
| Barlow Semi Condensed (The Barlow Project Authors), the UI face | SIL OFL 1.1 | `assets/fonts/BarlowSemiCondensed-*.ttf`, `assets/fonts/Barlow-OFL.txt` |
| Terminus (Dimitar Toshkov Zhekov), an alternative font set | SIL OFL 1.1 | `assets/fonts/ter-u*.bdf`, `assets/fonts/Terminus-LICENSE.txt` |
| JieLi AC79 SDK: `uboot.boot`, `cfg_tool.bin`, `eq_cfg_hw.bin` are read from your SDK checkout at build time and placed in the package; no SDK files are in this tree | Apache-2.0 | <https://gitee.com/Jieli-Tech/fw-AC79_AIoT_SDK> |

## Trademarks

"Felucca" and "Hügelton Instruments" are names of Hügelton Instruments.
"M-VAVE" and "FM-1" are trademarks of their respective owners. The FM-1 NACHTBAR is independent firmware; it is
not affiliated with, endorsed by or supported by any of them.

## Radio

The FM-1 NACHTBAR, like NACHTFAHRT, DUB-1 and AMB-1, never enables the Bluetooth / Wi-Fi radio of the hardware.
