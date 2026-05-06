# SOP: PowerPoint Deck → LinkedIn Carousel

*Template by Ashley Pyle, GadellNet · [linkedin.com/in/ashleypyle](https://linkedin.com/in/ashleypyle) · adapt freely for your brand.*

**Owner:** [Your name / role]
**Company:** [Your company]
**Last updated:** [YYYY-MM-DD]
**Reference:** Brand standards live in `01_Brand-Standards-Template.md`. Anything in `[BRACKETS]` below should be replaced with your own values.

---

## 1. When to Use This SOP

Use it when turning **existing source material** (a deck, a talk, a webinar) into a LinkedIn carousel.

**Do not use** for:
- Building a deck from scratch with no source.
- Other social platforms (Instagram square, Twitter, TikTok).
- Square 1080×1080 posts.
- Single-image LinkedIn posts.

---

## 2. Locked Format

| Item | Value |
|---|---|
| Aspect ratio | 1080 × 1350 portrait |
| Slide count | Up to 10 (LinkedIn cap) |
| Backgrounds | `[DARK]`, `[LIGHT]`, `[CTA]` only — see brand standards |
| Edge treatment | 1.5pt `[TINT]` stroke on every card and image |
| Typography | `[FONT]`, mobile-first floors |
| Final CTA | Always slide 10 — locked (see brand standards §6) |

---

## 3. The 10-Slide Arc

Compress or merge as needed, but **never skip hook, transformation, constraint, or CTA**.

| # | Role | Background |
|---|---|---|
| 1 | Hook — big visual + bold statement | DARK |
| 2 | Reframe — one contrarian idea | LIGHT |
| 3 | What we did/built — card grid (≤4 cards) | LIGHT or DARK |
| 4 | Mental model — 3 tiers | DARK or LIGHT |
| 5 | Transformation — "X disappears / Y remains" | LIGHT or DARK |
| 6 | What ships in the box / how it works | LIGHT |
| 7 | The hard part / honest constraint | DARK |
| 8 | Try this — Action 1 (tactical / immediate win) | LIGHT |
| 9 | Try this — Action 2 (stretch / strategic) | LIGHT |
| 10 | CTA — locked (see brand standards) | CTA |

> **Why this arc works:** hook earns the swipe; reframe and mental model give the reader a way to think; transformation makes the change concrete; constraint earns trust; the two prompts hand them something they can do; CTA converts.

---

## 4. The Process (Step by Step)

### Step 1 — Ingest the source deck

- Run the source PPTX through a markdown extractor to pull the text.
- Generate slide thumbnails so you can see the source visually.

### Step 2 — Run the source-deck preflight (BLOCKING)

Use `03_Source-Deck-Preflight-Template.md`. Extract every fact you might use in the carousel — and **verify it traces to the source**. Never invent a stat, quote, or name.

If a category in the preflight is empty, decide: drop the corresponding slide, or fill the gap with the user's confirmation.

### Step 3 — Audit for the carousel arc

Map source slides onto the 10-slide arc.

- **< 10 source slides:** Expand. Split the mental model into before/after; promote a card into its own slide; turn a stat into a hero number. Don't pad with filler.
- **= 10 source slides:** Map 1:1 where it works; reorder if needed.
- **> 10 source slides:** Compress in this order:
  1. Merge intro + agenda → hook.
  2. Collapse multi-slide examples into one card grid.
  3. Cut "thank you" / Q&A / appendix slides.
  4. Merge sub-points into bullets within an existing slide.
  5. Cut anything that doesn't earn its swipe.

If you can't compress to 10 without losing the argument, recommend a multi-post series instead.

### Step 4 — Cold-reader test (BLOCKING)

For each slide, simulate a stranger scrolling past with zero context:

- Would they get the point in 3 seconds?
- Does the slide assume context only the author has?
- Does the closing line apply to the **reader**, not the author?

If a closer is author-only, rewrite to address the reader.

### Step 5 — Pre-crop photos

Most deck-builder libraries have unreliable cover-sizing — pre-crop every photo to the exact box ratio before placing it. For headshots: square crop, then circular mask to a transparent PNG. (Sample Python/PIL helpers below if useful.)

```python
from PIL import Image, ImageDraw

def center_crop(src, dst, target_ratio):
    img = Image.open(src)
    w, h = img.size
    cur = w / h
    if cur > target_ratio:
        new_w = int(h * target_ratio); left = (w - new_w) // 2
        img = img.crop((left, 0, left + new_w, h))
    else:
        new_h = int(w / target_ratio); top = (h - new_h) // 2
        img = img.crop((0, top, w, top + new_h))
    img.save(dst, quality=92)

def circle_mask(src, dst, size):
    img = Image.open(src).convert("RGBA").resize((size, size))
    mask = Image.new("L", (size, size), 0)
    ImageDraw.Draw(mask).ellipse((0, 0, size, size), fill=255)
    img.putalpha(mask)
    img.save(dst)
```

### Step 6 — Build the deck

Use your locked brand template (or the helper functions in `references/template.js` if you build with `pptxgenjs`). Apply:
- The edge-treatment helpers to every card and image.
- The locked palette only.
- The font hierarchy from your brand standards (calibrated up to match the source).

### Step 7 — Density and accessibility caps (BLOCKING)

| Slide type | Max body chars | Notes |
|---|---|---|
| Hero | 200 (excl. headline) | |
| Card grid | 120 total + 50/card | Max 4 cards |
| Transformation tile | 100 | "X / Y" |
| Prompt slide | Quote ≤ 240 chars | One prompt per slide |
| Mental model | 60 chars/tier | Max 3 tiers |

**If over the cap, cut copy. Never shrink the font.**

WCAG: validate every text/background pairing for contrast (4.5:1 body, 3:1 large). Add alt text to every image. No color-only meaning.

### Step 8 — Build, QA, deliver

1. Build the deck (e.g., `node create-carousel.js`).
2. Convert to PDF (e.g., `soffice --headless --convert-to pdf`).
3. Slice the PDF to JPGs for visual review (e.g., `pdftoppm -jpeg -r 150`).
4. Run the QA checklist (`04_QA-Checklist-Template.md`).

### Step 9 — Write the LinkedIn post copy

A carousel without post copy is half-finished. Use `05_Post-Copy-Template.md` to produce:
- Hook (first ~140 chars — everything above the "see more" fold)
- Body (200–1300 chars total, 3–6 short paragraphs)
- Comment-bait closer (one specific, easy-to-answer question)
- Hashtags (3–5 max, brand-led, never generic)

### Step 10 — Deliver three artifacts

To `output/`:

1. The **PDF** (what you upload to LinkedIn — carousels go up as multi-page PDFs).
2. The **PPTX** (for future edits).
3. The **post-copy.md** (hook + body + comment-bait + hashtags).

Filename convention: `<TopicSlug>_LinkedIn_Carousel.<ext>`. Use the same slug for both files.

---

## 5. Slide Patterns (quick reference)

### Card grid (slides 3, 6)
- Max 4 cards (2×2). Never 6+ tiles.
- Edge-frame on every card.
- Optional 0.08" CTA-color top stripe inside the card.
- Card title 22pt DARK bold, body 16pt INK.
- Closer line 22pt CTA bold below the grid.

### Transformation tile (slide 5)
- Two columns: left "[CATEGORY] DOES" (light card, MUTED header bar); right "WE DO" (dark card, ACCENT-1 header bar).
- 4 short verbs per side, 26pt bold.
- Closer beneath: 24pt CTA bold.

### Mental model (slide 4)
- Three stacked light cards, each with a colored left rail (ACCENT-1 / CTA / DARK).
- Label 22pt DARK bold + sub-label 12pt accent + description 16pt INK (max 60 chars).

### Prompt/action slides (8 + 9)
**Differentiate by ask, not visual.**
- Both: light card with edge-frame, DARK header bar with TINT label "PROMPT 0X · <NAME>".
- Slide 8 = warm-up / tactical → immediate visible win.
- Slide 9 = stretch / strategic → meta-insight.
- Prompt text 26pt DARK bold inside curly quotes. Insight line below in 22pt CTA bold.

### Photo slides (1, 7)
- Pre-crop photos to the box ratio.
- Edge-frame on every photo.
- Headshots circle-cropped.
- Caption 11–12pt italic.

---

## 6. Anti-patterns (BLOCKING)

- **No accent lines under titles.** Decorative horizontal lines under titles are a known AI tell. Use whitespace, color contrast, or a small colored block (eyebrow accent) instead.
- **No footers** on every slide (no author byline, no page numbers). Branding lives in the logo (slide 1) and the byline (slide 10).
- **No emojis in the LinkedIn post's first line.** They eat character budget and read as desperate.
- **No "🔥 thread 🔥" / "Let me explain ↓" tells.**
- **No links in the post body.** LinkedIn deprioritizes them. Put the link in the first comment.
- **No invented facts.** Every number, quote, name, and photo credit traces to the source.
- **Never lower contrast for design.** If a pairing fails WCAG, swap to a passing one.

---

## 7. Reference Build

Once you've shipped your first carousel, save it as a reference build for future ones. Mirror its structure when in doubt.

- **Reference build:** `[file path / link to your first locked carousel]`
