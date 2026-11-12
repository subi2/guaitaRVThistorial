<!--
  Guaita Apps - Suite d'eines autònomes per a arquitectura, BIM i documentació.
  Copyright (c) 2026 SBS BiM Consulting, Jordi Subirós
  GNU Affero General Public License v3.0
  See LICENSE file for details
-->

# GUAITA·HISTORIAL — Guaita Historial

`v3.2 · User guide`

## Who saved the model, and when — read from the file itself.

Guaita Historial reads the save history stored inside `.rvt` and `.rte` files and shows, for each file, who saved it, when, and how robust that history is. Everything runs in your browser: no file is uploaded anywhere.

**Files:** [Application (ENG)](pagesENG/guaitaRVThistorial_32-ENG.html) · [User guide (ENG)](pagesENG/130_HLP_Guaita_RVT_Historial-ajuda_32-ENG.html) · [Application (CAT)](pagesCAT/guaitaRVThistorial_32.html) · [Manual (CAT)](pagesCAT/130_HLP_Guaita_RVT_Historial-ajuda_32.html) · [Landing page](index.html) · [Català](README-CAT.md)

---

## Contents

1. [Introduction](#01--introduction)
2. [What the file contains](#02--what-the-file-contains)
3. [Getting started](#03--getting-started)
4. [The interface](#04--the-interface)
5. [Temporal robustness](#05--temporal-robustness)
6. [Flagging multi-user files](#06--flagging-multi-user-files)
7. [Export to TSV](#07--export-to-tsv)
8. [Privacy and limits](#08--privacy-and-limits)
9. [Troubleshooting](#09--troubleshooting)
10. [Licence](#10--licence)

---

## 01 · Introduction

### A save-history reader in a single page

- Lists every save of a `.rvt` or `.rte` file: date, time and user.
- Counts saves per user, and flags files saved by more than one person.
- Measures how the saves are spread over time, so you can tell steady work from last-minute bursts.
- Exports one row per save to a TSV file for Excel.

The application is a single HTML file. It needs no installation, no server and no internet connection.

## 02 · What the file contains

Each `.rvt` or `.rte` file keeps an internal table (`Global/DocumentIncrementTable`) with one entry per save. Guaita Historial reads that table, plus the `BasicFileInfo` block for the project metadata. The model itself is never opened in any program.

Because the table records saves and not working time, the figures describe **saving habits**. Read section 05 before drawing conclusions.

## 03 · Getting started

- **Option 1 · Files:** choose one or more `.rvt` files (hold Ctrl or Cmd to select several). Tick **include .rte** to accept templates too.
- **Option 2 · Folder:** choose a folder. With **subfolders** ticked, inner folders are searched too.

The analysis starts as soon as you choose the files. Progress appears in the status bar.

## 04 · The interface

- **Header:** version, Help, language switch (CA/EN) and light or dark mode.
- **Loading:** the two loading options, **Clear** and **Export TSV**.
- **Flagging bar:** **Flag files saved by more than one user**, **Minimum expected span** (days) and **Excluded users**.
- **Table:** one row per analysed file, with saves and robustness, Project Info, saves per user and the full history.

## 05 · Temporal robustness

- **Span:** time between the first and the last save.
- **Active days:** distinct calendar days with at least one save.
- **Sessions:** groups of saves separated by more than 4 hours.
- **Last 48 h:** share of saves made within 48 hours before the last one. 80 % or more is flagged in amber.

A file created from a template reports the age of the document, not the working time. A "decl." value that does not match the total number of saves is also flagged.

> **Saving is not working.** These indicators are leads to review, not proof.

## 06 · Flagging multi-user files

Press **Flag files saved by more than one user**. Matching rows are highlighted and the summary lists them. Users named in **Excluded users** (comma, semicolon or new line separated, case-insensitive) are not counted. The **Minimum expected span** marks in amber any file shorter than the number of days you enter.

## 07 · Export to TSV

**Export TSV** downloads a tab-separated file with **one row per save** and these 15 columns: File, Folder, Size (MB), Increment, Date and time, Saved by, Total saves (file), First save, Last save, Span (days), Active days, Sessions, Concentration 48h (%), Build and Project Info. The file is named `RVT_Historial_yyyy-mm-dd.tsv` and carries a UTF-8 byte order mark so accents display correctly in Excel.

## 08 · Privacy and limits

- All processing runs locally in the browser. No file or history data is sent anywhere.
- IBM Plex fonts are embedded, so the pages make no external requests.
- Times are shown in the local time zone of the device.
- Only `.rvt` and `.rte` files are read. Other files are ignored.

## 09 · Troubleshooting

- **"No valid .rvt/.rte files found in the selection."** Check the file type, or tick *subfolders* / *include .rte*.
- **"Increment table not found."** The file has no save history (for example, a non-collaborative model). The row still appears, without history.
- **A row shows an error.** The file may be damaged, encrypted or not a valid `.rvt`/`.rte`. The rest of the selection is still processed.
- **"Project Info not found."** The metadata block could not be read. The history is still shown if it exists.

## 10 · Licence

Guaita Historial is free software under the **GNU Affero General Public License v3.0 only** (`AGPL-3.0-only`). Copyright © 2026 SBS BiM Consulting, Jordi Subirós. See [LICENSE](LICENSE).

IBM Plex is distributed under the SIL Open Font License 1.1 and is embedded unchanged in the pages.

---

**Repository:** https://github.com/subi2/guaitaRVThistorial · **Version:** 3.2
