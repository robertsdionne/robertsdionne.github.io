---
layout: post
title:  "Reading and Writing Electronic Text: Homework #1"
description: "My personal goal for homework #1 was to be able to mutate a given text using n-gram
statistics gathered from a set of onomatopoeias. Thus, I needed two components: one that gathered
n-gram statistics from any text, and another that applied the given statistics to mutate a new
text."
date:   2014-02-14 22:34:00
categories: rwet
---
My personal goal for homework #1 was to be able to mutate a given text using n-gram statistics
gathered from a set of [onomatopoeias](http://en.wikipedia.org/wiki/Onomatopoeia). Thus, I needed
two components: one that gathered n-gram statistics from any text, and another that applied the
given statistics to mutate a new text. I'm interested in how the [sound symbolism](http://en.
wikipedia.org/wiki/Sound_symbolism) of onomatopoeias might alter the experience of traditional
texts.

I found, on Wikipedia and Wiktionary, [lists of onomatopoeias](http://en.wiktionary.org/wiki/
Category:Onomatopoeias_by_language) and [ideophones](http://en.wikipedia.org/wiki/Ideophone) in
several languages, so I created two text files, [onomotopoeia.txt](https://github.com/robertsdionne/
rwet/blob/master/texts/onomotopoeia.txt) and [onomotopoeia_latin.txt](https://github.com/
robertsdionne/rwet/blob/master/texts/onomotopoeia_latin.txt), to scan for n-gram statistics. I used
a model with unigrams up to 5-grams to mutate sea_rose.txt into several alternate texts.

My homework #1 implementation includes two programs: ngram.py and hw1.py. A description of what each
program does, what kinds of input each program expects, and what kinds of output each produces can
be found in the [README](https://github.com/robertsdionne/rwet/tree/master/hw1#readme) on my github
page for homework #1.

[reading3.txt](https://github.com/robertsdionne/rwet/blob/master/hw1/reading3.txt) generated with
mutation probability = 0.5

    StA nOSt

    ahslo harsh host,
    oucred nod wubb staxt ow neracsö
    mealae nlowee, hhing
    spate nf lisf,

    mote noeepous
    ohan p bet rosh

    sizzle ow a yaem -c
    yau aae caught in the nortt.

    Stridel, nido voalk hearb
    you ate fleba ya the sand,
    pli at- liftsí
    ił the croak sing
    tuau drarrs ip tle wing-

    Cam thu gpococrune
    mrip sick aprtd googlunke
    haruealk nn a lídf?

[reading4.txt](https://github.com/robertsdionne/rwet/blob/master/hw1/reading4.txt) generated with
mutation probability = 1.0

    spl choo

    irlop bleep bleep
    afoodl don nort yadat po gattjom
    nackle nortysc gaili
    -bang do hoo-c

    owle nortysch
    kráa g don gooe
    barkla ga g dong po
    ppe nor pongho ho voe nortys

    iizhiiłc vovo vovov yada,
    otm nom nomng po hoo choo,
    iue nor yadaep
    li nom nomss yada
    dula yadaee no vov dongl

    ako cho hooppety-c
    aper nomh nomia gaashoote
    epingnud bl d dongy

[reading5.txt](https://github.com/robertsdionne/rwet/blob/master/hw1/reading5.txt) generated with
mutation probability = 0.9

    ew- hoop

    arlo, homsc gaspe
    sirrup arl gooh yadat ch pongle-
    umperi gaoffaw thudo
    licky ho hoosh

    ucho chooieko
    dóli n nor nort
    murous ya y stle no
    yow vov nomght nn don nortys

    owubble- homh gaakk perik
    avo voe norty no gae norty
    oou gae lishoo
    væ cho choo- dant
    wcho gailos ya yad yada.

    pia yad nortyschsl
    wlop blee nortd hoo-chooe
    hahahaea ya a gaaha
