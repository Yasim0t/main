# Digital edition — EPUB line

This directory defines the digital-publication branch of **F8.0 — Platform**.

## Decision

The preferred ebook format is a **reflowable EPUB** rather than a fixed-layout copy of the A5 print edition.

Production target for the first stable release: **EPUB 3.3**, the current W3C Recommendation line. EPUB 3.4 is monitored as the next-generation specification but remains on the Candidate Recommendation track as of 28 October 2026.

Official references:
- https://www.w3.org/TR/epub-33/
- https://www.w3.org/TR/epub-a11y-11/
- https://www.w3.org/TR/epub-34/
- https://github.com/w3c/epubcheck

## Why the digital line is separate

The A5 branch is typography for paper. It contains physical page geometry, recto/verso logic, fixed drop-cap slots, page numbers and image-flow decisions.

The EPUB branch instead preserves:
- semantic chapter structure;
- reflowable prose;
- user-selectable type size and reading-system pagination;
- language metadata;
- accessible navigation;
- image resources independent of print-page coordinates;
- no dependency on A5 page numbers;
- no narrow-column V60 construction inherited from print.

## RC1 builds prepared — 28 October 2026

Nine private release-candidate binaries now exist:

RU · EN · UK · ES · FR · DE · IT · JA · ZH

Naming pattern: `Platform_<LANG>_EPUB3.3_RC1.epub`.

They are **release candidates, not public binary releases yet**. The working RC1 package is retained in the private production archive while the public GitHub repository keeps the source texts, visual assets and digital specification.

### Completed internal QA

All nine candidates have been checked for:
- valid ZIP/container structure;
- uncompressed first `mimetype` entry with `application/epub+zip`;
- resolvable `META-INF/container.xml`;
- EPUB 3 package metadata and navigation;
- presence of every manifest resource;
- chapter ordering;
- source-to-EPUB beginning/end text anchors;
- no dependency on the A5 V60 table/column construction.

The multilingual A5 V60 defect therefore does **not** propagate into the EPUB line.

## Source of truth

Text sources:
- Russian: RU-TEXT 1.0.2 / RU-PUB RC3 textual content, with print-only structures flattened into reading order.
- EN / UK / ES / FR / DE / IT / JA / ZH: public locked TEXT 1.0 files under `../translations/`.

Print-layout PDFs are **not** ebook source files.

## Remaining gate before public .epub release

A generated EPUB is not considered released merely because its container is structurally sound.

Still required:
1. official EPUBCheck pass;
2. at least two independent reading systems;
3. small/large-font reflow and navigation checks;
4. accessibility metadata and meaningful-image alternative-text review;
5. final cover policy for every language;
6. final human spot-read against the locked TEXT source.

Status: **EPUB 3.3 RC1 prepared; public binary release pending external/device QA**.
