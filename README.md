# Revelry Toolkit

A character builder, play sheet and Spellforge for **Revelry**, a tabletop RPG
of contested d20 rolls where the margin buys what happens next.

**[Open the Character Builder →](https://sumosaga.github.io/revelry-toolkit/)**

| Page | What it does |
| --- | --- |
| [Builder](https://sumosaga.github.io/revelry-toolkit/) | Eleven steps from spark to legend, with the sheet filling in beside you. |
| [Play Sheet](https://sumosaga.github.io/revelry-toolkit/sheet/) | The sheet on its own: Grit, Momentum, Wounds, the Attack/Defense strip, and the maneuver and Spellforge flyouts. |
| [Spellforge](https://sumosaga.github.io/revelry-toolkit/spellforge/) | Building a spell out of Elements and Components, and seeing what it costs. |

Characters live in your own browser, under `localStorage`. Nothing is uploaded
and there is no account: a character built in the Builder opens on the Play
Sheet because both are reading the same key in the same browser. Clearing your
site data clears your characters, so export anything you mean to keep.

## Notes

Three static pages. No build step, no server, no framework, no dependencies —
each page is a single HTML file with every stylesheet and script inlined, so
they run just as happily from a `file://` URL as from here.

Five colour palettes ship with it; the dots in the header switch between them
and your choice follows you across all three pages.

## Source

Generated from the working repo by `build-single-file.py`. Edit there, rebuild,
and copy `dist/` over this folder — **do not hand-edit the HTML here**, it will
be overwritten on the next build.
