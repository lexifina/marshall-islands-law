# Marshall Islands: law history in git

The law of Marshall Islands as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change; picking a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

**What is in it now (a first build, not complete)**

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `treaties/` | Treaty actions of Marshall Islands recorded by WIPO Lex (name, administering organisation, dates; no treaty text) | one per action date | From the earliest recorded action to the latest |
| `catalogue/` | Catalogue of laws of Marshall Islands recorded by WIPO Lex (title, subject, date, link; no law text) | one per recorded date | Dated by the date WIPO Lex records for each law |
| `legal-system/` | Legal system of Marshall Islands: constitution, legislature, courts, official languages (Wikidata, WIPO Lex) | 1 | Oldest version available, 30 October 2026 |

**Language.** English. This repository holds metadata only.

**Source.** Metadata only, no law text, because the Nitijela's own rights statement requires permission for reuse of its legislation, so no legal text is published here (licence-held). Treaty actions, the list of laws and the constitution date come from the WIPO Lex member profile (https://www.wipo.int/wipolex/en/members/profile/MH); open facts on the legal system come from Wikidata (CC0). Both retrieved 30 October 2026.

## Dates

Each commit is dated at noon local time. A treaty is dated by the country's own action: its ratification, accession or similar instrument, else its entry into force for the country, else signature. A catalogue entry is dated by the date WIPO Lex records for the law (promulgation, entry into force, commencement or adoption); where WIPO Lex gives only 'January 1' of a year, that date is a placeholder, not a known date. A law with no recorded date is added on 30 October 2026, the retrieval date.

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; results are in `REPRODUCE.md`.

## What "author" means

The author of a commit is the law that made the change, with an e-mail address that cannot exist (`<law key>@wipo-int.invalid`). Each treaty action or catalogue date is credited to a key that names the record (treaty-<WIPO id>, catalogue-<date>); these are not laws. The committer is always Lexifina.

## Limits

Metadata only: the Constitution, the Revised Code and the treaties are named, not reproduced. The treaty list and the law list are what WIPO Lex records and omit anything it does not track. Law text resumes only after written permission for reuse.
