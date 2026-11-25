# Fonts used when editing text

Folio uses these to make edited text match the document (on screen and in the saved PDF). The website downloads a
font only the first time a document needs it; the Android app includes them all.

| Font | Matches | Licence | Copyright |
|---|---|---|---|
| Liberation Sans 2.1 | Arial, Helvetica | SIL OFL 1.1 (OFL.txt) | (c) 2010 Google Corporation, (c) 2012 Red Hat, Inc. |
| Liberation Serif 2.1 | Times New Roman | SIL OFL 1.1 (OFL.txt) | same |
| Liberation Mono 2.1 | Courier New | SIL OFL 1.1 (OFL.txt) | same |
| Carlito | Calibri | SIL OFL 1.1 (OFL.txt) | (c) 2010-2013 tyPoland Lukasz Dziedzic |
| Caladea | Cambria | Apache 2.0 (Caladea-LICENSE-Apache-2.0.txt) | (c) 2012 Huerta Tipografia |

`fontkit.umd.min.js` is @pdf-lib/fontkit 1.1.1 (MIT, fontkit-LICENSE.txt): it lets pdf-lib put these fonts into the
saved PDF. Fetched from npm by .github/workflows/fetch-fontkit.yml.

The Carlito files are trimmed (fontTools pyftsubset: Latin, Greek, Cyrillic, punctuation, symbols; hinting removed)
because pdf-lib can't subset Carlito correctly, so Folio puts the whole (trimmed) file into saved PDFs (~130 KB per style).
The other fonts are the unchanged releases and are subset when saved.
