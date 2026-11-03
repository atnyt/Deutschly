# Deutschly data sources and licensing notes

Last reviewed: 2026-11-03

This file records the known provenance of the data currently present in the
repository. It is a source inventory, not legal advice and not a grant of
rights. A source URL or citation does not by itself grant permission to copy,
adapt, publish, or redistribute that source's content.

## 1. Software code

The repository's original software source code is covered by the MIT License
in the root `LICENSE` file, only to the extent the Deutschly maintainer(s)
own or control the relevant rights. The MIT License does not cover the data
files or third-party materials listed below.

## 2. A1 vocabulary database

File: `data/a1-vocabulary.json`

The current database identifies its primary source as a user-provided PDF
titled **“A1 Vocabulary list_Deutsch mit Shakil”**. Its provenance metadata
records 1,715 source rows reconciled against a 40-page PDF, 10 duplicate rows
consolidated, and 8 omitted entries recovered, resulting in 1,713 normalized
headwords. Individual records retain source-page references to
“Deutsch mit Shakil A1 PDF”.

The repository review did not establish that this PDF or its selection,
translations, examples, or compiled list is licensed for redistribution, nor
did it establish that the Deutschly maintainer owns those rights or has
permission from the relevant rights holder. Therefore this database is
**not licensed under the repository's MIT License**. Do not treat the
presence of the file in this public repository as proof that it is free to
reuse. Obtain written permission or verify a license from the actual rights
holder before granting redistribution or adaptation rights. If permission
cannot be established, remove or replace the affected source-derived
material before presenting the dataset as openly licensed.

The independent grammar checks, corrections, Bengali explanations, and
examples added by Deutschly should be distinguished from material transcribed
or adapted from the source PDF. A source citation is not a substitute for
permission where permission is required.

## 3. Vocabulary audit

File: `data/a1-vocabulary-audit.json`

This audit records the source PDF name, page reconciliation, source-row
counts, and corrections/checks related to the A1 vocabulary database. Because
it contains provenance and analysis derived from the same source material, it
is also excluded from the MIT License. Its redistribution status should be
reviewed together with the A1 vocabulary database.

## 4. Grammar terminology and compound analysis

Files:
- `data/grammar-terms.json`
- `data/compound-analysis.json`

These files contain curated German–Bengali explanations, examples, and
analyses with references to sources such as IDS grammis, Goethe-Institut,
Duden, and the University of Michigan. The references are provided for
verification; they do not mean those organizations have endorsed Deutschly
or granted permission to reproduce their protected text.

Only independently written material for which Deutschly's maintainer(s)
hold the rights may be given a separate open content license. Any text,
examples, tables, or other material copied or adapted from a source must be
reviewed under that source's terms. These files are not covered by the root
MIT License.

## 5. Wiktionary and WiktApi

Deutschly's live dictionary/pronunciation features query WiktApi and/or
Wiktionary. Wiktionary text is generally available under the Creative Commons
Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0) and the GNU
Free Documentation License (GFDL), subject to page-specific exceptions and
third-party material notices. Reuse of Wiktionary text must follow the
applicable license, including attribution, a link to the license, indication
of changes, and ShareAlike requirements where applicable.

- Wiktionary copyright/licensing: https://en.wiktionary.org/wiki/Wiktionary:Copyrights
- CC BY-SA 4.0: https://creativecommons.org/licenses/by-sa/4.0/
- WiktApi documentation: https://wiktapi.dev/quickstart

Do not assume every item returned by WiktApi has identical rights: check the
underlying entry and any third-party notices when redistributing content.

## 6. Audio recordings

The vocabulary database currently contains a reference to a Wiktionary /
Wikimedia Commons audio file for “Keks”. The recording itself is not stored
in this repository, but is linked externally. Wikimedia Commons files have
individual licenses; verify the exact file-description page and include the
required creator, source, license, and modification information if the file
is redistributed or embedded in a way requiring attribution.

## 7. External reference sites

Duden, PONS, Goethe-Institut, IDS grammis, and other dictionary or learning
sites are cited as references for checking facts. A reference link is not a
license to copy their definitions, examples, explanations, images, or other
protected content. Keep Deutschly's explanations independently written and
use only material that may lawfully be reused.

## 8. Before assigning an open content license

Do not apply MIT or another blanket license to the entire `data/` directory
until the provenance and rights for each dataset have been checked. If the
rights holder grants permission, record the permission and exact license here.
If a dataset is independently created by Deutschly and all relevant rights
are controlled by the maintainers, choose and state a suitable content
license separately (for example, CC BY 4.0 or CC BY-SA 4.0); do not assume
the software MIT License automatically applies to it.

If you believe any item is incorrectly attributed or should be removed,
please open an issue with the relevant file path and source details.
