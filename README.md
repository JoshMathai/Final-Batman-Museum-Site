The Gotham Archive
A digital museum exhibit dedicated to Batman: The Animated Series (1992–1995) — the show that redefined what a superhero cartoon could be. The site is built as a guided, seven-stage tour through the series' origin, art direction, philosophy, voice cast, rogues gallery, and lasting cultural legacy.

Live exhibit routes

/ — Atrium (introduction & curator's thesis)
/origin — Exhibit I: Origin
/noir-deco — Exhibit II: Noir & Deco
/philosophy — Exhibit III: Philosophy (interactive)
/voices — Exhibit IV: The Voices
/rogues — Exhibit V: Hall of Rogues
/legacy — Exhibit VI: Legacy
/curator — Curator's Note

Using AI in different stages
AI was used as a pair, not a ghostwriter — a different role at each stage:

Stage	AI's role	My role
Concept	Brainstorm archetypes (Sage + Hero) and visual directions	Pick "Art Deco Editorial / Dark Deco" and reject generic options
Design system	Propose token names, oklch palette, typography pairings	Approve Cinzel + Cormorant Garamond, lock the gold/crimson/ink palette
Components	Scaffold Exhibit.tsx primitives (Plaque, Prose, Figure, NextExhibit)	Define the API so every exhibit feels consistent
Content	Draft prose for each exhibit from research notes	Edit for accuracy, tone, and Batman-fan credibility
Imagery	Generate noir/deco backdrop assets	Curate uploaded character photos and decide image placement
Interactivity	Implement the Philosophy tab state machine	Specify the five theses and their episode evidence

Using AI in different stages
AI was used as a pair, not a ghostwriter — a different role at each stage:

Stage	AI's role	My role
Concept	Brainstorm archetypes (Sage + Hero) and visual directions	Pick "Art Deco Editorial / Dark Deco" and reject generic options
Design system	Propose token names, oklch palette, typography pairings	Approve Cinzel + Cormorant Garamond, lock the gold/crimson/ink palette
Components	Scaffold Exhibit.tsx primitives (Plaque, Prose, Figure, NextExhibit)	Define the API so every exhibit feels consistent
Content	Draft prose for each exhibit from research notes	Edit for accuracy, tone, and Batman-fan credibility
Imagery	Generate noir/deco backdrop assets	Curate uploaded character photos and decide image placement
Interactivity	Implement the Philosophy tab state machine	Specify the five theses and their episode evidence

Required Museum Qualities
Requirement	Where it lives in this project
Clear topic	Batman: The Animated Series and why it redefined the superhero — stated in the Atrium thesis.
Strong homepage / introduction	src/routes/index.tsx — Atrium with hero, curator's thesis, and exhibit grid.
Guided route through the material	Numbered Exhibits I–VI plus Curator's Note, wired with NextExhibit footers and a persistent numbered nav in MuseumLayout.tsx.
Meaningful sections / exhibits	Origin, Noir & Deco, Philosophy, The Voices, Hall of Rogues, Legacy.
Supporting / companion routes	/curator (Curator's Note + persuasion disclosure).
Clear visual design system	src/styles.css tokens (oklch palette, gradients, shadows) + Exhibit.tsx primitives (ExhibitHero, Plaque, Prose, Figure, NextExhibit).
Intentional design style	"Dark Deco" — Art Deco editorial in a noir palette, named after the show's own art direction.
Brand archetype	Sage (curator) + Hero (Batman). Drives voice, typography, and composition.
Cialdini persuasion principle	Authority — formal curator voice, plaques, credited figures, source-grounded prose. Unity — second-person framing ("the city you walked through as a kid") in the Atrium and Legacy. Both are documented in the Curator's Note.
Images that support the subject	Generated noir/deco backdrops + curated character plates (Joker, Freeze, Two-Face, Harley, Mad Hatter, Clayface, the voice cast), each with caption and credit.
Evidence of research	Named creators (Timm, Radomski, Dini), specific episodes (Heart of Ice, Almost Got 'Im, Mad Love, Perchance to Dream), production techniques (paint on black paper), and the DCAU/Arkham lineage.
Coherent tone & educational purpose	Curatorial third person throughout; every exhibit teaches one idea (origin, style, ethics, performance, antagonists, legacy).
