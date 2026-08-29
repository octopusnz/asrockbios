# ASRock Z390 Taichi BIOS Mirror

A mirror of ASRock UEFI/BIOS updates for the **ASRock Z390 Taichi** (LGA1151, Z390/Cannon Point-H chipset), kept here alongside the Intel Management Engine (ME) and CPU microcode versions each release actually ships — information ASRock's own changelog doesn't list.

## ⚠️ Disclaimer

These files are provided **"AS IS", with no warranty of any kind, express or implied**. Use them entirely at your own risk. The maintainer(s) of this repository accept **no responsibility or liability** for any damage, data loss, bricked hardware, instability, security impact, or other issues arising from downloading, flashing, or otherwise using anything in this repository.

- Flashing a BIOS/UEFI is inherently risky. A failed or interrupted flash can brick your motherboard.
- These files are re-hosted as downloaded from ASRock. Verify file size/hash against ASRock's official [Z390 Taichi download page](https://www.asrock.com/mb/Intel/Z390%20Taichi/index.asp#BIOS) before flashing if you want an independent check.
- Always flash using ASRock's own tools (Instant Flash from within BIOS, or AsrockAPP on Windows) and keep the CMOS battery / clear-CMOS jumper in mind in case you need to recover.
- A **higher BIOS version number does not guarantee a newer ME firmware or microcode** — see the note under the table below.

## Compatibility

| | |
|---|---|
| Motherboard | ASRock Z390 Taichi |
| Socket | LGA1151 (300 series) |
| Chipset | Intel Z390 (Cannon Point-H, `CNP/CMP-H`) |
| CPU support | 8th/9th Gen Intel Core ("Coffee Lake" / "Coffee Lake Refresh") |

## Releases

