# Contributing

Thanks for improving the Hermes Evolving Agents Roadmap.

## What good contributions look like
- Keep claims **bounded, challengeable, and source-linked**.
- Prefer **clarity over breadth**.
- Keep **DE/EN navigation** coherent when changing reader-facing material.
- Distinguish **observation**, **inference**, **design decision**, and **hypothesis**.
- Do not turn private/internal evidence into public certainty.

## Contribution areas
- **Narrative clarity** — tighten framing, remove ambiguity, improve reading order.
- **Evidence quality** — improve citations, tables, caveats, and claim-to-source traceability.
- **Visual communication** — clearer diagrams, stronger layout, better public legibility.
- **Governance framing** — make oversight, reversibility, and limitations more explicit.

## Pull request checklist
Before opening a PR, verify:
1. The public claim remains narrow and defensible.
2. New text is consistent with `docs/en/` and `docs/de/` where relevant.
3. Any stronger claim has explicit support or is marked as open.
4. Website changes still render correctly in GitHub Pages.
5. README and landing page still describe the same public object.

## Style guide
- Write short paragraphs.
- Prefer tables when comparing states, components, or limitations.
- Use numbered references for public-facing claims.
- Treat missing evidence as a visible limitation, not a footnote.

## Local preview
A simple local preview for the Pages site:

```bash
cd docs
python3 -m http.server 8789
```

Then open `http://127.0.0.1:8789/`.
