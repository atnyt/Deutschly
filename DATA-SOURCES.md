# Deutschly data sources and licensing notes

Last reviewed: 2026-11-03

This document records authorship, license, and source-reference boundaries for the
repository. It is not legal advice. See [DATA-LICENSE.md](DATA-LICENSE.md) for
the CC BY 4.0 grant covering original Deutschly-authored data and its exclusions.

## 1. Original software

The standard MIT License in the root `LICENSE` file applies to original
software code authored by the Deutschly maintainer, to the extent the
maintainer holds the relevant rights. See [LICENSE-NOTICE.md](LICENSE-NOTICE.md).

## 2. A1 German–Bangla vocabulary database

File: `data/a1-vocabulary.json`

**Authorship clarification from the maintainer:** The Deutschly A1 database
is the maintainer's own work. The maintainer independently created and
curated the database records, Bengali meanings, German and Bengali examples,
grammatical annotations, corrections, review decisions, and JSON structure.
The “A1 Vocabulary list_Deutsch mit Shakil” PDF was suggested as a starting
reference/inspiration for vocabulary coverage and page-level comparison; it
was not the author of the Deutschly database and is not being claimed as its
licensor.

The database metadata records 1,715 reference-list rows compared with the
independently maintained database, 10 duplicate rows consolidated, and
8 vocabulary items recovered, resulting in 1,713 unique normalized
headwords. Per-record page references are retained for traceability to the
suggested reference, not as a claim that the PDF author created the Deutschly
entries.

The maintainer's independently authored contributions are licensed under CC BY 4.0 only to the extent the maintainer holds the relevant rights. The repository records 140 entries whose headword and English gloss/example fields are explicitly marked as transcribed from the suggested reference, plus seven Bengali fields marked source_transcribed. Those identified portions are excluded from the grant pending rights confirmation. The field-level register is in [data/a1-vocabulary-third-party-exclusions.json](data/a1-vocabulary-third-party-exclusions.json). The PDF itself is not included in this repository.

## 3. Vocabulary audit

File: `data/a1-vocabulary-audit.json`

This audit records the comparison against the suggested reference, duplicate
consolidation, coverage checks, and review status of the independently
maintained database. The audit does not claim that the reference PDF's author
created or owns the Deutschly database. Its independently written analysis
is the maintainer's work, subject to the same third-party-material caveat.

## 4. Grammar terminology and compound analysis

Files:
- `data/grammar-terms.json`
- `data/compound-analysis.json`

These files contain Deutschly-curated German–Bengali explanations, examples,
and analyses with references to IDS grammis, Goethe-Institut, Duden, and the
University of Michigan. The references are for fact-checking; they do not
mean those organizations endorse Deutschly or grant permission to reproduce
their protected text. The maintainer's independently written material may
be licensed by the maintainer, to the extent the relevant rights are owned.
Copied or adapted source material must be reviewed separately.

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
underlying entry and third-party notices when redistributing content.

## 6. Audio recordings

The vocabulary database currently links to a Wiktionary/Wikimedia Commons
audio file for “Keks”. The recording itself is not stored in this repository.
Wikimedia Commons files have individual licenses; verify the exact file
description page and include creator, source, license, and modification
information if the file is redistributed or embedded in a way requiring
attribution.

## 7. External reference sites

Duden, PONS, Goethe-Institut, IDS grammis, and other learning sites are cited
as references for checking facts. A reference link is not a license to copy
their definitions, examples, explanations, images, or other protected
content. Keep Deutschly's explanations independently written and use only
material that may lawfully be reused.

## 8. License boundaries

The root MIT License covers original software code only. Original Deutschly-authored data contributions are licensed under CC BY 4.0 only where the maintainer controls the relevant rights. The explicit field-level exclusions are recorded in `data/a1-vocabulary-third-party-exclusions.json`. A source citation is not reuse permission.

If any item is incorrectly attributed or should be removed, open an issue
with the relevant file path and source details.