This is the complete official version history for this board, as listed on [ASRock's Z390 Taichi download page](https://www.asrock.com/mb/Intel/Z390%20Taichi/index.asp#BIOS) (`ROM` variants only — for flashing via Instant Flash/AsrockAPP), plus the `4.34K`/`4.34L`/`4.35` builds already in this repo, which are no longer listed on ASRock's current page. Intel ME and CPU microcode versions were extracted directly from each file with [ME Analyzer](https://github.com/platomav/MEAnalyzer) and [MC Extractor](https://github.com/platomav/MCExtractor) — see below for how to reproduce this yourself. Newest first:

| BIOS file | Released | Intel ME (CSME) | ME build date | `906EA` | `906EB` | `906EC` | `906ED` |
|---|---|---|---|---|---|---|---|
| [Z39TC4.35.zip](Z39TC4.35.zip) | *unlisted* | `12.0.72.1757` | 2021-01-17 | F8 (2024-02-01) | F6 (2024-02-01) | F8 (2024-02-01) | 104 (2024-11-14) |
| [Z39TC4.34L.zip](Z39TC4.34L.zip) | *unlisted* | `12.1.1.1022` | 2025-07-16 | FA (2024-07-28) | F6 (2024-02-01) | F8 (2024-02-01) | 104 (2024-11-14) |
| [Z39TC4.34K.zip](Z39TC4.34K.zip) | *unlisted* | `12.0.97.2608` | 2025-02-19 | FA (2024-07-28) | F6 (2024-02-01) | F8 (2024-02-01) | 104 (2024-11-14) |
| [Z39TC4.34I.zip](Z39TC4.34I.zip) | 2024-11-07 (Beta) | `12.0.96.2562` | 2024-08-25 | F8 (2024-02-01) | F6 (2024-02-01) | F8 (2024-02-01) | 100 (2024-02-05) |
| [Z39TC4.30.zip](Z39TC4.30.zip) | 2020-01-02 | `12.0.49.1534` | 2019-11-06 | CA (2019-10-03) | CA (2019-10-03) | CA (2019-10-03) | CA (2019-10-03) |
| [Z39TC4.20.zip](Z39TC4.20.zip) | 2019-09-02 | `12.0.31.1416` | 2019-02-18 | B4 (2019-04-01) | B4 (2019-04-01) | AE (2019-02-14) | B4 (2019-02-28) |
| [Z39TC4.21.zip](Z39TC4.21.zip) | 2019-08-22 (Beta) | `12.0.31.1416` | 2019-02-18 | B4 (2019-04-01) | B4 (2019-04-01) | AE (2019-02-14) | B4 (2019-02-28) |
| [Z39TC4.10.zip](Z39TC4.10.zip) | 2019-05-15 | `12.0.31.1416` | 2019-02-18 | B4 (2019-04-01) | B4 (2019-04-01) | AE (2019-02-14) | B4 (2019-02-28) |
| [Z39TC4.00.zip](Z39TC4.00.zip) | 2019-03-20 | `12.0.8.1123` | 2018-08-22 | AA (2018-12-12) | AA (2018-12-12) | A2 (2018-09-29) | B0 (2019-02-04) |
| [Z39TC2.00.zip](Z39TC2.00.zip) | 2019-03-15 | `12.0.8.1123` | 2018-08-22 | AA (2018-12-12) | AA (2018-12-12) | A2 (2018-09-29) | — |
| [Z39TC1.90.zip](Z39TC1.90.zip) | 2019-01-16 | `12.0.8.1123` | 2018-08-22 | 9A (2018-07-16) | 9A (2018-07-16) | A0 (2018-09-17) | — |
| [Z39TC1.80.zip](Z39TC1.80.zip) | 2018-12-13 | `12.0.8.1123` | 2018-08-22 | 9A (2018-07-16) | 9A (2018-07-16) | A0 (2018-09-17) | — |
| [Z39TC1.60.zip](Z39TC1.60.zip) | 2018-11-21 | `12.0.8.1123` | 2018-08-22 | 9A (2018-07-16) | 9A (2018-07-16) | A0 (2018-09-17) | — |
| [Z39TC1.30.zip](Z39TC1.30.zip) | 2018-10-29 | `12.0.6.1120` | 2018-07-11 | 96 (2018-05-02) | 8E (2018-03-24) | 98 (2018-05-31) | — |
| [Z39TC1.20.zip](Z39TC1.20.zip) | 2018-10-29 | `12.0.6.1120` | 2018-07-11 | 96 (2018-05-02) | 8E (2018-03-24) | 98 (2018-05-31) | — |

Each `906Ex` column is an Intel CPUID signature this board supports (all four are Coffee Lake / Coffee Lake Refresh steppings), showing the microcode `Revision (date)` bundled for it — `—` means that BIOS predates support for that stepping (9th Gen/`906ED` support was added in `4.00`). "Released" dates and Beta labels are as shown on ASRock's page; "*unlisted*" means the file isn't (or is no longer) on ASRock's current download page.

> **Note:** `Z39TC4.35` ships an *older* Intel ME package (`12.0.72.1757`, built 2021-01-17) and an older `906EA` microcode (`F8` vs `FA`) than `Z39TC4.34L` before it. BIOS version numbers on this board don't increase monotonically for ME/microcode, so don't assume the latest-numbered BIOS has the newest ME or microcode — check this table, or re-run the tools below yourself, before deciding which file to flash.

## How to check the Intel ME version yourself

You can check either (a) which ME version a *downloaded BIOS file* contains before flashing, or (b) which ME version is *currently running* on your board.

### (a) Check the ME version bundled in a BIOS file — using ME Analyzer

1. Install Python 3.7+, then install ME Analyzer's dependencies:
   ```bash
   pip3 install colorama crccheck pltable
   ```
2. Download [ME Analyzer](https://github.com/platomav/MEAnalyzer) (`MEA.py` + its `.dat` database files from the Releases page, or `git clone` the repo).
3. Extract the BIOS `.zip` from this repo — it unpacks to a single raw firmware file (e.g. `Z39TC4.35`).
4. Drag and drop that file onto `MEA.py` (Windows), or run it from a terminal:
   ```bash
   python3 MEA.py Z39TC4.35
   ```
5. Read the `Version` field under the `CSE ME` block in the output — that's the Intel ME/CSME version this BIOS will install.

### (b) Check the ME version currently running on your system (Windows)

**Intel MEInfoWin64.exe** — the official Intel CSME diagnostic tool, and the most direct way to read the live firmware version:

1. Install the Intel Management Engine Interface (MEI) driver first, if not already installed (needed for the tool to talk to the ME).
2. Get `MEInfoWin64.exe` — it's part of Intel's "Intel(R) CSME System Tools" package. This isn't on Intel's public download center; the enthusiast/modding community mirrors it on the [Win-Raid forum](https://winraid.level1techs.com/t/intel-converged-security-management-engine-drivers-firmware-and-tools/30719) (the same community behind ME Analyzer/MC Extractor above).
3. Open an **administrator** Command Prompt, `cd` to the folder containing the tool, and run:
   ```bat
   MEInfoWin64.exe
   ```
4. Read the **"Current State"** / **"Version"** field near the top of the output — that's the ME firmware version actually running on your board right now.

Alternative / cross-check: dump your current SPI flash with Intel FPT (`FPTW64 -d spi.bin`) and run that dump through ME Analyzer exactly as in (a) above — this is the most authoritative method since it reads the raw firmware image directly.

Device Manager → System devices → **Intel(R) Management Engine Interface** → Driver tab shows the *MEI driver* version, not the firmware version — don't rely on it to confirm your ME firmware version.

## How to check the CPU microcode version

### Currently loaded microcode (Windows)

- **CPU-Z** (v2.11+): open the **Mainboard** tab → **BIOS** section → the microcode revision is shown there.
- **HWiNFO64** (more consistently reliable for this specific field): Summary screen or Sensors → CPU section → **Microcode Update Revision**.

### Currently loaded microcode (Linux)

```bash
grep microcode /proc/cpuinfo
```

### Microcode bundled in a BIOS file — using MC Extractor

1. Install the same dependencies as ME Analyzer (`pip3 install colorama crccheck pltable`) and download [MC Extractor](https://github.com/platomav/MCExtractor).
2. Extract the BIOS `.zip` to get the raw firmware file, same as above.
3. Run:
   ```bash
   python3 MCE.py Z39TC4.35
   ```
4. The output table lists every microcode blob in the file by `CPUID`, `Revision`, and `Date` — match `CPUID` against your CPU's own signature (shown by CPU-Z/HWiNFO64 as "Stepping"/"CPUID") to find the microcode that applies to you.

## Credits

- [ME Analyzer](https://github.com/platomav/MEAnalyzer) and [MC Extractor](https://github.com/platomav/MCExtractor) by [platomav](https://github.com/platomav), used above to analyze these BIOS files.
