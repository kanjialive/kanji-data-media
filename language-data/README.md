### Formats

The *Kanji alive* language data files are offered in UTF-8 encoded, .csv (comma-delimited) and in Microsoft Excel (.xlsx) formats.

### Kanji alive data (*ka_data.csv* and *.xlsx*)

This contains all of the language data used by the *Kanji alive* web application (https://app.kanjialive.com) with the following exceptions: For copyright reasons, it does not include data on the mnemonic hints and the (Classic) Nelson and Kodansha dictionary indices for each kanji seen in the app's "detail" view or data on the division of kanji into chapters/lessons for [textbooks supported](http://kanjialive.com/supported-textbooks/) in the "search & results" view.

Some kanji have no kunyomi or onyomi reading at all (e.g. 法 has no kunyomi).
These are recorded with an empty kana cell and the value "n/a" in the matching romaji cell.

Note that in order to make use in particular of the [kanji animation](https://github.com/kanjialive/kanji-data-media/tree/master/kanji-animations) and [example audio](https://github.com/kanjialive/kanji-data-media/tree/master/examples-audio) media, you will need to match the kanji character you are looking for (e.g. 述) with the unique, romanized name we assigned to it when we created its filename, e.g. jutsu-no(beru).
In the case of the example audio files, the filenames were additionally marked (in alphabetical order) with the letters 'a' to 'l' to match them to their respective readings.
For example, there are 10 audio files starting with "jutsu-no(beru)" and ending with [a-j] plus the format's extension (.opus, .aac, .ogg or .mp3).
These are the audio files for the 10 readings (in the same order) for this kanji.

Please note also that some of the radical characters in the spreadsheet are not defined in Unicode and had to be assigned PUA (private use area) encodings.
To view these characters correctly, you will first have to install our custom [Japanese Radicals](https://github.com/kanjialive/kanji-data-media/tree/master/radicals-font) font.

### Japanese Radicals data (*japanese_radicals.csv* , *.xlsx* and .pdf)

The data in *japanese_radicals* is a superset of that found in *ka_data* since it covers all of the 214 traditional radicals – not just those found in the 1235 kanji supported by the Kanji alive web application.
Second, it includes columns indicating whether a radical is a variant of a base radical and whether it belongs to the category of the most important radicals.
This information can be viewed in use on the [214 traditional kanji radicals](http://kanjialive.com/214-traditional-kanji-radicals/) page on our website.

As with *ka-data*, please note also that some of the radical characters in the spreadsheet are not defined in Unicode and had to be assigned PUA (private use area) encodings.
To view these characters correctly you will first have to install our custom [Japanese Radicals](https://github.com/kanjialive/kanji-data-media/tree/master/radicals-font) font.
The PDF version bundles this font and can be used 'as is'.

To match a radical with its media files in [radical-characters](https://github.com/kanjialive/kanji-data-media/tree/master/radical-characters) and [radical-animations](https://github.com/kanjialive/kanji-data-media/tree/master/radical-animations), use its *Reading-R* value as the base of the filename.
The one wrinkle is where two different radicals with media files share a reading: there, one of the pair carries an English suffix for disambiguation, in both the character and the animation filenames:

| Radical | Reading-R | Filenames use |
| ------- | --------- | ------------- |
| ⼄ (the second) | otsu | otsu-nine (plain "otsu" is its variant ⺃) |
| ⽕ (fire) | hi | hi-fire (plain "hi" is ⽇, sun) |
| ⽕ as へん | hihen | hihen-fire (plain "hihen" is ⽇ as へん) |
| ⾔ (words) | gen | gen-word (plain "gen" is ⽞, darkness) |
| ⻩ (yellow) | ki | ki-yellow (plain "ki" is ⽊, tree) |

### Japanese Radicals IDs (*japanese-radicals-ids.csv*)

A machine-readable companion to *japanese-radicals.csv* for anyone using it as a dataset rather than a reference to read or print. It has the same rows in the same order, adding what the main file leaves out:

- *ID* — a stable integer key for each row (the main file identifies rows only by radical character and reading).
- *Kangxi#* — the traditional 1–214 radical number, on base radicals.
- *Codepoint* — the radical character's Unicode codepoint (U+2Fxx for the Kangxi block, U+E7xx for our PUA-encoded characters), for exact matching without Unicode-normalization surprises.
- *Variant-of-ID* — the *Variant-of* link expressed as an ID reference instead of a character + reading pair.

It is generated from *japanese-radicals.csv* and carries no data of its own beyond the IDs; the main file remains the source of truth.

### Recent Changes

#### September 2026

Media and timing files brought into step with the *Kanji alive* web application:

- 状: the stroke-order animation (in *animations-mp4.zip*) and the images of strokes 1–3 (in *kanji_strokes.zip*) now show the corrected stroke order, as on the website since 2020.
- Stroke timings (*kanji-animations/stroke_timings*): 17 files replaced with the values used by the web application. 状 gains the timings for its corrected first strokes; 話 was empty; the rest carried unnormalised or outdated values.

#### August 2026

The following corrections were made to both spreadsheets (in their .csv and .xlsx versions) and, where applicable, to the database used by the *Kanji alive* web application.

_**ka_data:**_

| Change                                                                                                                                                      | Rows |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ---- |
| 薄: onyomi kana corrected from ハス to ハク                                                                                                                      | 1    |
| 解, 断, 造: romaji typos corrected ("takasu" → "tokasu", "korowa" → "kotowa", "tukuri" → "tsukuri")                                                            | 3    |
| 納, 坊: rare onyomi removed (納: ナツ "nat"; 坊: ボツ "bot")                                                                                                        | 2    |
| 染: last kunyomi romaji corrected from "jimiru" to "shimi", matching its kana しみ                                                                             | 1    |
| 凍: first kunyomi corrected from こ to こお ("ko" → "koo")                                                                                                      | 1    |
| 優: kunyomi やさし completed to やさしい ("yasashi" → "yasashii")                                                                                                   | 1    |
| 告: literary kunyomi つぐ ("tsugu") removed                                                                                                                    | 1    |
| 法, 合, 以, 三: readings with a doubled consonant now written with small っ/ッ — 法 ハッ、ホッ ("hat, hot"), 合 カッ、ガッ ("kat, gat"), 以 adds もっ ("mot"), 三 adds みっ ("mit") | 4    |
| Stray space before a comma removed from an example meaning for each of 吸, 迷, 囲, 乾, 鳴, 辛 and 幹 (e.g. "cigarette end , tobacco ashes")                        | 7    |

_**japanese-radicals:**_

The *japanese-radicals* files (.csv, .xlsx and .pdf) were rebuilt from the [214 traditional kanji radicals](http://kanjialive.com/214-traditional-kanji-radicals/) table on our website:

- The files now cover all 214 traditional radicals and their variants (321 rows), not only the radicals of the 1235 kanji supported by the web application.
- New columns: *Importance* (marks the most important radicals to learn), *Origin* (identifies the base Kangxi radicals), and *Variant-of* / *Variant-of-Reading* (link each variant form to its base radical).
- Removed columns: *Radical ID#*, *R-Filename* and *Anim-Filename*; *Reading-J* is now named *Reading*.
- Trailing non-breaking space removed from the Radical character 𦉰 (amiguchi)
- The repetition symbol 々, not one of the 214 traditional radicals, is no longer listed.
- New companion file *japanese-radicals-ids.csv*: stable row IDs, Kangxi numbers, Unicode codepoints, and *Variant-of* as an ID reference (see above).

#### July 2026

The following corrections were made to both spreadsheets (in their .csv and .xlsx versions alike), bringing them back into agreement with the language data used by the *Kanji alive* web application.

_**ka_data:**_

| Change                                                                                                                                       | Rows |
| -------------------------------------------------------------------------------------------------------------------------------------------- | ---- |
| 画: radical corrected from ⼐（かんにょう）to ⽥（た）, together with its dependent radical fields (radical number, strokes, name, meaning and position)  | 1    |
| 可: missing kanji meaning added ("able, approve")                                                                                             | 1    |
| 貯: kanji meaning corrected from "lay-up, storage, store" to "lay up, storage, store"                                                         | 1    |
| 々: placeholder "n/a" values removed from the kunyomi and radical name/meaning fields (now blank); radical strokes normalised to "n/a"        | 1    |
| Trailing whitespace removed from radical meanings ("person", "the second"), the radical character ⼌ and three example words (for 一, 九 and 簡) | 72   |

_**japanese-radicals:**_

| Change                                                                                                                   | Rows |
| ------------------------------------------------------------------------------------------------------------------------ | ---- |
| 々 (ID 322): placeholder "n/a" values removed from Meaning, Reading-J and Reading-R (now blank); R-Filename set to "none" | 1    |
| Trailing whitespace (non-breaking spaces) removed from Meaning (IDs 6, 12, 13) and Radical (ID 18)                       | 4    |
| Meaning of ⼸ and its variant corrected from "bow （in archery）" to "bow（in archery）" (IDs 76, 77)                         | 2    |

### Data Provenance

None of the language data presented here is dependant on or derived from Jim Breen's [Electronic Dictionary Research and Development Group](http://www.edrdg.org) datasets (i.e. on JMDICT/EDICT, KANJIDIC and KRADFILE/RADKFILE).

The language data on kanji was compiled by native Japanese instructors and graduate students at the University of Chicago, largely between 2002 and 2005 (see [Credits](http://kanjialive.com/credits/)) with reference, as needed, to Jack Halpern, "The Kodansha Kanji Learner’s Dictionary", 1st ed.
1999, Kodansha, and Andrew N. Nelson, "The Original Modern Reader’s Japanese-English Character Dictionary: Classic Edition", 2nd.
ed.
(1974), Tuttle Publishing.

The language data on radicals draws on the following references: For the English meanings of each radical, "Kanji & Kana" by Wolfgang Hadamitzky & Mark Spahn, (1981), Tuttle Publishing with additional reference to "Basic Kanji" by Matsuo Soga & Michio Yusa (1989), Taishūkan, and Andrew N. Nelson, "The Original Modern Reader’s Japanese-English Character Dictionary: Classic Edition", 2nd.
ed.
(1974), Tuttle Publishing.
For the Japanese names for the radicals,『講談社カラー版日本語大辞典』（第一版）1989, 講談社.

All of the language data in *Kanji alive* was reviewed and revised by Harumi Hibino Lory, now emerita at the University of Chicago.
