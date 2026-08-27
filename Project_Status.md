---
tier: Pounce
phase: concept-built
next_action: "2026-08-27, later same session: after promoting the editorial build to src/index.html (see design concept history below), user asked to swap the filenames back — src/bauhaus.html renamed to src/index.html (restoring v3 as the live build) and the former src/index.html (v4 editorial) renamed to src/minimal.html. Plain file renames, no content changes; both files' internal <title> tags already read identically ('Umme Jannath Tamanna — Product Designer') so nothing needed touching there. v3 (Bauhaus) is live again. v4 (editorial) is preserved and browsable at src/minimal.html but is no longer the default. Reason for the reversal wasn't stated — worth asking next session whether this is a final call or still mid-comparison. Still no git commits in this project, so all version history continues to live only in these differently-named sibling files, not commits. Two other untracked exploration files (src/futuristic.html, src/sidebar.html) also exist from earlier sessions and still aren't folded into this Project_Status.md history."
plan_approved: false
spec_approved: false
---

# tamanna-portfolio-redesign

A from-scratch visual redesign of the live portfolio
(`ummejannath.github.io/Tamanna`) for a Product/UX-UI Designer (Brac IT
Ltd, Dhaka, Bangladesh — fintech, enterprise, e-commerce and wellness
product work). Single self-contained HTML/CSS/JS page, no build step, no
dependencies. All copy, project links, and images pulled directly from the
live site.

## Design concept

**v4 ("editorial monochrome", built and browsable, not currently live):**
Modeled on an external reference portfolio (sahor.work, found via
wallofportfolios.in) at the user's request, keeping every real content
item, image, and link from v3 unchanged. Black/white system (no
blue/mustard/red) built from Instrument Serif italic (script display) +
Bricolage Grotesque (bold display) + Inter (body) — confirmed via the
reference site's own computed styles, not guessed. Signature moves:
layered outline-script-behind-bold-solid headings (e.g. "Selected"
outlined behind "Works" solid), a hairline 5-column grid-guide overlay, a
`mix-blend-mode:difference` header that auto-inverts over both light and
dark sections, a scroll-driven circle-mask transition between the light
Work section and the dark Skills section, a pinned horizontal-scroll
"Design Toolkit" skills gallery, and grayscale-to-color hover on work
thumbnails. An Experience timeline section was added (monochrome hairline
rows, not in the reference) since v3's timeline data had no equivalent
section to land in otherwise. `prefers-reduced-motion` fully disables the
circle-mask and scroll-jack mechanics, falling back to normal stacked
layout. Built as `src/index-editorial.html`, compared side-by-side
against v3 in a published artifact, approved and briefly promoted to
`src/index.html`, then demoted back to a sibling file — now at
`src/minimal.html`.

**v3 (current, live at `src/index.html`):** Modern minimal, mixed with Bauhaus accents. User
rejected v2 Swiss too ("noo... please make a modern minimal design mix
bauhaus") — third direction change, no preview question this time since
the ask was specific enough to execute directly. White/near-white base,
near-black ink, restrained spacing-led "minimal portfolio" layout
(generous whitespace, rounded 20-28px cards, soft shadows on hover only)
as the foundation, with Bauhaus expressed narrowly: a primary-color trio
(cobalt blue `#2A4CDB` / mustard `#F6B93B` / red `#E5484D`, blue
dominant) and a circle/square/triangle shape system used as section
markers, list bullets, skill badges, and work-card corner badges — never
as full color-block backgrounds, which would tip it into literal Bauhaus
rather than "minimal mixed with Bauhaus." Space Grotesk for headings,
Manrope for body. Hero has a single decorative shape cluster
(circle-in-circle + rotated square + small triangle) instead of a dense
grid system. Work and Experience returned to card/timeline layouts
(dropped v2's index-row table treatment — didn't fit the airier goal).
Contact is a dark inset panel instead of a full-bleed dark section.

**v2 (superseded):** Swiss / International Typographic Style — light
paper bg, single red accent, Archivo throughout, numbered index-row
tables for Work/Experience, grayscale-to-color thumbnails.

**v1 (superseded):** "Nakshi Kantha" — Bengali running-stitch embroidery
motif, warm near-black base, terracotta/mustard/indigo accents, Fraunces
+ Work Sans.

v1 and v2 exist only in git history (none exists for this project yet),
not recoverable as files. v3 and v4 are both preserved as full sibling
files instead — `src/index.html` (v3, live) and `src/minimal.html` (v4).

Also fixes every usability issue found in the original during review:
- Nav links didn't actually scroll to their section — rebuilt with plain
  anchors + `scroll-behavior: smooth` + `scroll-margin-top`, no
  `preventDefault` hijacking.
- Inconsistent per-project card backgrounds (random pastel gradients) —
  replaced with one consistent card/frame system (fixed aspect-ratio
  thumbnail, `object-fit: cover`) applied to all 8 projects.
- No real "Contact" destination — added direct mailto/tel/WhatsApp action
  cards instead of just footer text.
- Work cards linked inconsistently (some real, some dead `#` links) — kept
  every real link found (Play Store, live sites, Dribbble shots) and
  marked the ones with no real destination as non-interactive instead of
  a fake/dead link.
- No visible focus states, no working mobile menu — both added.

## Where things are

- `src/index.html` — the live build (v3, modern minimal + Bauhaus),
  single file, open directly in a browser or serve via `python3 -m
  http.server` (file:// URLs don't work with the Chrome extension used
  for verification).
- `src/minimal.html` — v4 (editorial monochrome), fully built and
  verified, kept as a sibling file rather than the live one.
- `src/futuristic.html`, `src/sidebar.html` — earlier untracked
  exploration files, not folded into this status doc's history.
- `src/assets/` — all images (portrait + 8 project screenshots + about
  photo + avatar illustration), downloaded from the live site or
  supplied directly by the user.

## Status

v3 (modern minimal + Bauhaus) is live in `src/index.html` again as of
2026-08-27 (was briefly swapped out for v4, then swapped back same
session). v4 (editorial monochrome) is fully built, verified end-to-end
in Chrome, and browsable at `src/minimal.html`, but is not the current
default. Neither version is approved for deployment to the live GitHub
Pages site yet.
