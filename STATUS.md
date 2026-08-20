# STATUS — alexnews.github.io

Static portfolio site (HTML5 UP "Read Only" template). Pages: `index.html` and
`code-with-claude-2026/index.html`.
Deployed by GitHub Pages from `main`. **Anything pushed to `main` is live immediately.**


## Live pages

- `index.html` — main portfolio.
- `code-with-claude-2026/` — summaries of all 19 talks from Anthropic's Code with Claude
  2026 conference, with video links. Source notes live in `HQ/youtube/`.
- `navigator/` — one-page Navigator AI architecture draft, written for the Flash Global
  interview (Aug 2026). `noindex` + disallowed in `robots.txt`, so it is reachable by link
  only and stays out of search. Regenerate the shareable PDF by printing it from Chrome
  headless in light theme; the current PDF lives in
  `~/Downloads/000RESUME/interviews-20260817/`.
- `sitemap.xml` — referenced by `robots.txt`; previously 404'd.


## Open decisions for Alex

- **CV file.** No `Alex_Kargin_Resume.pdf` exists in the repo, so the header button was
  removed rather than left dead. Commit the PDF to the repo root and re-add the button
  (the removed markup is left as an HTML comment in `index.html`, in `#header > header`).
- **Push discipline.** `main` deploys instantly, and a `git push` ships *every* unpushed
  commit — not just the newest. Check `git log origin/main..HEAD` before pushing when
  anything is being held back deliberately.
- **`Apache Kafka`** is still listed in JSON-LD `knowsAbout`. It is pre-existing, appears
  nowhere else on the page, and is not corroborated by any listed role. Keep or drop?

## Content rules for this repo

There is a standing forbidden-keyword list for this site — technologies Alex will not
defend in an interview and that must never appear in user-visible text (Spark/PySpark,
Databricks, Terraform, Kubernetes, Tableau, LangChain, MCP, Salesforce, clearances, etc.).
Never add a technology keyword to `Skills` that is not backed by a role in `#experience`.
Never invent employers, titles, dates, metrics, degrees, or certifications.

## Verified (2026-08-15)

- JSON-LD parses on both pages; HTML tag balance clean on both.
- All 19 YouTube IDs on the notes page cross-checked against the resolved source list, in order.
- `/`, `/code-with-claude-2026/` and `/sitemap.xml` all return 200 locally.
- Notes page renders correctly and matches template styling; anchor links (`#talk-N`) work.
- Zero forbidden keywords in user-visible text on either page (notes page originally said
  "MCP server" for the Google Cloud talk — reworded to "live documentation service").

## Verified earlier (2026-08-09)

- All 5 original nav anchors resolve; only remaining `href="#"` is the `#logo` template idiom.
- All 18 external links return HTTP 200.
- Renders correctly at 1440x900 and 390x844 (mobile nav panel includes Experience).

## Local preview

```
python3 -m http.server 8899   # then open http://localhost:8899/
```
