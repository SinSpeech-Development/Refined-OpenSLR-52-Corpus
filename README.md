# Refined-OpenSLR-52-Corpus

This repository contains a refined set of transcriptions of a speech corpus for Sinhala.

> Our goal is to provide a **clean** speech corpus for Sinhala, which is **readily-usable** with ASR toolkits.

We have used an open-source Sinhala speech corpus titled "Large Sinhala ASR training data set" [published](https://www.researchgate.net/publication/328067279_Crowd-Sourced_Speech_Corpora_for_Javanese_Sundanese_Sinhala_Nepali_and_Bangladeshi_Bengali) by Google. The complete dataset is available [here](https://openslr.org/52).

By going through the transcriptions, we have identified two kinds of issues:
1. Issues related to textual characters
2. Issues related to linguistics

We have addressed the above issues by following a *systematic approach* of filtration and correction. The tasks done for each kind of issue are listed below.
### Issues related to textual characters
- Removing punctuation marks (e.g. **. , / " " : -**)
- Excluding utterances which contain English characters
- Replacing numerical characters with their textual forms
- Removing unnecessarily applied non-printable characters (e.g. ZWJ, NZWJ, ZWSP)

### Issues related to linguistics
- Applying spelling corrections on misspelled words
- Applying a consistent way of spacing between words, complying with Sinhala grammar

When applying the refinements, certain transcriptions were excluded because, in each such utterance, the speaker has spoken words incorrectly as those words have been misspelled in the original transcription (i.e. prompt). The statistics of the corpus after applying refinements and corresponding transcription files are listed in the below table.
| Version identifier  | Description | Total utterances | Unique utterances | Unique words |
| ------------- |------------- | ------------- | ------------- | ------------- |
| [V0](https://github.com/SinSpeech-Development/Refined-OpenSLR-52-Corpus/blob/master/V0.tsv) | Original, unmodified  | 185,293 | 102,576 | 69,581 |
| [V1](https://github.com/SinSpeech-Development/Refined-OpenSLR-52-Corpus/blob/master/V1.csv) | Corrected textual characters | 178,409 | 98,435 | 63,376 |
| [V2](https://github.com/SinSpeech-Development/Refined-OpenSLR-52-Corpus/blob/master/V2.csv) | Applied lingustic corrections on V1 | 178,096 | 98,127 | 57,029 | 

In addition to the above refinements, we have also tagged each speaker with his/her gender, as that information is required by ASR toolkits like [Kaldi](https://kaldi-asr.org/). The speaker to gender mapping is contained in [this file](https://github.com/SinSpeech-Development/Refined-OpenSLR-52-Corpus/blob/master/Gender%20Information.csv).

We have developed Python scripts to automate most of the steps of the refinement process. Those scripts can be accessed in [this repository](https://github.com/SinSpeech-Development/Corpus-Cleaning).
