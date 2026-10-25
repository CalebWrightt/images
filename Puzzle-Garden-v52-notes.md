# Puzzle Garden v52

This release integrates the four supplied asset ZIPs and fixes stacked-card rendering.

## Changes

- Dig Deep, Pair Off and Hole in One now show full-width rank/suit strips for covered cards. Clipped corners, conflicting negative margins and phantom stack heights were removed. Full card faces retain their proportions.
- Replaced both previous card decks with one supplied 52-card deck, joker and three backs. The missing hearts Queen, clubs Jack and spades King were correctly sourced from the mixed sheet. Removed the obsolete classic/pixel selector and its old image payloads; previous saved style settings remain harmless.
- Integrated supplied ivory/scored/gold/wild letter tiles, true ×2 letter faces, math operators and mystery tiles. Points, stock counts, chosen wild letters and game states remain live and accessible. The ×3/×4/×5 sheet variants are not attached to unrelated stock counts or embedded unused.
- Updated dice, all 12 chess pieces, gems, Slide Show symbols, frogs, lily pads, glass jars, mining tools, home game icons, controls, achievement badges and the Word Balance scale. Rulebreaker retains live rule-dependent geometry/colors/outlines rather than substituting a fixed image with incorrect rule attributes.
- Replaced Word Balance's decorative scale with supplied balanced/tilted artwork, while word weights and totals stay in separate readable boxes. The direction of tilt follows the actual heavier pan.
- Removed 108 superseded classic/compact card images, superseded game artwork, unused icon payloads and retired sprite/canvas effect data. Only used crops and rule-relevant variants are bundled; original full sprite sheets are not duplicated inside the player file. Existing sounds, fonts, brand/navigation identity and necessary semantic file/direction icons are retained.
- Crops use full connected-component bounds to avoid including neighboring sprite edges. Runtime WebP compression reduces supplied sprite data from about 11.2 MB to 3.5 MB without changing its dimensions or transparency layout.

## Validation

- Home and all 25 daily game screens: 104 checks at 320×568, 390×844, 768×1024 and 1440×1000; no detected missing boards, horizontal control overflow, broken images, duplicate IDs or uncaught page errors.
- All 25 games also generated fresh practice boards in dark mode, with landscape touch emulation.
- 49 stack checks cover the three affected games across four widths, two themes and both legacy card preference values, plus Dig Deep buried-card digging and undo. There is one new deck; legacy preference values do not restore the removed deck.
- Nine regression groups cover three completed playthroughs (Critical Sum, Pokerdoku, Undercut), keyboard interaction, cancelled gestures, reload persistence, backups, URL/date handling and home links.
- Additional checks decode all 52 faces, the joker and backs; exercise Word Balance with a legal word and matching displayed weight; and complete all four Patchwork deals with the supplied wild/gold tiles and a result.
- JavaScript lint reports zero findings for undefined names, duplicate keys, unreachable code, unused bindings and constant conditions.
- The dictionary, word-tier data and all 775 bundled daily puzzle entries are unchanged. Game rules, scoring, undo allowances and hint charges were not changed.
- Final mobile/desktop screenshots and the complete card atlas were visually reviewed.

Safari/Firefox, physical phones, screen readers, all historical-save migrations and exhaustive playthroughs of every game were not verified. Touch emulation is not a physical-device test.

## Files

`Puzzle-Garden-v52.zip` contains the offline HTML and opening instructions.
`Puzzle-Garden-v52-source.zip` contains editable JS/CSS/shell, the rebuild script, QA scripts and evidence.

To rebuild from the source package, run `python3 source/build.py`.
For Chromium QA, install the development dependencies with `npm install`, install Chromium with `npx playwright install chromium` if needed, and run `npm test`. `CHROMIUM_PATH` can select a system browser. The player HTML needs no Node packages.

Supplied artwork is credited in Settings. Existing license and attribution notices are retained in the HTML. No public website hosting or GitHub Pages configuration was enabled by this release.
