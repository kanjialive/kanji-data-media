Kanji-alive
===========

[_Kanji alive_][1] is a free resource for learning to read and write kanji. With few exceptions, this repository includes all of the language data and media files used by the _Kanji alive_ [website][2] and web application ([http://app.kanjialive.com][3]). 

The files will primarily be of interest to instructors and studenst who want to re-use them for teaching and learning purposes. Developers should make use of the _Kanji alive_ public web API which will be made available in Summer, 2015. 

[Subscribe][4] to the news page on our website or [follow us on Twitter][5] for the latest updates.

Language Data
---- 
A CSV file with all of the publically available language data used in _Kanji alive_. It is necessary to reference this file in order to match individual kanji characters to the naming scheme used for the media files in this repository. For additional details, please see the README file in the language-data directory.

Due to copyright restrictions, the mnemonic hints shown in the ‘Detail View’ of the _Kanji alive_ web application as well as the organization of kanji into lessons/chapters by textbook publishers are not included.

Examples Audio
---- 
Audio files of the pronuciations of 6-12 common compound words for each supported kanji, in the listed order of their Onyomi and Kunyomi pronunciations in _Kanji alive_. The words are spoken by male and female native Japanese speakers. 32Khz, mono, AAC audio files.

Kanji Animations
---- 
Kanji stroke order animations hand-written by native Japanese writers on a Wacom Cinqtiq tablet. The videos were captured as 15fps QuickTime movies and converted into 248x248, H.264 encoded MP4 files.  

Kanji Strokes
---- 
Individual SVG images of each completed stroke in a kanji stroke order animation in ascending strole prder. The SVG files were created with potrace from PNG images exported from the kanji stroke order animations.

Radical Animations
---- 
SVG image files showing the initial, middle and final images of the three-part animations of each radical illustrating its historical derivation. The SVG files are based on a variety of original vector image files.  

Radical Characters
---- 
SVG image files of every radical character used in _Kanji alive_. The characters are in the Kyokashotai typeface. 

Radical Positions
---- 
SVG image icons illustrating the different positions a radical can take in a kanji character.

Radicals Font
---- 
A small (54KB), custom OTF font with full support for all Japanese radicals and their variants (321 characters). EOT, TTF, SVG and WOFF versions can be found in the webfonts sub-directory. In addition, further information is provided on the radicals present in the font, their encodings, stroke numbers, meanings, readings and positions. 

[1]:	http://kanjialive.com
[2]:	http://kanjialive.com
[3]:	http://app.kanjialive.com
[4]:	http://kanjialive.com/feed/
[5]:	https://twitter.com/kanjialive