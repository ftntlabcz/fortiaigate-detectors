# FortiAIGate Governance Detectors

Interactive map of the predefined governance detectors in FortiAIGate 8.0.2.

**Live page:** https://ftntlabcz.github.io/fortiaigate-detectors/

## Controls

- **Click a bubble** to highlight everything connected to it and open the detail panel with a description and a link to the official source.
- **Region chips** (EU & Europe, USA, Asia, Global) in the top bar show or hide detectors from that region.
- **Hide topics** leaves only categories and detectors for a cleaner overview.
- **Search** highlights matching detectors and topics.
- **Recenter** fits the whole graph back on screen. **Full screen** is for presenting.
- **Drag** to pan, **scroll** to zoom, drag a bubble to move it.
- **EN / CZ / SK** in the top right switches the interface language.

## Suggesting a change

Found a mistake or want to add something? Send a pull request.

1. **Fork** this repository (button *Fork* at the top right of the repository page).
2. In your fork, edit the data:
   - `src/detectors.py` for detectors: region, rule count, topics, official link, descriptions
   - `src/topics.py` for topics: names, descriptions, source link
3. Regenerate the page data:
   ```bash
   python3 src/build.py data.js
   ```
   If you edit directly on GitHub and cannot run the command, skip this step and mention it in the pull request.
4. **Commit** the changes and open a **Pull request** against `main` in `ftntlabcz/fortiaigate-detectors`. Describe what you changed and add a link to the source.

Collaborators with write access can create a branch here directly instead of forking.
