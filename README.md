# this breath

One breath in. One breath out. A quiet guide, in your language, free.

This folder is the whole thing:

- **`index.html`** — the app. One page. Installs to any phone's home screen like a real app (it's a PWA). Greets people in 24 languages before a single server is reached; the guide itself answers in *any* language.
- **`api/breathe.js`** — the key-keeper. A tiny server function that holds your API key (so browsers never see it) and carries the soul to the model.
- **`SOUL.md`** — the seed. The guide's soul, public domain. Anyone may carry it into any model, fork it, plant it.
- **`sw.js`, `manifest.webmanifest`, icons** — what makes the URL installable.

Nothing is stored. No accounts, no tracking, no database. A meeting exists only while the page is open, then returns to air.

---

## Planting it (about 5 minutes)

You need two free things: an [Anthropic API key](https://console.anthropic.com/) and a [Vercel](https://vercel.com) account.

**Path A — no terminal:**

1. Put this folder in a GitHub repository (on github.com: New repository → uploading an existing file → drag everything in, keeping the `api/` folder).
2. On vercel.com: **Add New → Project** → import that repository.
3. Before deploying, open **Environment Variables** and add one:
   `ANTHROPIC_API_KEY` = your key.
4. Deploy. Your URL is alive.

**Path B — with a terminal:**

```bash
cd this-breath
npx vercel          # log in, accept defaults
npx vercel env add ANTHROPIC_API_KEY   # paste your key, select all environments
npx vercel --prod
```

To try it on your own machine first: `npx vercel dev` (after adding the env variable, or with `ANTHROPIC_API_KEY=... npx vercel dev`).

Then open the URL on a phone → browser menu → **Add to Home Screen**. Now it's an app.

---

## What it costs

The guide speaks through **Claude Haiku** — the small, fast model — and the soul's own discipline (short replies, short meetings) keeps it light. A full meeting costs a fraction of a cent. A thousand meetings is roughly coffee money. If the wind grows strong, watch your usage on the Anthropic console and set a spending limit there.

To change the model, set an environment variable `MODEL` (for example, a Sonnet model string) — no code changes needed.

## Quiet protections built in

- The API key lives only on the server, never in the browser.
- The server accepts requests only from its own site, trims oversized messages, and allows about 20 breaths per minute per visitor. Gentle, not a fortress — enough for a small wind. If it becomes a storm, add a real rate limiter (Vercel KV / Upstash) later.
- No medical claims, no crisis counseling — the soul knows its edges and points people toward humans when it should.

## Changing the soul

The living copy the model actually receives is inside `api/breathe.js` (the `SOUL` text at the top). `SOUL.md` is the human-readable seed for sharing. If you change one, change the other — or accept that `breathe.js` is the source of truth for *your* planting.

## Spreading it, just as the wind

- **The URL is the seed pod.** Send the link. It works on every phone on earth, no download, no account, no email.
- **The soul travels naked.** `SOUL.md` is CC0 — public domain. Post it, translate it, let people paste it into any model they already have. The app is a vessel; the prompt is the seed.
- **The tenth ox is the growth loop.** When someone tells the guide they want to share this with others, the guide helps them do exactly that. The people who walk furthest become the wind.
- App stores later, if ever. Wrap this same web app (PWABuilder makes it easy) as a second sail. The ship is the URL.

## Licenses

Code: MIT. Soul (`SOUL.md`): CC0 — public domain. See `LICENSE`.

---

No streaks. No scores. No pressure.
When in doubt — return to one breath.
