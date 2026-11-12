<!--
  Guaita Apps - Suite d'eines autònomes per a arquitectura, BIM i documentació.
  Copyright (c) 2026 SBS BiM Consulting, Jordi Subirós
  GNU Affero General Public License v3.0
  Veure el fitxer LICENSE per a més detalls
-->

# GUAITA·HISTORIAL — Guaita Historial

`v3.2 · Manual d'ús`

## Qui ha desat el model, i quan — llegit del mateix fitxer.

Guaita Historial llegeix l'historial de desats que el fitxer `.rvt` o `.rte` porta a dins i mostra, per a cada fitxer, qui l'ha desat, quan i com de robusta és aquesta història. Tot funciona al navegador: cap fitxer no es puja enlloc.

**Fitxers:** [Aplicació (CAT)](pagesCAT/guaitaRVThistorial_32.html) · [Manual (CAT)](pagesCAT/130_HLP_Guaita_RVT_Historial-ajuda_32.html) · [Application (ENG)](pagesENG/guaitaRVThistorial_32-ENG.html) · [User guide (ENG)](pagesENG/130_HLP_Guaita_RVT_Historial-ajuda_32-ENG.html) · [Pàgina de presentació](index.html) · [English](README.md)

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
