# ASRock Z390 Taichi BIOS Repository

A repo of ASRock UEFI/BIOS updates for the **ASRock Z390 Taichi** (LGA1151, Z390/Cannon Point-H chipset).

## Disclaimer

These files are provided **"AS IS", with no warranty of any kind, express or implied**. Use them entirely at your own risk. The maintainer(s) of this repository accept **no responsibility or liability** for any damage, data loss, bricked hardware, instability, security impact, or other issues arising from downloading, flashing, or otherwise using anything in this repository.

- Flashing a BIOS/UEFI is inherently risky. A failed or interrupted flash can brick your motherboard.
- These files are re-hosted as obtained from ASRock. Most were downloaded directly from ASRock's official [Z390 Taichi download page](https://www.asrock.com/mb/Intel/Z390%20Taichi/index.asp#BIOS) and can be verified by file size/hash against it; `4.30I`, `4.34D`–`4.34H`, `4.34K`, `4.34L`, and `4.35` were instead provided directly by ASRock support and aren't independently verifiable against the public page (see the note in the table below).
- Always flash using ASRock's own tools (Instant Flash from within BIOS, or AsrockAPP on Windows) and keep the CMOS battery / clear-CMOS jumper in mind in case you need to recover.
- A **higher BIOS version number does not guarantee a newer ME firmware or microcode** — see the note under the table below.

## Important things to know

