# German Pronunciation Verifier

A static, AMOLED-black German-learning tool with a dictionary/example page and a pronunciation-audio lookup page.

## How the current search works

1. Calls WiktApi's structured word endpoint, filtered to German entries.
2. Requires an exact normalized headword match and a German language identifier.
3. Checks the structured pronunciation fields for a file/URL reference. It does not guess from a regular expression over raw wikitext.
4. Only labels the Wiktionary entry as having an audio reference when the structured metadata check passes.
5. If the exact entry or audio metadata cannot be confirmed, it clearly says so and shows manual dictionary search links.

## Pronunciation fallback

- The pronunciation page prioritizes an actual German audio file linked from the German Wiktionary entry when one is found.
- When no native recording is detected, the page offers browser/device speech synthesis only if an installed voice has a German language tag (`de-*`). It never silently falls back to an English voice.
- Device speech synthesis is labelled as generated TTS, not a native-speaker recording. Voice quality and availability depend on the user's operating system and browser.
- The dictionary page uses the same strict German-only TTS fallback. IPA and Bengali phonetic spellings are not fabricated when a reviewed source is unavailable.

## Accuracy and limitations

- WiktApi is a third-party API based on processed Wiktionary data; it is not an official Duden, PONS, or DWDS API.
- An audio reference in data does not guarantee that the file still works or that it matches every regional pronunciation. Open the source entry to listen and verify.
- The frontend does not claim to search every dictionary, and it does not mark Duden/PONS audio as verified. They are alternatives for manual checking.
- If WiktApi is unreachable or browser access is blocked, the app shows a fallback message instead of inventing a result.
- No API keys or secrets are stored in this repository.

## References

- [WiktApi quickstart and endpoints](https://wiktapi.dev/quickstart)
- [WiktApi data pipeline and structured sound fields](https://wiktapi.dev/concepts/data-pipeline)
- [Duden](https://www.duden.de/)
- [PONS](https://de.pons.com/)

## GitHub Pages

The frontend is a static `index.html` file and requires no build step. Configure GitHub Pages in repository settings if it is not already enabled.

## Dictionary and translation behavior

- The dictionary keeps the bundled A1 vocabulary as a local fallback, including its English glosses and example sentences.
- Locally curated Bengali mappings take priority over the local English-to-Bengali map; online machine translation is a fallback only and is labelled as unverified in the interface.
- Translation fallback tries MyMemory first, then Google's keyless web translation endpoint. The latter is unofficial and may change, rate-limit, or stop working; it is not the Google Cloud Translation API and has no uptime guarantee.
- The app never stores a private API key. Searching a word or sentence may send that text to the translation provider when fallback translation is needed.
- Common A1 German verb forms and phrases have explicit lookup mappings. This is helpful coverage, not a complete German morphological analyser; rare forms and context-dependent phrases may still need manual checking.
- Deutschly's Bengali meanings and example sentences are independently authored or curated by the maintainer. Any text copied verbatim from an external source must be separately attributed and checked against that source's reuse terms before redistribution.

## Validation notes

The embedded JavaScript in both HTML pages was syntax-checked after the latest changes. This does not replace live browser testing: third-party API availability, CORS behavior, audio file availability, and the GitHub Pages deployment still need to be checked in a browser.


## Deutschly learning data and search

- `data/a1-vocabulary.json` contains the maintainer-authored and curated A1 word list. The suggested reference list was compared against the database: 1,715 reference rows were reviewed, 10 duplicate rows were consolidated, and 8 missing vocabulary items were recovered, resulting in 1,713 unique normalized headwords. Page references are retained only for traceability to the suggested reference.
- `data/grammar-terms.json` contains curated German–Bangla grammar terminology. It is a separate data source and does not inflate the A1 vocabulary count.
- `data/compound-analysis.json` contains curated exact compound-word analyses. It does not guess arbitrary word splits.
- `data/a1-vocabulary-audit.json` records the first-pass audit and unresolved items. A blank plural is not automatically an error: many entries are mass nouns, collective nouns, months, or have uncommon/context-specific plurals.
- Dictionary records expose a confidence label: source-checked correction, reviewed draft, or needs verification. A review batch is not the same as a guarantee that every grammatical detail has been independently verified.

## Optional AI assistant deployment

The AI assistant interface is `ai-assistant.html`. It is deliberately shown as **not connected** until a private backend is deployed and configured.

1. Create a Cloudflare Worker from `worker/src/index.js` (the included `wrangler.toml` is a starting configuration).
2. Add `OPENAI_API_KEY` as a Worker **secret** and `OPENAI_MODEL` as a Worker variable in the Cloudflare dashboard. Never add the API key to GitHub, `data/ai-config.json`, or browser JavaScript.
3. Keep `ALLOWED_ORIGIN` set to `https://atnyt.github.io`. The Worker includes an optional rate-limit binding and limits question length.
4. Enable web search with `ENABLE_WEB_SEARCH=true` when source-backed answers are required. Web search adds usage cost; OpenAI's published pricing lists web search at $10 per 1,000 calls, plus retrieved-content token usage.
5. After deployment, set the Worker HTTPS URL in `data/ai-config.json` under `endpoint`. Until this is done, the page remains disabled rather than pretending AI is connected.

The backend uses the OpenAI Responses API with `store:false`, returns source URLs when available, and labels answers without sources as AI-generated and needing verification. API model availability and pricing depend on the OpenAI API project. The Assistants API was sunset on 26 August 2026; new integrations should use Responses.

## Current validation boundary

JavaScript syntax and local database invariants are checked after code changes. This repository has not been authenticated to a Cloudflare account, no API key has been supplied, and the Worker has not been deployed or live-tested. GitHub Pages deployment and the actual mobile browser experience must still be checked after deployment.


## Licensing and data sources

The standard MIT License covers original software code authored by the
Deutschly maintainer, to the extent the relevant rights are held. The A1
German–Bangla vocabulary database is independently created and curated by the
maintainer. See [LICENSE-NOTICE.md](LICENSE-NOTICE.md), [DATA-LICENSE.md](DATA-LICENSE.md),
and [DATA-SOURCES.md](DATA-SOURCES.md) for data licensing, authorship, and
third-party material boundaries. The external Keks audio recording is excluded from the CC BY 4.0 grant.
