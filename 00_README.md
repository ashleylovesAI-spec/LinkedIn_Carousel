# PPT → LinkedIn Carousel — Template Pack

**Created by:** Ashley Pyle, Chief Experience Officer, GadellNet
**Email:** Ashley.Pyle@gadellnet.com
**LinkedIn:** [linkedin.com/in/ashleypyle](https://linkedin.com/in/ashleypyle)

Hi! I put this together to share a process we've validated for turning existing PowerPoint decks into high-performing LinkedIn carousels. It's been refined across multiple iterations — this pack hands you the same skeleton, with placeholders for your own brand and voice. Adapt freely.

## What's in this pack

| File | Purpose |
|---|---|
| `00_README_Start-Here.md` | This file — how to use the pack |
| `01_Brand-Standards-Template.md` | Fill in your colors, fonts, logo rules. **Do this first.** |
| `02_Carousel-SOP-Template.md` | The end-to-end process — generic version with `[BRACKETED]` placeholders |
| `03_Source-Deck-Preflight-Template.md` | Worksheet to extract facts from a source deck before drafting |
| `04_QA-Checklist-Template.md` | Final QA gate — format, content, accessibility, delivery |
| `05_Post-Copy-Template.md` | Template for the LinkedIn post that ships *with* the carousel |

## Recommended order

1. **Fill out `01_Brand-Standards-Template.md` once.** This becomes your single source of truth — every carousel references it. You'll need: backgrounds, accents, edge-treatment color, typography rules, logo rules, and (if you have one) a locked CTA.
2. **Adapt `02_Carousel-SOP-Template.md`** by replacing the `[BRACKETED]` placeholders with your brand specifics. Save it as your team's SOP.
3. **Use `03`, `04`, and `05` as living worksheets** — copy them into each project folder when you start a new carousel.

## A few principles that make this whole thing work

- **Only three approved background colors.** Lock them. Resist the urge to introduce more.
- **One signature edge treatment.** A soft-tint colored stroke on every card and image makes the carousel instantly recognizable as yours.
- **Mobile-first font floors.** LinkedIn carousels are read at thumbnail size on phones. If body copy is below ~14pt, it's invisible.
- **One locked CTA across every carousel.** Do not invent a new CTA per topic — pick one ask that ladders to your business goal and use it every time.
- **Density caps.** If a slide is over the cap, cut copy. Never shrink the font.
- **Cold-reader test.** Before publishing, read every slide as if you've never heard of the topic. Closers must apply to the *reader*, not the author.
- **Source traceability.** Every fact in the carousel traces back to the source deck. No invented stats.
- **Post copy is part of the deliverable.** A carousel without a post is half-finished.

## Format spec (LinkedIn-locked)

| Item | Value |
|---|---|
| Aspect ratio | 1080 × 1350 (portrait) |
| Slide count | Up to 10 (LinkedIn's cap) |
| Upload format | Multi-page PDF |

These are LinkedIn's own constraints, so they apply across brands.

## Tooling

The original implementation uses `pptxgenjs` (Node) to build the deck and LibreOffice to convert PPTX → PDF, then `pdftoppm` to slice the PDF for visual QA. Any deck builder works — what matters is the *process*, not the tool.

## Questions

If you want to talk through how we adapted slide 10 into a locked CTA, or how we handle photo credits and headshots, just reach out — happy to walk through it.

— Ashley Pyle · GadellNet · Ashley.Pyle@gadellnet.com · [linkedin.com/in/ashleypyle](https://linkedin.com/in/ashleypyle)
