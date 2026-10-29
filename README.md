# German Pronunciation Verifier

A minimal, AMOLED-black search interface for checking German dictionary entries and whether structured pronunciation-audio metadata is available.

## How the current search works

1. Calls WiktApi's structured word endpoint, filtered to German entries.
2. Requires an exact normalized headword match and a German language identifier.
3. Checks the structured pronunciation fields for a file/URL reference. It does not guess from a regular expression over raw wikitext.
4. Only labels the Wiktionary entry as having an audio reference when the structured metadata check passes.
5. If the exact entry or audio metadata cannot be confirmed, it clearly says so and shows manual dictionary search links.

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
