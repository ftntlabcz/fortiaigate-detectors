# FortiAIGate Governance Detectors

An interactive map of the predefined governance detectors that ship with **FortiAIGate 8.0.2**: AI security frameworks and regulations, grouped by category and colored by region.

**Open the map:** enable GitHub Pages for this repository (see below) and visit `https://<account>.github.io/<repo>/`.

## What it shows

- **6 categories:** AI & LLM Security, EU & European Regulations, AI Governance Standards, Industry Regulations, USA, Asia
- **51 detectors**, colored by region: EU & Europe, USA, Asia, Global
- **82 topics** that the detectors cover. A topic shared by several detectors is one node, so overlaps are visible at a glance (for example, *Prompt injection* is covered by 7 detectors).

Every detector and topic has a short description and a link to its official source: the legal text on EUR-Lex, the standard body, the regulator or the OWASP / MITRE project page.

Interface languages: **English** (default), Czech, Slovak.

### Using it

- Click a bubble to highlight its connections and open the detail panel.
- Filter by region with the chips in the top bar.
- *Hide topics* leaves only categories and detectors, which works well as an overview slide.
- Search, recenter and full screen are in the top bar. Drag to pan, scroll to zoom.

## Publish with GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under *Build and deployment*, choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Save. The page is live at `https://<account>.github.io/<repo>/` within a minute or two.

The page is static: `index.html`, `data.js` and D3 loaded from cdnjs. No build step is needed to host it.

## Editing the data

The data lives in Python files under `src/`:

| File | Contents |
| --- | --- |
| `src/detectors.py` | Categories and detectors: region, rule count, topics, official URL, descriptions (EN/CS/SK) |
| `src/topics.py` | Topics: labels, descriptions (EN/CS/SK), official source |
| `src/build.py` | Generates `data.js` |

After editing, regenerate the data file:

```bash
python3 src/build.py data.js
```

## Sources and caveats

- Detector list and rule counts: FortiAIGate 8.0.2 GUI, *Regulation and security framework detectors (shipped by Fortinet, view-only)*. The rule count for Utah SB 149 was not visible in the listing.
- [FortiAIGate 8.0.2 documentation – Detectors and guardrails](https://docs.fortinet.com/document/fortiaigate/8.0.2/fortiaigate-administration-guide/210987/detectors-and-guardrails)
- Per the Fortinet documentation, a detector match **is not a regulatory compliance assessment or certification**.
- Descriptions are short summaries written for orientation. Always check the linked official text.
- The 2023 EEOC technical assistance on AI in hiring is no longer published on eeoc.gov. The EEOC detector links to the underlying Uniform Guidelines (29 CFR 1607).
- Unofficial overview, not affiliated with or endorsed by Fortinet.