- **SATA drives might not be automatically detected after flashing one of the newer BIOS versions.** Some of the newer BIOS versions in this repo change the shared M.2/SATA storage lane configuration to default to **M.2** instead of **Auto**, which disables the SATA controller/ports in the process. If your SATA drives (including a SATA boot drive) go missing from BIOS/Windows after updating, go into BIOS setup → Storage Configuration and manually set the mode back to `Auto` (or `SATA`, if you don't have an M.2 drive installed) to restore SATA drive detection.

## Backup BIOS (dual BIOS chips)

This board has two physical BIOS chips as a safety net, (see [`Z390_Taichi_Manual.pdf`](Z390_Taichi_Manual.pdf), pages 90–91):

- **`BIOS_A`** (main/active) and **`BIOS_B`** (backup). The board normally boots from `BIOS_A`; onboard LEDs `BIOS_A_LED1` / `BIOS_B_LED1` show which chip is currently active.
- **Automatic failover:** if the active chip's BIOS is corrupted or repeatedly fails to boot, the board automatically switches over and boots from the backup chip instead — no user action needed. Whether this failover behavior itself is enabled is controlled by **Advanced → Chipset Configuration → BIOS Backup Switch** in UEFI setup.
- **You can't flash the backup chip directly** with a chosen file (e.g. via Instant Flash) — ASRock blocks that for safety. The only sanctioned way to write to it is **Tools → Secure Backup UEFI** in UEFI setup, which duplicates whichever BIOS you're *currently running from* onto the *other* chip. It mirrors your current active image — it doesn't let you pick a specific file/version to put on the backup chip.
- **Use this before flashing a new BIOS** since Secure Backup UEFI only ever copies your *currently running* BIOS, run it **before** you flash anything new — while your current, working BIOS is still active — so your known-good version gets preserved on the backup chip first. Enter UEFI setup (`Del`/`F2` at boot) → **Tools** → **Secure Backup UEFI**

## Compatibility

| | |
|---|---|
| Motherboard | ASRock Z390 Taichi |
| Socket | LGA1151 (300 series) |
| Chipset | Intel Z390 (Cannon Point-H, `CNP/CMP-H`) |
| CPU support | 8th/9th Gen Intel Core ("Coffee Lake" / "Coffee Lake Refresh") |
| Manual | [Z390_Taichi_Manual.pdf](Z390_Taichi_Manual.pdf) (official ASRock user manual, mirrored here) |

## Releases

| BIOS file | Released | Intel ME (CSME) | ME build date | `906EA` | `906EB` | `906EC` | `906ED` |
|---|---|---|---|---|---|---|---|
| [Z39TC4.35.zip](Z39TC4.35.zip) | via ASRock support † | `12.0.72.1757` | 2021-01-17 | F8 (2024-02-01) | F6 (2024-02-01) | F8 (2024-02-01) | 104 (2024-11-14) |
| [Z39TC4.34L.zip](Z39TC4.34L.zip) | via ASRock support † | `12.1.1.1022` | 2025-07-16 | FA (2024-07-28) | F6 (2024-02-01) | F8 (2024-02-01) | 104 (2024-11-14) |
| [Z39TC4.34K.zip](Z39TC4.34K.zip) | via ASRock support † | `12.0.97.2608` | 2025-02-19 | FA (2024-07-28) | F6 (2024-02-01) | F8 (2024-02-01) | 104 (2024-11-14) |
| [Z39TC4.34I.zip](Z39TC4.34I.zip) | 2024-11-07 (Beta) | `12.0.96.2562` | 2024-08-25 | F8 (2024-02-01) | F6 (2024-02-01) | F8 (2024-02-01) | 100 (2024-02-05) |
| [Z39TC4.34H.zip](Z39TC4.34H.zip) | via ASRock support † | `12.0.94.2380` | 2023-05-18 | F8 (2024-02-01) | F6 (2024-02-01) | F8 (2024-02-01) | 100 (2024-02-05) |
| [Z39TC4.34G.zip](Z39TC4.34G.zip) | via ASRock support † | `12.0.94.2380` | 2023-05-18 | F4 (2023-02-23) | F4 (2023-02-23) | F4 (2023-02-23) | FA (2023-02-27) |
| [Z39TC4.34F.zip](Z39TC4.34F.zip) | via ASRock support † | `12.0.92.2145` | 2022-05-29 | F4 (2023-02-23) | F2 (2022-12-26) | F2 (2023-01-12) | FA (2023-02-27) |
| [Z39TC4.34E.zip](Z39TC4.34E.zip) | via ASRock support † | `12.0.92.2145` | 2022-05-29 | F4 (2023-02-23) | F2 (2022-12-26) | F2 (2023-01-12) | FA (2023-02-27) |
| [Z39TC4.34D.zip](Z39TC4.34D.zip) | via ASRock support † | `12.0.72.1757` | 2021-01-17 | DE (2020-05-25) | DE (2020-05-25) | DE (2020-06-03) | DE (2020-05-24) |
| [Z39TC4.30I.zip](Z39TC4.30I.zip) | via ASRock support † | `12.0.49.1534` | 2019-11-06 | CA (2019-10-03) | CA (2019-10-03) | CA (2019-10-03) | CA (2019-10-03) |
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

Each `906Ex` column is an Intel CPUID signature this board supports (all four are Coffee Lake / Coffee Lake Refresh steppings), showing the microcode `Revision (date)` bundled for it — `—` means that BIOS predates support for that stepping (9th Gen/`906ED` support was added in `4.00`). "Released" dates and Beta labels are as shown on ASRock's page.

† `4.30I`, `4.34D`–`4.34H`, `4.34K`, `4.34L`, and `4.35` were **not** downloaded from ASRock's public site — they were provided directly by ASRock support and aren't (or aren't yet) listed on the public download page. Treat their provenance accordingly: they came from ASRock, but not through the same publicly-verifiable channel as the rest of this table.

> **Note:** `Z39TC4.35`'s Intel ME package (`12.0.72.1757`, built 2021-01-17) isn't just older than `Z39TC4.34L`'s — it's *byte-identical* to the one in `Z39TC4.34D`, three versions and roughly two years earlier. Its `906EA` microcode was still updated to `F8`, so this wasn't a blanket rollback, but the ME component specifically reverted rather than advanced. BIOS version numbers on this board don't increase monotonically for ME/microcode, so don't assume the latest-numbered BIOS has the newest ME or microcode — check this table, or re-run the tools below yourself, before deciding which file to flash.

## How to check the Intel ME version yourself

You can check either (a) which ME version a *downloaded BIOS file* contains before flashing, or which ME version is *currently running* on your board, on (b) Windows or (c) Linux.

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

### (c) Check the ME version currently running on your system (Linux)

No extra tools needed — the in-kernel `mei_me` driver (present since kernel 4.18) exposes the live firmware version directly via sysfs:

```bash
cat /sys/class/mei/mei0/fw_ver
```

Each line is one firmware component in `<index>:<major>.<minor>.<hotfix>.<build>` format, e.g. `0:12.0.97.2608` — the `major.minor.hotfix.build` part is the ME/CSME version, directly comparable to the `Intel ME (CSME)` column in the table above. If `/sys/class/mei/mei0/` doesn't exist, the `mei_me` kernel module either isn't loaded or your distro's kernel is too old — `sudo modprobe mei_me` first, or check `dmesg | grep -i mei`.

Alternative / cross-check: dump your current SPI flash with [flashrom](https://www.flashrom.org/) (`sudo flashrom -p internal -r spi.bin`) and run that dump through ME Analyzer exactly as in (a) above.

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
