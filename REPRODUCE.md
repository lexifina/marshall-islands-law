# How this repository was made (Marshall Islands)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| WIPO Lex member profile | <https://www.wipo.int/wipolex/en/members/profile/MH> | 2026-10-30 | WIPO content: CC BY 4.0 (https://www.wipo.int/web/terms-of-use); only facts copied |
| Wikidata | <https://www.wikidata.org/> | 2026-10-30 | CC0 |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `treaties` | Treaty actions of Marshall Islands recorded by WIPO Lex (facts only; no treaty text) | 22 | 1988-03-18 to 2025-03-12 |
| `catalogue` | Catalogue of laws of Marshall Islands recorded by WIPO Lex (title, date, link only; no law text) | 5 | 1970-01-01 to 2026-10-30 |
| `legal-system` | Legal system of Marshall Islands: open facts (Wikidata, WIPO Lex) | 1 | 2026-10-30 to 2026-10-30 |

The build made 33 commits:

| Commits | Kind |
| ---: | --- |
| 3 | first version of an act |
| 30 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 32 laws in the record.
- 60 tags.

## Dates

Each commit is dated at noon (Pacific/Majuro) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: This repository holds metadata only, no law text. Each treaty is dated by the party's own action (ratification, accession or similar instrument; failing that its entry into force for the party, then signature); each catalogue entry by the date WIPO Lex records for the law. https://www.wipo.int/wipolex/en/members/profile/MH

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `abb88d9a7f5251edc72cd43b24c766888b68416e66a564eae7c4af09444d01cf` (47071 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Metadata only, no law text: the Nitijela's site states rights that need permission for reuse, so no legal text is published here.
- Treaty versions are dated by the party's instrument date (ratification, accession or similar), else its entry-into-force date for the party, else signature; treaties with none of these are left out.
- Catalogue entries use the date WIPO Lex records (promulgation, entry into force, commencement or adoption, in that order); WIPO Lex gives some laws only "January 1" of a year, which is a placeholder, not a known date; a law with no date is added on the retrieval date.
- No treaty or law text is included: titles, dates, administering organisation and links only.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none
