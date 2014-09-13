---
layout: post
title:  "Reading and Writing Electronic Text: Midterm Project"
date:   2014-03-27 16:20:00
tags: rwet
---
My midterm project devises a new form of electronic poetry called **dead language poetry** in which
one finds an ancient, untranslated or untranslatable text and attempts to generate rhythmically
plausible translations in another language: here English.

I've created a Python program that generates texts conforming to this form by examining digital
transcriptions of the [Voynich Manuscripts](http://www.jasondavies.com/voynich) and reconstructing a
translation of the manuscripts using lines remixed from a different source text.

The program has several components:

* [cleanup_text.py](https://github.com/robertsdionne/rwet/blob/master/midterm/cleanup_text.py):
preprocesses source texts to split them at punctuation boundaries to produce one phrase per line.
* [cmudict_to_json.py](https://github.com/robertsdionne/rwet/blob/master/midterm/
cmudict_to_json.py): preprocesses the [cmudict](http://www.speech.cs.cmu.edu/cgi-bin/cmudict)
pronunciation dictionary into the more easily readable [JSON](http://www.json.org) format.
* [process_voynich.py](https://github.com/robertsdionne/rwet/blob/master/midterm/
process_voynich.py): extracts a consistent transcription of the Voynich Manuscripts from the
[transcription data file](http://www.ic.unicamp.br/~stolfi/voynich/98-12-28-interln16e6/
text16e6.evt).
* [translate.py](https://github.com/robertsdionne/rwet/blob/master/midterm/translate.py): Chooses
phrases from the source text that could be plausible rhythmic translations of lines from the Voynich
Manuscript by examining consonant and vowel rhythms from each phrase.

Specifically, translate.py examines each line of the Voynich Manuscript input, generates a plausible
set of phonemes for each word in a line and converts the phonemes into a sequence of consonant and
vowel markers:

> fachys ykal ar ataiin shol shory cth res y kor sholdy
> 
> F-AE0-CH-EY0-EH1-S&nbsp;&nbsp;&nbsp;&nbsp;EY0-K-AE1-L&nbsp;&nbsp;&nbsp;&nbsp;AA1-R&nbsp;&nbsp;
> &nbsp;&nbsp;AE0-T-AE0-AY0-EH1-N&nbsp;&nbsp;&nbsp;&nbsp;SH-OW0-EH1-L&nbsp;&nbsp;&nbsp;&nbsp;
> SH-AO1-R-IY0&nbsp;&nbsp;&nbsp;&nbsp;S-T-IY1-EY1-CH&nbsp;&nbsp;&nbsp;&nbsp;R-EY1-Z&nbsp;&nbsp;&nbsp;
> &nbsp;W-AY1&nbsp;&nbsp;&nbsp;&nbsp;K-AO1-R&nbsp;&nbsp;&nbsp;&nbsp;SH-OW0-L-D-W-AY1
>
> CVCVVC VCVC VC VCVVVC CVVC CVCV CVVC CVC CV CVC CVCV

Then, the program selects the most similar line from the source text to serve as the translation by
comparing the consonant and vowel representation for the line in the source text to the representation for the ancient line. The representations are compared using [edit distance](http://en.wikipedia.org/wiki/Edit_distance):

> CVC CV CVC CV**V**V**C** CVC CV**V**VC
> 
> CVC CV CVC CV**CV** CVC CV**C**VC

I've generated three candidate poems that I found satisfactory:

* [f1r_lightinaugust](http://robertsdionne.github.io/rwet/midterm/f1r_lightinaugust.html): a
combination of [folio f1r](http://www.jasondavies.com/voynich/#f1r/0.5/0.5/2.50) and William
Faulkner's [Light in August](http://en.wikipedia.org/wiki/Light_in_August).
* [f39v_rosettastone](http://robertsdionne.github.io/rwet/midterm/f39v_rosettastone.html): a
combination of [folio f39v](http://www.jasondavies.com/voynich/#f39v/0.5/0.5/2.50) and an [English
translation](https://github.com/robertsdionne/rwet/blob/master/midterm/text/rosettastone.txt) of the
[Rosetta Stone](http://en.wikipedia.org/wiki/Rosetta_Stone).
* [f81r_odyssey](http://robertsdionne.github.io/rwet/midterm/f81r_odyssey.html): a combination of
[folio f81r](http://www.jasondavies.com/voynich/#f81r/0.5/0.5/2.50) and Homer's
[Odyssey](http://en.wikipedia.org/wiki/Odyssey).

**How well does the output of my computer program conform to my invented poetic form?**

The output conforms relatively well, however there are almost no perfect matches for rhythmic
translations. Most lines are different by 5-10 phonemes but some flexibility enhances the illusion
of the translation being legitimate.

**Could a human do it better?**

Yes, a human would have greater control over the theme and content of the translation, and would
probably be able to match the rhythm 100% phoneme for phoneme.

Also, sometimes, especially with shorter source texts, the translations can be repeated when a
particular line matches many ancient lines in terms of rhythm. A human can completely avoid this
obvious error.

**How does my choice of source text (my “raw material”) affect the character and quality of the
poems that your program generates?**

I chose the Rosetta Stone text because the resulting translations were very convincing since both
the Voynich Manuscript and the Rosetta Stone are ancient relative to modern day.

I chose the Odyssey text because it also matched the time period of an ancient text, however the
story-like quality of the Odyssey doesn't match my expectations of what a translation of the Voynich
Manuscript would be, so it provides an interesting juxtaposition.

I chose Faulkner's Light in August precisely for its stark contrast, being a more modern text. The
juxtaposition of the two texts combined with the oddly consistent mixture of Faulkner's lines lead
to a surprising result.

See the [README](https://github.com/robertsdionne/rwet/tree/master/midterm#readme) on github.
