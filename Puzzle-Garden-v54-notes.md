# Puzzle Garden v54

Check & Flip now has fixed square board tracks, Word Balance words sit on the illustrated pans, and new Rulebreaker puzzles start with an empty 4×4 grid and a hand of 16 pieces.

**Pattern artwork limitation:** the requested Google Drive folder could not be retrieved in this environment (connection blocked with HTTP 403). Its “pattern mix” artwork is not included. This version uses subdued motifs already bundled in the game, with calmer sage colors for Roll Call. Attach the requested folder as a ZIP to incorporate that exact artwork in a follow-up.

## Changes

- Check & Flip uses an explicit row count and a square board whose cells cannot expand to image dimensions. Every chess piece is contained with its native proportions. Hand slots reserve consistent space for names. The play layout scrolls rather than shrinking the board as pieces and captions change. At a given viewport, initial and fully occupied boards have the same dimensions.
- Word Balance places word chips directly on the pan surfaces. Chips follow the balanced, left-heavy and right-heavy illustrations; totals stay in a small summary above. Each pan supports two stacked words, including seven-letter words, without changing scoring or the four-round rules.
- Rulebreaker is now a placement game for new puzzles. Fill the empty grid with all 16 supplied pieces, arranging them so every listed statement is false somewhere. Shapes, colors, outlines and directions are fixed properties of the hand pieces. Drag, tap-to-place, moving, swapping and returning pieces are supported. The old edit budget and row/column edit restriction do not apply to this placement version.
- Every new Rulebreaker hand has a deterministic tested solution. Empty squares never count as breaking a rule. Check is available after all 16 pieces are placed. Scoring remains 1,000 per broken rule plus 4,000 for completion, with 300 deducted per failed check; rearranging is free. Scores are kept separate from older rule versions.
- Saved older Rulebreaker attempts retain their original board and rules. A link on the saved mosaic starts a practice game with the new placement rules. New daily and practice puzzles use the empty-grid version.
- Artwork uses `saturate(1.1)`, a 10% saturation increase applied to images and game symbols rather than entire panels or text. A shared alpha filter removes faint matte fringes. Supplied art bytes remain intact and protected by build-time hashes.
- Removed high-specificity legacy card-column backgrounds, padding and duplicate shadows, including Pair Off’s extra dark cushion. Card images retain their natural outlines, rounded clipping and proportional faces. Covered-card rank/suit strips remain readable.
- Added quiet themed board textures from the existing offline bundle. Roll Call uses softer sage cells and very faint grass motifs. Patterns have low opacity and do not intercept taps.

## Validation

- JavaScript lint: zero findings.
- 104 home/game screen checks across 320×568, 390×844, 768×1024 and 1440×1000: no detected missing boards, horizontal control overflow, broken images, duplicate IDs or uncaught page errors.
- All 25 games generated fresh practice boards with landscape touch emulation.
- Nine existing gameplay regression groups passed, including completed Critical Sum, Pokerdoku and Undercut playthroughs, persistence, backup validation, URL/date handling, keyboard interaction and pointer cancellation.
- 49 card-stack checks and three legacy-preference checks passed, including digging and undo.
- Existing artwork checks decode every card face and back, exercise a legal Word Balance word, and complete all four Patchwork deals.
- 81 existing focused visual checks across four sizes and both themes passed.
- New Rulebreaker tests verify 19 deterministic solvable daily/practice hands, empty initial grids, inventory uniqueness, moves, swaps, returns, incomplete-check rejection, penalty arithmetic, completion scoring, pointer cancellation, drag and tap placement, reload persistence, a completed UI playthrough and old saved mosaics.
- New Check & Flip checks load every piece type/color and verify unchanged square board dimensions, equal row heights and image containment at four sizes.
- New Word Balance checks exercise left-heavy, right-heavy and level loads at four sizes and verify chip bounds on the scale.
- 40 additional checks cover Check & Flip, Rulebreaker, Word Balance, Roll Call and Pair Off across four sizes in both themes. They check saturation filters, texture opacity, image decoding, horizontal bounds and removal of card-stack cushions. Final screenshots were visually reviewed after the last CSS adjustment.
- Dictionary, word-tier data and bundled historical daily data remain byte-for-byte unchanged. New Rulebreaker puzzles are generated under `rulebreaker-placement-1`; older puzzle rules are preserved.

Testing used Chromium, with touch emulation where noted. Safari, Firefox, physical phones, screen readers and exhaustive playthroughs of every game were not verified.

## Files

Extract `Puzzle-Garden-v54.zip` and open `Puzzle-Garden-v54.html`. It is self-contained and works offline. Use Settings to export a backup before changing browser or file version; local-file storage behavior varies by browser.

`Puzzle-Garden-v54-source.zip` contains editable source, payload hashes, QA scripts and selected evidence. Rebuild using `python3 source/build.py`. Run QA with `npm install`, `npx playwright install chromium`, then `npm test`. `CHROMIUM_PATH` can select a system browser. Development dependencies are not needed to play.

Existing credits and license notices are retained. GitHub Pages hosting is not enabled by this release.
