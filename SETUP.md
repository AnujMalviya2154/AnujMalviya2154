# Setup checklist

Only `README.md` renders on your GitHub profile page. This file is safe to keep
or delete before pushing — it won't be visible to visitors either way.

---

## 1. Create the repo

The repo name must match your username **exactly**, and it must be public:

```
AnujMalviya2154
```

GitHub only treats a repo as a profile README if the name matches the username.
`anujmalviya2154` or `AnujMalviya-2154` will not work.

```bash
cd AnujMalviya2154
git init
git add .
git commit -m "feat: profile readme"
git branch -M main
git remote add origin https://github.com/AnujMalviya2154/AnujMalviya2154.git
git push -u origin main
```

---

## 2. Fill the three placeholders

In `README.md`, search for and replace:

| Placeholder | Replace with |
|---|---|
| `YOUR_EMAIL_HERE` | your contact email |
| `YOUR_RESUME_URL_HERE` | a stable public link (Drive share link is fine) |

The LinkedIn URL is already set to `linkedin.com/in/anujmalviya764` — confirm
that's correct.

---

## 3. Add the two screenshots

Both go in `assets/`. Both should be **dark-theme** captures so they read as a
matched pair.

| File | Size | What to capture |
|---|---|---|
| `assets/mockhire-room.png` | 560 × 340 | Interview room with video tiles **and** the shared code editor visible in one frame. If chat fits too, include it. |
| `assets/fintrak-dashboard.png` | 560 × 340 | Crop tight to the charts area — the monthly overview and category distribution. Skip the nav chrome. |

Exact pixel size isn't critical, but keep both at the **same aspect ratio**
(roughly 16:10). Mismatched ratios are the fastest way to make the pair look
accidental.

The MockHire repo already has product screenshots committed — crop from those
rather than re-capturing.

---

## 4. Verify before you call it done

- [ ] Toggle GitHub between light and dark mode. The banner and the P2P diagram
      should each swap. If they don't, the `<picture>` block didn't apply.
- [ ] Check the page on a phone. The screenshot + diagram pair should wrap to
      two stacked rows rather than squashing.
- [ ] Confirm the **activity graph** widget actually renders. That service has
      had reliability issues. If it's blank or slow, delete that one `<p>` block
      — the design loses nothing without it.
- [ ] Confirm the **streak** widget renders. Same deal.

---

## 5. Repo housekeeping (same day)

These matter because the README argues you're precise, and the repos below it
shouldn't contradict that.

- [ ] **BlogVerse** — the description claims "MERN stack principles" but there's
      no MongoDB and no React. It's EJS over JSON files. Rewrite it honestly.
- [ ] **Fix three wrong clone URLs** in these READMEs:
  - MockHire → says `Video-Interview-Platform`
  - BlogVerse → says `Blog-app`
  - anime-quote-generator → says `anime-quote-app`
- [ ] **Set pins to 4, not 6:** MockHire, Fintrak, ThinkBoard, NeetCode-150.
- [ ] **Archive `html-portfolio`.** Feb 2024, no description, weakest thing on
      the profile.

---

## Design system reference

Keep these values if you extend the profile later.

| Token | Light | Dark |
|---|---|---|
| Accent | `#B0741F` | `#E8A94E` |
| Wordmark | `#1F2328` | `#E6EDF3` |
| Muted text | `#6E7681` | `#8B949E` |
| Hairline / dots | `#D9D4CB` | `#262C33` |
| Widget text (shared) | `#768390` | `#768390` |

Rules the design depends on:

- **`###` for section headers, never `##`.** GitHub auto-draws a horizontal rule
  under `#` and `##`. Using `###` keeps rule placement under your control.
- **No HTML tables.** They get cell borders and scroll sideways on mobile.
  Side-by-side images are done with two `<img>` tags in one centered `<p>`.
- **Blockquotes as cards.** The `How I work` section uses `>` for its left rule —
  native markdown, no CSS needed.
- **Badges:** `flat-square` only, five on the whole page. Never `for-the-badge`.
- **No emoji.** Anywhere. This is the main thing separating the page from a
  template.
