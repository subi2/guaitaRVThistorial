<!--
  Guaita Apps - Suite d'eines autònomes per a arquitectura, BIM i documentació.
  Copyright (c) 2026 SBS BiM Consulting, Jordi Subirós
  GNU Affero General Public License v3.0
  See LICENSE file for details / Veure el fitxer LICENSE
-->

# GUAITA·HISTORIAL — Guaita Historial

![Guaita Historial](social-preview.png)

**[English](#english)** · **[Català](#català)**

---

<a id="english"></a>

# English

![Guaita Historial](social-preview.png)

`v3.2 · User guide`

## Who saved the model, and when — read from the file itself.

Guaita Historial reads the save history stored inside `.rvt` and `.rte` files and shows, for each file, who saved it, when, and how robust that history is. Everything runs in your browser: no file is uploaded anywhere.

**Files:** [Application (ENG)](pagesENG/guaitaRVThistorial_32-ENG.html) · [User guide (ENG)](pagesENG/130_HLP_Guaita_RVT_Historial-ajuda_32-ENG.html) · [Application (CAT)](pagesCAT/guaitaRVThistorial_32.html) · [Manual (CAT)](pagesCAT/130_HLP_Guaita_RVT_Historial-ajuda_32.html) · [Landing page](index.html) · [Català](#català)

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

---

<a id="català"></a>

# Català

`v3.2 · Manual d'ús`

## Qui ha desat el model, i quan — llegit del mateix fitxer.

Guaita Historial llegeix l'historial de desats que el fitxer `.rvt` o `.rte` porta a dins i mostra, per a cada fitxer, qui l'ha desat, quan i com de robusta és aquesta història. Tot funciona al navegador: cap fitxer no es puja enlloc.

**Fitxers:** [Aplicació (CAT)](pagesCAT/guaitaRVThistorial_32.html) · [Manual (CAT)](pagesCAT/130_HLP_Guaita_RVT_Historial-ajuda_32.html) · [Application (ENG)](pagesENG/guaitaRVThistorial_32-ENG.html) · [User guide (ENG)](pagesENG/130_HLP_Guaita_RVT_Historial-ajuda_32-ENG.html) · [Pàgina de presentació](index.html) · [English](#english)

---

## Índex

1. [Introducció](#01--introducció)
2. [Què conté el fitxer](#02--què-conté-el-fitxer)
3. [Com començar](#03--com-començar)
4. [La interfície](#04--la-interfície)
5. [Robustesa temporal](#05--robustesa-temporal)
6. [Marcar fitxers amb més d'un usuari](#06--marcar-fitxers-amb-més-dun-usuari)
7. [Exportar a TSV](#07--exportar-a-tsv)
8. [Privadesa i límits](#08--privadesa-i-límits)
9. [Resolució de problemes](#09--resolució-de-problemes)
10. [Llicència](#10--llicència)

---

## 01 · Introducció

### Un lector de l'historial de desats en una sola pàgina

- Mostra cada desat d'un fitxer `.rvt` o `.rte`: data, hora i usuari.
- Compta els desats per usuari i marca els fitxers desats per més d'una persona.
- Mesura com es reparteixen els desats en el temps, per distingir la feina constant dels desats d'última hora.
- Exporta una fila per desat en un fitxer TSV per a Excel.

L'aplicació és un únic fitxer HTML. No cal instal·lar res, ni servidor, ni connexió a internet.

## 02 · Què conté el fitxer

Cada fitxer `.rvt` o `.rte` guarda una taula interna (`Global/DocumentIncrementTable`) amb una entrada per desat. Guaita Historial llegeix aquesta taula, i el bloc `BasicFileInfo` per a les metadades del projecte. El model no s'obre mai en cap programa.

Com que la taula registra desats i no temps de feina, els indicadors descriuen **hàbits de desat**. Llegeix la secció 05 abans de treure conclusions.

## 03 · Com començar

- **Opció 1 · Fitxers:** tria un o més fitxers `.rvt` (manté premut Ctrl o Cmd per seleccionar-ne diversos). Activa **incloure .rte** per acceptar també plantilles.
- **Opció 2 · Carpeta:** tria una carpeta. Amb **subcarpetes** activat, també es miren les carpetes internes.

L'anàlisi comença en triar els fitxers. El progrés apareix a la barra d'estat.

## 04 · La interfície

- **Capçalera:** versió, Ajuda, canvi d'idioma (CA/EN) i mode clar o fosc.
- **Càrrega:** les dues opcions de càrrega, **Netejar** i **Exporta TSV**.
- **Barra de marcatge:** **Marca fitxers amb més d'un usuari**, **Durada mínima esperada** (dies) i **Usuaris excepció**.
- **Taula:** una fila per fitxer analitzat, amb desats i robustesa, Project Info, desats per usuari i l'historial complet.

## 05 · Robustesa temporal

- **Abast:** temps entre el primer i el darrer desat.
- **Dies actius:** dies naturals diferents amb algun desat.
- **Sessions:** grups de desats separats per més de 4 hores.
- **Últ. 48 h:** percentatge de desats fets dins les 48 hores abans del darrer. A partir del 80 % es marca en ambre.

Un fitxer creat a partir d'una plantilla mostra l'edat del document, no el temps de feina. Un valor «decl.» que no coincideix amb el total de desats també es marca.

> **Desar no és treballar.** Aquests indicadors són pistes per revisar, no proves.

## 06 · Marcar fitxers amb més d'un usuari

Prem **Marca fitxers amb més d'un usuari**. Les files que compleixen la condició es ressalten i el resum les enumera. Els usuaris escrits a **Usuaris excepció** (separats per comes, punt i coma o salt de línia; sense distingir majúscules) no es compten. La **Durada mínima esperada** marca en ambre els fitxers amb un abast inferior als dies indicats.

## 07 · Exportar a TSV

**Exporta TSV** descarrega un fitxer separat per tabulacions amb **una fila per cada desat** i aquestes 15 columnes: Fitxer, Carpeta, Mida (MB), Increment, Data i hora, Modificat per, Total desats (fitxer), Primer desat, Darrer desat, Abast (dies), Dies actius, Sessions, Concentració 48h (%), Build i Project Info. El fitxer es diu `RVT_Historial_aaaa-mm-dd.tsv` i porta la marca BOM UTF-8, perquè els accents es vegin bé a Excel.

## 08 · Privadesa i límits

- Tot el processament és local al navegador. Cap fitxer ni dada d'historial no s'envia enlloc.
- IBM Plex va incrustat a les pàgines, per això no fan cap petició externa.
- Les hores es mostren en la zona horària local de l'equip.
- Només es llegeixen fitxers `.rvt` i `.rte`. La resta s'ignora.

## 09 · Resolució de problemes

- **«No s'han trobat fitxers .rvt/.rte vàlids segons la selecció.»** Revisa el tipus de fitxer, o activa *subcarpetes* / *incloure .rte*.
- **«No s'ha trobat la taula d'increments».** El fitxer no té historial de desats (per exemple, un model no col·laboratiu). La fila apareix igualment, sense historial.
- **Una fila surt amb error.** El fitxer pot estar malmès, xifrat o no ser un `.rvt`/`.rte` vàlid. La resta de la selecció es processa igualment.
- **«No s'ha trobat Project Info».** No s'han pogut llegir les metadades. L'historial es mostra igualment si existeix.

## 10 · Llicència

Guaita Historial és programari lliure sota la **GNU Affero General Public License v3.0 only** (`AGPL-3.0-only`). Copyright © 2026 SBS BiM Consulting, Jordi Subirós. Veure [LICENSE](LICENSE).

IBM Plex es distribueix sota la SIL Open Font License 1.1 i va incrustat sense modificacions.

---

**Repositori:** https://github.com/subi2/guaitaRVThistorial · **Versió:** 3.2
