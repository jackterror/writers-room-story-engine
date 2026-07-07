# CAP AND CUT – DESIGN.md

The visual system for Cap and Cut brand assets across the public skill library and related surfaces – social preview cards, repo graphics, deck-adjacent one-offs. This is the execution spec: anyone (human or agent) should be able to produce an on-brand asset from this document alone, with zero taste decisions left open.

Reference implementations: the four repo social preview cards (persuasion-audit-engine, writers-room-story-engine, social-demand-signal-agent, script-to-video-production-agent), July 2026.

---

## 1. Brand foundations

Cap and Cut is a trailer house and creative design studio. The visual world is the edit bay – timelines, playheads, frame registration, slates. Assets should feel like they came out of a cutting room, not a SaaS template.

Two domains anchor everything, always together:

- **jackdalrymple.com** – the person. Creator link, About-panel website field.
- **capandcut.com** – the studio. Creator block, studio attribution.

The studio name is written **Cap and Cut** – never "Cap & Cut", never "Cap&Cut". The ampersand does not exist in this brand's name (the logo lockup styles it CAP and CUT). In all-caps contexts: CAP AND CUT.

Voice on assets: confident, declarative, zero filler. Say what the thing does. No exclamation points, no "supercharge," no gradient-brain adjectives.

## 2. Color tokens

| Token | Hex | RGB | Role |
|---|---|---|---|
| `ink` | #111420 | 17, 20, 28 | Primary background – deep slate, not pure black |
| `panel` | #171B25 | 23, 27, 37 | Secondary surfaces, cards-on-cards |
| `paper` | #F0EDE4 | 240, 237, 228 | Primary text – warm off-white, never #FFFFFF |
| `mute` | #969BA8 | 150, 155, 168 | Secondary text, captions, metadata |
| `line` | #3A404E | 58, 64, 78 | Rules, inactive timeline, tick marks |
| `yellow` | #FFD600 | 255, 214, 0 | THE highlight. One accent, everywhere |

Rules of the palette:

- **Yellow is the only accent.** No per-project accent colors, no secondary accent. If something needs emphasis, it gets yellow or it gets nothing.
- Yellow is used sparingly and precisely – eyebrow tag, the signature rule, separator dot. It should occupy well under 5% of any composition. Scarcity is what makes it read.
- Never place yellow text on paper, or paper text on yellow at small sizes. Yellow lives on ink.
- `paper` on `ink` is the body pairing. `mute` on `ink` for anything the eye can arrive at second.

> #FFD600 is the confirmed canonical yellow – used in presentations and on capandcut.com. Locked July 2026.

## 3. Typography

The brand typeface is **Inter** – one family, every role, differentiated by weight. Use the variable font (Inter[opsz,wght], available via Google Fonts or rsms/inter) so weights render true.

| Role | Weight | Case & treatment |
|---|---|---|
| Display | Inter ExtraBold (800), optical size 32 | ALL CAPS, tight leading (~1.12), left-aligned |
| Body | Inter Regular (400) | Sentence case, generous leading |
| Utility / footer | Inter Medium (500) | lowercase for URLs and metadata |
| Eyebrow | Inter Bold (700) | ALL CAPS with wide letter-spacing (+6 to +8px at 22pt) |

Display type is the personality carrier – big, heavy, unapologetic, like a title card. Never center-align. Never use more than two lines of display type. No second typeface, ever – hierarchy comes from weight and size, not from mixing families.

## 4. The signature: the yellow rule

Every Cap and Cut asset carries the brand's signature element – a solid, full-width horizontal rule in yellow. Provenance: the Jack Dalrymple LinkedIn banner, where paired yellow rules frame the identity block. It reads as a cut line – clean, decisive, edit-bay.

Construction:

- Full-width rule in `yellow`, 5px weight, running margin to margin (110px insets on the 1280 canvas)
- Always solid, always one color – never segmented, gradiented, or two-toned
- May appear once (above the footer) or paired (framing a content block, per the banner)

Secondary motif: frame-registration corner ticks in `line` (26px arms, 3px weight, 56px inset) at all four corners. Quiet, optional on small formats, always on 1280×640 cards.

## 5. Social preview card spec (1280 × 640)

GitHub/OG standard. Layout grid, top to bottom, all measurements from canvas edges:

1. **Corner ticks** – four corners, per §4
2. **Eyebrow** – y≈118, x=110: `AGENTIC SYSTEM` in yellow, `//  CAP AND CUT` in mute, both tracked caps. AGENTIC SYSTEM is the positioning label – it matches the package language (agentic pipelines, AI & systems projects) and claims systems-level altitude. The spec term "Agent Skill" lives only where precision is functional: README install sections and GitHub topics. Never label the brand surface with the commodity noun "skill"
3. **Title** – starts y≈186, x=106: two lines max, display caps in paper, 84pt (drop to 72pt if any line exceeds ~1000px)
4. **Subtitle** – one to two lines in mute, 30pt, max width 980px. Formula: what it does – grounded in what. Use a spaced en dash, never an em dash
5. **Yellow rule** – y = H−128, x 110 → W−110, solid 5px per §4
6. **Footer** – y = H−88, mono 22pt: `jackdalrymple.com` (paper), yellow dot with symmetric 20px padding both sides, `capandcut.com` (paper), right-aligned `github.com/jackterror` (mute)

Export: PNG, exactly 1280×640. Upload via repo → Settings → Social preview.

## 6. Copy rules on assets

- Spaced en dashes ( – ) only. The em dash does not exist in this brand.
- Titles are the repo name in Title Case, split at the natural noun break (PERSUASION / AUDIT ENGINE).
- Subtitles are one sentence, verb-first, naming the frameworks or mechanism – credibility through specificity, not adjectives.
- URLs always lowercase, always bare (no https:// on display).

## 7. Extending the system

New formats (banners, deck covers, thumbnails) inherit in this order: ink background → paper display type → one yellow signature element (the solid rule) → mono metadata footer with both domains. If a new format can't fit all four, cut from the bottom of the list, never the top.

What is off-brand, permanently: gradients, drop shadows, rounded-corner cards, more than one accent color, centered display type, pure black, pure white, stock imagery, and any composition where yellow exceeds a highlight role.

## 8. Regeneration

The card renderer lives as a Python/PIL script (`make_previews.py` pattern). To produce a new card: copy an existing repo entry in the `repos` list, set slug, two title lines, and subtitle, run. Any agent session given this document plus that script can extend the set with zero drift.

---

*Cap and Cut – jackdalrymple.com – capandcut.com*
