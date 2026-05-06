# Brand Standards — LinkedIn Carousel

*Template by Ashley Pyle, GadellNet · [linkedin.com/in/ashleypyle](https://linkedin.com/in/ashleypyle) · adapt freely for your brand.*

> **Fill this out once for your company.** Every carousel will reference these rules. Lock the choices — consistency across posts is what makes a carousel feel branded.

---

## 1. Approved Background Colors

Pick **exactly three**. More than three and the deck loses its visual identity. Typical pattern: one dark, one light, one CTA accent.

| Hex | Name | Use |
|---|---|---|
| `#[DARK]` | **[DARK NAME]** | Dark slides — hook, constraint, key emotional beats |
| `#[LIGHT]` | **[LIGHT NAME]** | Light slides — content, card grids, prompts |
| `#[CTA]` | **[CTA NAME]** | CTA slide only (typically slide 10) |

**Default rotation across 10 slides:**
[DARK] → [LIGHT] → [DARK] → [DARK] → [DARK] → [LIGHT] → [LIGHT] → [LIGHT] → [LIGHT] → [CTA]

Adjust to topic, but stick to these three colors.

---

## 2. Accent Palette (foreground only — never as backgrounds)

Add the supporting colors used for type, accents, edges, and de-emphasized text. Keep this list short.

| Hex | Name | Use |
|---|---|---|
| `#[ACCENT-1]` | **[NAME]** | Mid-accent on dark backgrounds |
| `#[EDGE-COLOR]` | **TINT** | Edge-frame color + soft accents |
| `#[PALE]` | **PALE** | Very pale fill / hover-card |
| `#[INK]` | **INK** | Body text on light backgrounds |
| `#[MUTED]` | **MUTED** | De-emphasized text |

---

## 3. The Edge Treatment ("Soft-Tint Frame")

This is your **signature** — the visual cue that makes a carousel instantly recognizable as yours.

- Every card and every framed image gets a **[1.5pt] [TINT-COLOR]** stroke.
- Never use a hard black or grey stroke.
- Apply consistently to: card backgrounds, photos, photo frames.

---

## 4. Typography (mobile-first floors)

LinkedIn carousels are read at thumbnail size on phones. The numbers below are **floors**, not targets — calibrate up to match your source deck's hierarchy.

**Type family:** [FONT NAME] (e.g., Poppins, Inter, Source Sans, Helvetica Neue)

| Element | Floor | Typical |
|---|---|---|
| Hero (slides 1, 5, 7 — biggest beat) | **56pt** | **80–105pt** |
| Section title | **44pt** | 56–68pt |
| Light-slide title | **36pt** | 44–60pt |
| Sub-line | 22pt | 24–28pt |
| Body | **14pt** | 18–22pt |
| Card title | 22pt bold | 24–28pt |
| Card body | **16pt** | 18–20pt |
| Takeaway / closer | **22pt** bold [CTA color] | 24–28pt |
| Eyebrow | 14pt bold (charSpacing 6) | 14–16pt |

**Rule:** match the source deck's hierarchy. If the source uses 92pt heroes, the carousel hero should too. Defaulting to the floor produces a deck that feels timid.

---

## 5. Logo Rules

| Rule | Spec |
|---|---|
| Where it appears | Slide 1 only (top-right, inside the safe zone) |
| Position | `x = W - 2.0", y = 0.4"` |
| Size | `w = 1.3", h = 0.48"` (preserve aspect ratio) |
| Variants | White-on-dark logo on dark/CTA backgrounds; full-color on white |
| Alt text | `"[Your Company] logo"` |
| Fallback | If logo asset unavailable, leave the position empty — never substitute a typeset wordmark |

The logo does **not** repeat on every slide. The footer does the work everywhere else.

---

## 6. The Locked CTA (slide 10)

> **Pick one CTA. Use it across every carousel.** Inventing a new CTA per topic dilutes the funnel.

**Required elements (in this order):**

1. **Eyebrow** — `[ONE ASK]` or similar (16pt TINT, charSpacing 6)
2. **Three-line hero** — *e.g., "Save this. / Try the prompts. / Tell me what shipped."* (56pt WHITE bold)
3. **Author byline** — `I'm [Author Name], [Author Role].` (22pt WHITE bold) + one-line credibility (18pt TINT)
4. **CTA action block** — left side, white card containing your conversion mechanism:
   - [QR code / link / scan / sign-up — whatever yours is]
   - SCAN/SIGN UP/etc. label (11pt TINT, centered)
   - "[CTA headline — what's the offer?]" (15pt WHITE bold, centered)
   - "[Free assessment · yourcompany.com]" (11pt TINT italic, centered)
5. **Three actions** — stacked to the right of the CTA card:
   - SAVE — this carousel for your team
   - COMMENT — with [a question tied to the carousel content]
   - FOLLOW — for more [your content category]
6. **Logo** — top-right, white-on-dark variant (same position as slide 1)

**Asset requirement:** if the CTA depends on a static asset (QR code, sign-up image), specify the file path here so it's reused every time:
- Asset path: `[input/YOUR_CTA_ASSET.png]`

---

## 7. Accessibility (WCAG 2.1 AA — non-negotiable)

LinkedIn carousels are public content. Lock the rules below — they apply to every carousel.

1. **Contrast:** body text ≥ 4.5:1, large text (18pt+ regular / 14pt+ bold) ≥ 3:1.
   - Pre-validate every locked palette pairing once. Then never combine outside them.
   - Approved pairings:
     - LIGHT BG: text in [DARK], INK, or [CTA color]
     - DARK BG: text in WHITE, TINT, or [ACCENT-1]
     - CTA BG: text in WHITE only
2. **Font floors:** body ≥ 14pt, captions ≥ 11pt.
3. **Alt text on every image.** Decorative images use `alt=""`.
4. **No color-only meaning.** If a comparison relies on color, also add an icon, label, or position cue.
5. **Reading order:** top→bottom, left→right. Z-order matters for screen readers.
6. **CTA mechanism (QR or similar) ≥ 1.8" square** at 1080×1350.
7. **Plain language** — Flesch reading ease 60+ (8th grade or below) on body copy.

---

## 8. Voice & Tone (optional override)

This document governs format, brand, and accessibility — not voice. If you have a separate voice/tone guide, point to it here:

- **Voice & tone reference:** `[link or file path]`
- **Default if no voice guide:** confident, plainspoken, short sentences, no jargon, no AI tells.

---

## 9. Filename Convention

Consistent naming makes posts easier to find later and looks professional in the upload UI.

**Pattern:** `<TopicSlug>_LinkedIn_Carousel.<ext>`
- `TopicSlug` is PascalCase, no spaces, no dates (e.g., `Cowork_30Days`, `MicrosoftCommunityDay`)
- Always `_LinkedIn_Carousel` suffix
- `.pptx` and `.pdf` use the same slug

**PDF metadata** — set on the deck before exporting:
- Author: `[Default Author Name]`
- Company: `[Your Company]`
- Title: `[Human-readable post title]`
- Subject: `LinkedIn Carousel`

---

## 10. Lock-it-in Checklist

Before adopting these standards, confirm:

- [ ] Three background colors picked and locked
- [ ] Edge-frame (TINT) color picked and locked
- [ ] Type family picked; floors match mobile readability
- [ ] Logo variants (light/dark) available as image assets
- [ ] Locked CTA elements decided and asset path documented
- [ ] WCAG pairings pre-validated
- [ ] Filename + metadata convention agreed on
