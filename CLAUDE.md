# HR Connect 2027 — membership brochure

Single-page React (Vite + Tailwind) app. All content lives in `src/App.jsx`
(membership bands, benefits, programme calendar, members, testimonials).

## Deploying to gh-pages — ALWAYS

After any change that affects the site, **redeploy to gh-pages** so the live
site stays current. Do this without being asked, as part of finishing the work:

```
npm run deploy   # = vite build && npx gh-pages -d dist
```

Confirm it prints `Published` before reporting done.

## Workflow

- Develop on branch `claude/hr-connect-brochure-48kzfi`.
- Run `npm run build` to verify changes compile.
- Redeploy gh-pages (see above).
- Commit with a clear message and push the branch.
- Open a fresh PR into `main` only when asked.

## Branding — HR Connect, not NEXT.io

HR Connect has its own identity. Do **not** restyle this toward the NEXT.io
dark-grey/yellow house style used by the summit brochures.

- Green `#245b3c`, deep green `#1b2d21`, amber `#ffce33`, cream `#fffdf6`,
  sand `#f6f3e9` — defined as `hrc-*` tokens in `src/index.css`.
- Type is Plus Jakarta Sans.
- The lockup is an `<img>`, so it cannot inherit `currentColor` — use the
  matching colourway file in `public/logos/` (`-green`, `-amber`, `-white`).
- The four-piece `<Mark>` is inline SVG and *does* follow `currentColor`. It
  carries explicit `width`/`height` attributes; without them `w-auto` has no
  intrinsic ratio to work from and the mark renders at full size.

## Content rules

- Membership bands are the `TIERS` array; shared deliverables are `TIER_INCLUDES`.
  Only the representative count and fee change between bands.
- `CONTACT` (top of `App.jsx`) is the enquiry address used by every mailto.
- The programme calendar is deliberately member-facing only. Internal admin,
  invoicing and campaign lines from the project deck are filtered out.

## Internal-only material — never publish

The 2027 project deck is an internal document. These must not reach the site:
revenue, cost of sales, commission, profit, cashflow, per-member fees, churn,
internal KPI targets, team responsibilities, sales mechanics (light-membership
add-on, September Drive, HubSpot campaigns) and the OneDrive link.

See `README.md` for the full list.

## Notes

- Member logos in `public/logos/members/` were extracted from the official
  infographic: background flood-filled to transparency, chamfered corners masked,
  then quantised to 128 colours (1.3 MB → 313 KB).
- The `neo-group` logo is icon-only in the source artwork; it was identified
  from the members word-cloud in the project deck.
