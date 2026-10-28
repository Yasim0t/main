# Digital edition — EPUB line

This directory defines the digital-publication branch of **F8.0 — Platform**.

## Decision

The preferred ebook format is a **reflowable EPUB** rather than a fixed-layout copy of the A5 print edition.

Production target for the first stable release: **EPUB 3.3**. EPUB 3.4 is monitored as the next-generation specification but remains a Candidate Recommendation as of 28 October 2026.

Official references:
- https://www.w3.org/TR/epub-33/
- https://www.w3.org/TR/epub-a11y-11/
- https://www.w3.org/TR/epub-34/

## Why the digital line is separate

The A5 branch is typography for paper. It contains physical page geometry, recto/verso logic, fixed drop-cap slots, page numbers and image-flow decisions.

The EPUB branch must instead preserve:
- semantic chapter structure;
- reflowable prose;
- user-selectable type size and reading-system pagination;
- language metadata;
- accessible navigation;
- alt text / descriptions for narrative images;
- CSS drop caps that degrade gracefully;
- no dependency on A5 page numbers;
- no narrow-column V60 construction inherited from print.

## Proposed package

Each language edition should contain:
1. title and rights metadata;
2. the four chapters as semantic XHTML sections;
3. navigation / table of contents;
4. common narrative figures `fig01`–`fig06`;
5. localized chapter art where approved;
6. accessible text alternatives for meaningful images;
7. lightweight CSS;
8. no private production notes, Drive links or QA internals.

## Source of truth

Text sources:
- Russian: public RU-TEXT / AI-readable source.
- EN / UK / ES / FR / DE / IT / JA / ZH: public locked TEXT 1.0 files under `../translations/`.

Print-layout PDFs are **not** ebook source files.

## Gate before publishing .epub

A generated EPUB is not considered a release merely because it opens.

Required checks:
- EPUB validation;
- navigation and metadata;
- chapter order;
- image presence and alt text;
- reflow at small/large font sizes;
- dark/light reading themes where supported;
- at least two independent reading systems;
- spot-check against the locked TEXT source;
- accessibility metadata.

Status: **digital specification v0.1 — no EPUB release yet**.
