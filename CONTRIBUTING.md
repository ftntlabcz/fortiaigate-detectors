# Contributing

Thanks for helping keep this map accurate. Corrections, new detectors from newer FortiAIGate versions and better source links are all welcome.

## Ways to contribute

- **Report a mistake or suggest an addition:** open an [issue](../../issues/new/choose) and pick a template.
- **Fix it yourself:** send a pull request (below).

## Pull request workflow

1. **Fork** the repository, or create a branch if you are a collaborator.
2. Edit the data in `src/`:
   - `src/detectors.py`: categories and detectors
   - `src/topics.py`: topics
3. Regenerate the page data and check it builds without errors:
   ```bash
   python3 src/build.py data.js
   ```
   Editing in the GitHub web editor and cannot run it? Say so in the pull request and a maintainer will regenerate `data.js`.
4. Open `index.html` in a browser and check your change in the graph.
5. Open a **pull request** against `main` and fill in the template.

Do not edit `data.js` by hand. It is generated.

## Data format

A detector entry in `src/detectors.py`:

```python
("GDPR", "eu", "eu", 6,
 ["personal", "privacy", "adm"],
 "https://eur-lex.europa.eu/eli/reg/2016/679/oj",
 {"en": "...", "cs": "...", "sk": "..."}),
```

| Field | Meaning |
| --- | --- |
| name | Exactly as shown in the FortiAIGate GUI |
| category | `sec`, `eu`, `std`, `ind`, `usa` or `asia` |
| region | `eu`, `usa`, `asia` or `global` (sets the color) |
| rules | Rule count from the GUI, or `None` if unknown |
| topics | Keys from `src/topics.py` |
| url | Link to the official text or project page |
| descriptions | One or two sentences in English, Czech and Slovak |

A topic entry in `src/topics.py` holds the label in three languages, the official source link and its name, and a one-sentence description in three languages. A topic shared by several detectors is defined once.

## Content guidelines

- **Official sources only:** legal texts (EUR-Lex, legislature sites), regulators, standards bodies, or the framework's own project page. No blogs or vendor marketing.
- **Facts from the product:** names and rule counts must match the FortiAIGate GUI or documentation. Mention the version you checked.
- **Neutral and short:** describe what a law or framework covers. Do not claim that FortiAIGate makes anyone compliant.
- **All three languages:** if you cannot write Czech or Slovak, leave the English text in those fields and say so in the pull request.

## Code of conduct

By taking part you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md).
