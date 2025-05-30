![Version](https://img.shields.io/github/v/release/DCMLab/liszt_pelerinage?display_name=tag)
[![DOI](https://zenodo.org/badge/379678214.svg)](https://doi.org/10.5281/zenodo.7473580)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/liszt_pelerinage)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/liszt_pelerinage](https://github.com/DCMLab/liszt_pelerinage) and the corresponding
* documentation page [https://dcmlab.github.io/liszt_pelerinage](https://dcmlab.github.io/liszt_pelerinage)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/liszt_pelerinage/introduction).

When you use (parts of) this dataset in your work, please read and cite the accompanying data report:

_Hentschel, J., Rammos, Y., Neuwirth, M., Moss, F. C., & Rohrmeier, M. (2024). An annotated corpus of tonal piano music 
from the long 19th century. Empirical Musicology Review, 18(1), 84–95. https://doi.org/10.18061/emr.v18i1.8903_

This corpus forms part of the larger [Distant Listening Corpus](https://github.com/DCMLab/distant_listening_corpus)
which constitutes a data infrastructure the data report of which has implications for the present corpus, too:

_Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the 
empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z_

# Franz Liszt – Années de Pèlerinage (A corpus of annotated scores)


## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/liszt_pelerinage/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [liszt_pelerinage.zip](https://github.com/DCMLab/liszt_pelerinage/releases/latest/download/liszt_pelerinage.zip)
  * [liszt_pelerinage.datapackage.json](https://github.com/DCMLab/liszt_pelerinage/releases/latest/download/liszt_pelerinage.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/liszt_pelerinage.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first piece has the following files:

* `MS3/160.01_Chapelle_de_Guillaume_Tell.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/160.01_Chapelle_de_Guillaume_Tell.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/160.01_Chapelle_de_Guillaume_Tell.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/160.01_Chapelle_de_Guillaume_Tell.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/160.01_Chapelle_de_Guillaume_Tell.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/160.01_Chapelle_de_Guillaume_Tell.harmonies.tsv")
notes = ms3.load_tsv("notes/160.01_Chapelle_de_Guillaume_Tell.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/liszt_pelerinage/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/liszt_pelerinage/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Hentschel, J., Rammos, Y., Neuwirth, M., Moss, F. C., & Rohrmeier, M. (2024). An annotated corpus of tonal piano music from the long 19th century. Empirical Musicology Review, 18(1), 84–95. https://doi.org/10.18061/emr.v18i1.8903

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## File naming convention