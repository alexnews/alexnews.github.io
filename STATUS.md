# STATUS — alexnews.github.io

Static portfolio site (HTML5 UP "Read Only" template). Single page: `index.html`.
Deployed by GitHub Pages from `main`. **Anything pushed to `main` is live immediately.**

## BLOCKING — do not push until resolved

`index.html` contains two literal placeholders in the **Education & Certifications** section:

- `[[UNIVERSITY_NAME]]`
- `[[YEAR]]`

They render as visible text on the page. Fill them in before pushing, or delete the
Master's line. Search: `grep -n '\[\[' index.html`

## In flight

Uncommitted working-tree changes to `index.html` (recruiter-credibility pass), pending Alex's review:

- Added `#experience` section (7 roles, Silicon Army → LiveIntent) + nav entry.
- Added `#education` section (Master's + SnowPro Core). No nav entry by design.
- Removed the dead `Download CV` button (it pointed at `href="#"`).
- Rewrote `About Me` to lead with employment history and migration work; added a
  **semantic layer** paragraph linking to Alex's own 2026-08-08 Daily AI Brief analysis.
- Rewrote `Skills`: added Data Migration & Modernization, Snowflake Platform,
  Database Engineering & Production Support, Delivery & Collaboration.
- Updated `<title>` / meta description / JSON-LD; removed `PySpark` from JSON-LD
  `knowsAbout` (Alex will not defend it in interview).

## Open decisions for Alex

- **CV file.** No `Alex_Kargin_Resume.pdf` exists in the repo, so the header button was
  removed rather than left dead. Commit the PDF to the repo root and re-add the button
  (the removed markup is left as an HTML comment in `index.html`, in `#header > header`).
- **`Apache Kafka`** is still listed in JSON-LD `knowsAbout`. It is pre-existing, appears
  nowhere else on the page, and is not corroborated by any listed role. Keep or drop?

## Content rules for this repo

There is a standing forbidden-keyword list for this site — technologies Alex will not
defend in an interview and that must never appear in user-visible text (Spark/PySpark,
Databricks, Terraform, Kubernetes, Tableau, LangChain, MCP, Salesforce, clearances, etc.).
Never add a technology keyword to `Skills` that is not backed by a role in `#experience`.
Never invent employers, titles, dates, metrics, degrees, or certifications.

## Verified (2026-08-09)

- JSON-LD parses; HTML tag balance clean.
- All 5 nav anchors resolve; only remaining `href="#"` is the `#logo` template idiom.
- All 18 external links return HTTP 200.
- Renders correctly at 1440x900 and 390x844 (mobile nav panel includes Experience).
- Zero forbidden keywords in user-visible text.

## Local preview

```
python3 -m http.server 8899   # then open http://localhost:8899/
```
