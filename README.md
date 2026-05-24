# Privacy & landing page for My Life on the Move

A single-file static site (`index.html`) designed to satisfy the privacy-policy URL requirement for Meta, Google (YouTube), and TikTok developer app reviews. Editorial design, single page, no JavaScript dependencies (other than auto-updating the footer year).

## Customise (one-time)

Open `index.html` in any editor and find-and-replace these placeholders:

| Placeholder | Replace with | Example |
|---|---|---|
| `My Life on the Move` | Your brand / app name | `Wander Notes` |
| `{APP_TAGLINE}` | One-line description | `Travel video automation for indie creators` |
| `cyberwire2025@gmail.com` | Contact email | `hello@wandernotes.app` |
| `Mylifeonthemove` | Your public handle, no `@` | `wandernotes` |
| `{SITE_URL}` | Where this page will live | `https://wandernotes.github.io/privacy` |
| `24 May 2026` | Today, written out | `24 May 2026` |

VS Code: `Cmd+Shift+H` opens find-and-replace across all files. Do the six replacements, save, you're done.

## Publish to GitHub Pages

```bash
# 1. Create a new repo on github.com — any name works.
#    Easiest pattern: name the repo "privacy"
#    so the final URL is https://<your-username>.github.io/privacy/

# 2. Locally:
cd privacy-site
git init
git add .
git commit -m "Initial privacy site"
git branch -M main
git remote add origin git@github.com:<your-username>/privacy.git
git push -u origin main

# 3. On github.com:
#    Settings → Pages → Source: "Deploy from a branch"
#    Branch: main, folder: / (root) → Save

# 4. Wait ~1 minute. Your site is live at:
#    https://<your-username>.github.io/privacy/
```

That URL is what you paste into Meta's "Privacy Policy URL" field, TikTok's developer app, and YouTube's OAuth consent screen.

## Custom domain (optional)

If you own a domain (e.g. `wandernotes.app`):

1. In the repo root, create a file named `CNAME` (no extension) containing just your domain on one line: `privacy.wandernotes.app`
2. On your DNS provider, add a CNAME record pointing `privacy` to `<your-username>.github.io`
3. In repo Settings → Pages → enter the custom domain, check "Enforce HTTPS"

Wait ~15 minutes for HTTPS to provision, then visit `https://privacy.wandernotes.app/`.

## What this page covers

Meta and TikTok reviewers look at your privacy policy URL and check for:

- ✅ Page loads and is specifically about your app (not a generic template)
- ✅ Lists what data is collected, why, how long it's kept
- ✅ Lists third-party integrations by name (Meta, Google, OpenAI, TikTok)
- ✅ References Meta Platform Terms and Developer Policies by link
- ✅ Has a working contact method
- ✅ Has a "Last updated" date
- ✅ Covers children's privacy (Meta especially)
- ✅ Mentions GDPR / data-subject rights

All present. The wording is written as if this is a single-operator personal tool, which is true and is the simplest configuration to get approved.

## When your situation changes

If you ever start letting other people use the app (giving someone else access to the bot, or extending it to friends), you should:

- Update the "What this is" section
- Update "What information the app handles" to reflect new data flows
- Bump the "Last updated" date
- Add a short summary of the change at the bottom of the policy

Until then, this version is good to ship.
