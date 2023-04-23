# Introduction

The LIA Treebank and The NDC Treebank are two Norwegian treebanks with dialect transcriptions from about the same 17 places in Norway, transcribed in Nynorsk and Bokmål respectively.  Both treebanks are annotated in the same way with part-of-speech morphological features and dependency-style syntactic analysis.

## The LIA Treebank

The LIA Treebank includes 7536 speech segments and 77 701 tokens from the Nynorsk transcriptions in the corpus LIA Norwegian. The treebank is annotated with morphological and dependency-style syntactic analysis and manually corrected. The treebank is available in three versions:

* A downloadable version in conllx format is found in the folder /treebanks/Norwegian-NynorskLIA/ with a Creative Commons license.
* A searchable version in the Glossa search interface.
* A downloadable version in conllu format with a Creative Commons license. This version is automatically converted to Universal Dependencies. The conllu version contains 5250 speech segments and 55 410 tokens. Download the conllu version

The segments in the treebank are taken from 19 transcribed LIA Norwegian recordings from 17 different places in Norway: Aaustevoll, Bardu, Brandbu, Eidsberg, Fana, Lista, Flakstad, Førde, Giske, Gol, Hemsedal, Herad, Hjartdal, Høyanger, Nordli, Vardø and Ål.

The annotations follow the guidelines for [The Norwegian Dependency Treebank](https://aclanthology.org/L14-1273/ "The Norwegian Dependency Treebank") and [NDT Guidelines for Morphological and Syntactic Annotation.](https://www.nb.no/sbfil/dok/20140314_guidelines_ndt_english.pdf) For certain speech specific features that are not mentioned in the NDT guidelines, the LIA Treebank extend this annotation scheme.

The annotation of the treebank is done automatically, but is manually corrected by at least one person using the annotation tool TreD.

## The NDC Treebank

The NDC Treebank contains 4637 speech segments and 66 042 words/tokens from the Bokmål transcriptions in the Norwegian part of Nordic Dialect Corpus. The treebank is manually corrected and is annotated with morphological and dependency-style syntactic analysis. The NDC Treebank is available in two versions:

* A downloadable version in conllx format is found in the folder /treebanks/Norwegian-BokmaalNDC/ with a Creative Commons license
* A searchable version in the Glossa search interface: Search the NDC Treebank

The segments in the treebank are taken from 30 transcribed NDC recordings from 17 different places in Norway: Bergen, Bømlo, Flå, Herøy in Møre and Romsdal, Hjartdal, Hyllestad, Jevnaker, Jølster, Kirkesdalen, Lierne, Lyngdal, Rømskog. Sokndal, Stamsund, Trondheim, Vardø and Ål in Hallingdal.

As far as possible, the annotations follow the guidelines for LIA as well as the mentioned [The Norwegian Dependency Treebank](https://aclanthology.org/L14-1273/ "The Norwegian Dependency Treebank") and [NDT Guidelines for Morphological and Syntactic Annotation.](https://www.nb.no/sbfil/dok/20140314_guidelines_ndt_english.pdf)

The annotation of the treebank is done automatically, but is manually corrected by at least one person using the annotation tool [ConlluEditor](https://github.com/Orange-OpenSource/conllueditor "ConlluEditor").

# Evaluation

In order to quantify the parsability i.e. the quality that can be induced by a parser based on the annotations of the treebanks we partitioned each of them in n folds and performed a n-fold cross validation with n=5 given the size of the treebanks. The following results for the baseline parsers are as follows

| Treebank   | UAS    | LAS    |
|---------------|:-------:|--------:|
| LIA                | 85.23 | 80.01 |
| NDC             | 84.11 | 78.43 |

Both the UAS and LAS is the mean of the five folds. All training and evaluation is done with the [uuparser](https://github.com/UppsalaNLP/uuparser "uuparser").

# Run

For running prediction with a parser: 1) Clone the [uuparser](https://github.com/UppsalaNLP/uuparser "uuparser") repo, 2) install requirements and 3) use the command below

```console
uuparser --predict --testfile parsers/clarino/lia/lia_1.conllu --modeldir parsers/clarino/lia/2_3_4_5/ --outdir [path to write results]
```

# Acknowledgements

The development of the LIA Treebank and the NDC Treebank are financed by the Norwegian Research Council in two infrastructure projects: LIA and Clarino+

Many researchers, engineers and part-time students have worked on the different parts of these projects -- a huge thanks to them all.

# References

Lilja Øvrelid, Andre Kåsen, Kristin Hagen, Anders Nøklestad, Per Erik Solberg and Janne Bondi Johannessen. 2018. The LIA Treebank of Spoken Norwegian Dialects. In Nicoletta Calzolari et al.: Proceedings of the Eleventh International Conference on Language Resources and Evaluation.

Andre Kåsen, Kristin Hagen, Anders Nøklestad, Joel Priestley, Per Erik Solberg and Dag Trygve Truslew Haug. 2022. The Norwegian Dialect Corpus Treebank. In Nicoletta Calzolari et al.: Proceedings of the Thirteenth Language Resources and Evaluation Conference.

