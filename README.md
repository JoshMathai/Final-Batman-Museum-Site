# The Gotham Archive

A digital museum exhibit dedicated to *Batman: The Animated Series* (1992–1995) — the show that redefined what a superhero cartoon could be. The site is built as a guided, seven-stage tour through the series' origin, art direction, philosophy, voice cast, rogues gallery, and lasting cultural legacy.

**Live exhibit routes**
1. `/` — Atrium (introduction & curator's thesis)
2. `/origin` — Exhibit I: Origin
3. `/noir-deco` — Exhibit II: Noir & Deco
4. `/philosophy` — Exhibit III: Philosophy (interactive)
5. `/voices` — Exhibit IV: The Voices
6. `/rogues` — Exhibit V: Hall of Rogues
7. `/legacy` — Exhibit VI: Legacy
8. `/curator` — Curator's Note

---

## Step 7 — Orchestration Process

I care about how this site was made, not just how it looks. The build followed a structured, multi-stage workflow rather than a single mega-prompt.

### 1. Breaking the work into parts

I decomposed the museum into independently shippable units before writing any code:

```
Topic research        →  thesis + outline
Information arch      →  7 exhibits, each a separate route
Design system         →  tokens, typography, components
Content per exhibit   →  prose, plaques, image plates
Interactive layer     →  Philosophy tab system
Polish + QA           →  navigation, metadata, image wiring
```

Each exhibit was built as its own route file (`src/routes/*.tsx`) so I could iterate on one section without breaking the others.

### 2. Researching the topic

Source material drawn on for the exhibits:
- Bruce Timm & Eric Radomski's published interviews on the "Dark Deco" pitch and the painted-on-black-paper technique.
- Paul Dini's writing on episodes like *Heart of Ice*, *Almost Got 'Im*, and *Mad Love*.
- Production history of Warner Bros. Animation 1990–1995 and the Fox Kids broadcast standards that shaped the show's restraint.
- The DCAU continuity that grew out of B:TAS (*Superman: TAS*, *Batman Beyond*, *Justice League*) and downstream influence on the *Arkham* games and Nolan films.

These sources fed the Plaques, the Philosophy theses, and the Legacy timeline.

### 3. Using AI in different stages

AI was used as a pair, not a ghostwriter — a different role at each stage:

| Stage | AI's role | My role |
|---|---|---|
| Concept | Brainstorm archetypes (Sage + Hero) and visual directions | Pick "Art Deco Editorial / Dark Deco" and reject generic options |
| Design system | Propose token names, oklch palette, typography pairings | Approve Cinzel + Cormorant Garamond, lock the gold/crimson/ink palette |
| Components | Scaffold `Exhibit.tsx` primitives (`Plaque`, `Prose`, `Figure`, `NextExhibit`) | Define the API so every exhibit feels consistent |
| Content | Draft prose for each exhibit from research notes | Edit for accuracy, tone, and Batman-fan credibility |
| Imagery | Generate noir/deco backdrop assets | Curate uploaded character photos and decide image placement |
| Interactivity | Implement the Philosophy tab state machine | Specify the five theses and their episode evidence |

### 4. Revising and improving AI output

Concrete revision passes the project went through:
- **First pass** produced a 6-route site. Review found the philosophy of the show was buried inside other exhibits → added a dedicated `/philosophy` route as Exhibit III and renumbered everything.
- **Image pass**: generic placeholder art was replaced with uploaded reference photos (Joker, Freeze, Two-Face, Harley, Mad Hatter, Clayface, the cast).
- **Interaction pass**: the Philosophy page was static prose. Reviewer feedback ("turn each theme into clickable takeaways") drove the rebuild into a five-tab interactive with episode evidence cards.
- **Navigation pass**: numbered the exhibits in `MuseumLayout.tsx` and added `NextExhibit` footers so the tour has a guided spine instead of being a pile of pages.

### 5. Design decisions

- **Archetypes:** Sage (curatorial authority) + Hero (Batman's mythic stance). Drives the formal, declarative voice.
- **Style:** "Dark Deco" — the production design term Timm and Radomski used for the show itself. Picking the subject's own aesthetic vocabulary keeps the exhibit honest.
- **Type:** Cinzel for display (engraved plaque feel), Cormorant Garamond for body (museum wall-text feel). Explicitly avoided Inter / Poppins to dodge generic AI defaults.
- **Color:** oklch tokens for gold, crimson, and ink defined in `src/styles.css`. No raw color classes in components.
- **Layout:** `.deco-frame` utility gives every plate the same gold-rule border, so the whole tour reads as one institution.

### 6. Evaluating quality

Quality checks applied throughout:
- **Build / typecheck** runs after every change set.
- **Route walk:** click through Atrium → Exhibit I → … → Curator's Note in order, looking for broken visual rhythm or dead links.
- **Image audit:** every `Figure` has a real caption and credit; no decorative-only images without alt text.
- **Token audit:** components use semantic tokens (`bg-background`, `text-foreground`, `border-primary/30`) — no hardcoded colors.
- **Tone audit:** prose stays in a curatorial register; no marketing-speak, no fan-wiki bullet dumps.
- **Persuasion check:** at least one Cialdini lever is explicit (see Step 8).

### 7. How the process improved the final site

The structured workflow produced specific, visible improvements over what a one-shot prompt would have made:
- Dedicated **Philosophy** exhibit (exists only because review surfaced the gap).
- **Interactive** thesis tabs with per-episode evidence (exists only because of a second revision pass).
- **Consistent** plaque/figure/prose components across seven routes (exists only because the design system was built before the content).
- **Real** character imagery instead of generic placeholders (exists only because of a deliberate asset pass).
- **Numbered, guided** tour (exists only because navigation was treated as its own pass).

---

## Step 8 — Required Museum Qualities

| Requirement | Where it lives in this project |
|---|---|
| **Clear topic** | *Batman: The Animated Series* and why it redefined the superhero — stated in the Atrium thesis. |
| **Strong homepage / introduction** | `src/routes/index.tsx` — Atrium with hero, curator's thesis, and exhibit grid. |
| **Guided route through the material** | Numbered Exhibits I–VI plus Curator's Note, wired with `NextExhibit` footers and a persistent numbered nav in `MuseumLayout.tsx`. |
| **Meaningful sections / exhibits** | Origin, Noir & Deco, Philosophy, The Voices, Hall of Rogues, Legacy. |
| **Supporting / companion routes** | `/curator` (Curator's Note + persuasion disclosure). |
| **Clear visual design system** | `src/styles.css` tokens (oklch palette, gradients, shadows) + `Exhibit.tsx` primitives (`ExhibitHero`, `Plaque`, `Prose`, `Figure`, `NextExhibit`). |
| **Intentional design style** | "Dark Deco" — Art Deco editorial in a noir palette, named after the show's own art direction. |
| **Brand archetype** | Sage (curator) + Hero (Batman). Drives voice, typography, and composition. |
| **Cialdini persuasion principle** | **Authority** — formal curator voice, plaques, credited figures, source-grounded prose. **Unity** — second-person framing ("the city you walked through as a kid") in the Atrium and Legacy. Both are documented in the Curator's Note. |
| **Images that support the subject** | Generated noir/deco backdrops + curated character plates (Joker, Freeze, Two-Face, Harley, Mad Hatter, Clayface, the voice cast), each with caption and credit. |
| **Evidence of research** | Named creators (Timm, Radomski, Dini), specific episodes (*Heart of Ice*, *Almost Got 'Im*, *Mad Love*, *Perchance to Dream*), production techniques (paint on black paper), and the DCAU/*Arkham* lineage. |
| **Coherent tone & educational purpose** | Curatorial third person throughout; every exhibit teaches one idea (origin, style, ethics, performance, antagonists, legacy). |

---

## Tech

TanStack Start (React 19) · TypeScript · Tailwind v4 (tokens in `src/styles.css`) · shadcn/ui primitives · file-based routing in `src/routes/`.

```
src/
├── components/
│   ├── Exhibit.tsx         # ExhibitHero, Plaque, Prose, Figure, NextExhibit
│   └── MuseumLayout.tsx    # numbered nav + outlet
├── routes/                 # index, origin, noir-deco, philosophy, voices, rogues, legacy, curator
├── assets/                 # generated + uploaded imagery
└── styles.css              # design tokens
```