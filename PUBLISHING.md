# Putting this on GitHub Pages

Everything in this folder is the site. Four files, no build step at the far end
— GitHub serves them exactly as they are.

The URL you will end up with:

**`https://sumosaga.github.io/revelry-toolkit/`**

---

## The drag-and-drop way

No command line. About two minutes.

1. Go to **[github.com/new](https://github.com/new)**.
2. Repository name: **`revelry-toolkit`**. Set it to **Public** — GitHub Pages
   needs public on a free account. Leave every checkbox alone; do **not** tick
   "Add a README", because this folder already has one.
3. Click **Create repository**.
4. On the empty repo page, click **uploading an existing file**.
5. Open this `revelry-pages` folder and drag **everything inside it** into the
   browser — not the folder itself, its contents. You want `index.html`, the
   `sheet` folder, the `spellforge` folder, `README.md` and `.nojekyll` landing
   at the top level of the repo.
   - If `.nojekyll` will not drag (Windows hides dotfiles), skip it. Nothing
     here starts with an underscore, so Jekyll has nothing to eat.
6. Click **Commit changes**.
7. Go to **Settings → Pages** in that repo. Under *Build and deployment*, set
   **Source** to `Deploy from a branch`, **Branch** to `main` and the folder to
   `/ (root)`. Save.
8. Wait a minute or two. The link appears at the top of that same Settings →
   Pages screen.

## The command-line way

From inside this folder:

```bash
git init -b main
git add -A
git commit -m "Revelry Toolkit — builder, play sheet, Spellforge"
git remote add origin https://github.com/sumosaga/revelry-toolkit.git
git push -u origin main
```

Then do step 7 above — Pages still has to be switched on in Settings, once.

---

## Updating it later

The HTML here is **generated**. Edit the real source in `../revelry/`, then:

```bash
cd ../revelry
python3 build-single-file.py
cp -r dist/* ../revelry-pages/
```

and commit. Never hand-edit the HTML in this folder; the next build overwrites
it without asking.

## Two things worth knowing

**Characters live in the browser, not on the site.** They are in `localStorage`,
which is per-browser and per-origin. So a character built on
`sumosaga.github.io` is not the same vault as one built from a local file, and
anyone you send the link to gets their own empty vault rather than yours. That
is the right behaviour for a character sheet, but it does mean *you* will start
empty on the published site too — and that clearing site data clears characters.

**This is a separate repo from the Parry sheet.** `Revelry-Parry-Hybrid-Sheet`
still runs the Parry ruleset and stays where it is; nothing here touches it.
Both can be live at once, which is the point of having branched rather than
overwritten.
