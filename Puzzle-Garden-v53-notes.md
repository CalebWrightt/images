# Puzzle Garden v53

This release fixes the collision between illustrated assets and fluid game layouts. Controls and word bars now use scalable CSS surfaces; supplied illustrations remain on cards, frogs, lily pads, symbols, tools, chess pieces, jars and other suitable artwork.

## Visual fixes

- Removed stretched PNG backgrounds from buttons, letter and number tiles, equation slots and Word Gradient bars. Cream CSS surfaces, inset borders and consistent shadows scale without distorted end caps or white corner triangles. Removed 119 redundant raster skins from the player bundle.
- Tile metadata has a dedicated footer: points stay at bottom-right, multipliers at bottom-left and penalties in a separate field. Wither inventory reads “n left” rather than looking like a multiplier. Repeated withering letters are grouped with their actual count, such as “L ×3”.
- Hop To It uses centered letters on clean discs, usage badges away from the pad outline, and larger frog icons and labels. Twist & Turn has separate tiles without beige column seams and clearer level tabs.
- Word Balance has clean rack tiles and word pills; three-digit weights such as J ×2 = 160 fit alongside the multiplier. Word Gradient has proportionate bars and room for the Outlier label. Play and Check buttons use readable CSS surfaces.
- Slide Show has contained edge previews and higher-contrast directional controls. Critical Sum has inset slot numbers and a typographic mystery tile.
- Card faces retain their aspect ratio and have clipped rounded corners without a second frame. Covered cards use shorter readable rank/suit strips. Pair Off shows all three rows and Undo at 390×844; shorter screens scroll instead of cutting off the last row. Dig Deep and Hole in One retain correct stack behavior.
- Roll Call dice now have blue, green and coral-red bodies matching their selectors, with pip patterns for every face. The directional pad uses compact controls.
- Status summaries and timers have explicit spacing, one separator and tabular timer digits. Dark-mode controls preserve readable contrast.
- Restored exact reviewed artwork and embedded font payloads after detecting a version-label replacement that had touched encoded data. The build now checks payload hashes and stops if artwork or font bytes change unexpectedly.

## Validation

- 104 home/game screen checks across 320×568, 390×844, 768×1024 and 1440×1000, with no detected missing boards, horizontal control overflow, broken images, duplicate IDs or uncaught page errors.
- 81 focused visual/layout checks covering the ten audited games at those four sizes in both themes, plus an active Wither word. Checks cover raster-free controls, metadata bounds and collisions, timer separators, card visibility, dice colors, preview bounds and badge positions.
- All 25 games generated fresh practice boards with landscape touch emulation.
- Nine regression groups include completed Critical Sum, Pokerdoku and Undercut playthroughs, keyboard interaction, gesture cancellation, persistence, backups, URL/date handling and home links.
- 49 card-stack checks plus three legacy-preference checks cover Dig Deep, Pair Off and Hole in One, including Dig Deep digging and undo.
- Art checks decode all 52 card faces, the joker and backs; exercise a legal Word Balance word with matching weight; and complete all four Patchwork deals.
- JavaScript lint reports zero findings. Dictionary, word-tier data and bundled daily puzzles match v52. Rules, scoring, undo allowances and hint charges are unchanged.
- Final phone and desktop screenshots were reviewed. Build payload hashes protect all retained artwork and embedded CSS data.

These are Chromium checks with touch emulation. Safari, Firefox, physical devices, screen readers and exhaustive playthroughs of every game were not verified.

## Opening and rebuilding

Download `Puzzle-Garden-v53.zip`, extract it, and open `Puzzle-Garden-v53.html` in a browser. The player is self-contained and works offline. Keep the same browser for saved progress; export a backup from Settings before switching browsers or files.

`Puzzle-Garden-v53-source.zip` contains editable JS/CSS/shell, payload hashes, the build script, QA scripts and selected evidence. Rebuild with `python3 source/build.py`. To run Chromium QA, use `npm install`, then `npx playwright install chromium` and `npm test`; `CHROMIUM_PATH` can select a system browser. The player needs no Node packages.

Supplied-art credit and existing attribution/license notices are retained. This release provides downloadable files and does not enable GitHub Pages hosting.
