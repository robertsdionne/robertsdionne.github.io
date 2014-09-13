---
layout: post
title:  "Reading and Writing Electronic Text: Homework #3"
description: "My goal for homework #3 was to combine both homeworks #1 and #2 into a set of reusable
classes."
date:   2014-04-10 12:54:00
tags: rwet
---
My goal for homework #3 was to combine both homeworks #1 and #2 into a set of reusable classes.

From the code of homework #1, I created a class, **MarkovMutator**, that mutates input text given a
language model, and two child classes, **MarkovCharacterMutator** and **MarkovTokenMutator**, that
use character and token language models to mutate individual characters or individual words. I also
made a **LanguageModel** class with child classes **CharacterLanguageModel** and
**TokenLanguageModel**.

From homework #2, I created a class, **FlowingGenerator**, that indexes the lines of an input text
by their starting and ending characters and tries to string them along connecting similar starting
and ending sounds.

I modified **FlowingGenerator** so that it uses a **MarkovCharacterMutator** to mutate the
substituted words of a text with an onomatopoeia language model before they are inserted within the
output lines to connect neighboring words with similar starting and ending sounds.

Here is a resulting [reading](https://github.com/robertsdionne/rwet/blob/master/hw3/reading1.txt):

    8.

    emotional breadth,
    "he's sat-a a arb build,
    drifted dest them,
    manmovement,
    trying glassing get tootmoli into ob bed,
    Dont tt that." He was sat-a almost tearfalh his sc ceased.
    dragging gvom man neih held doonkabl leashes.
    Slowly yng gradually yom muscles sush his show were ef flat ter rigid dest tense exforb boards.
    Shhhhhhhhhhh.
    he e-neespearert the dish,
    He entimpti in nnmeupsq quiet,
    the eup planked dingobb beyond dólii in nha ammoniac cncollected dryscented dingobb beasts simn now wrrruinert then nortes snorts scsöishoopi indolent thuds.
    She ee-n not,
    That tfleba a youth,
    He each have eho or rr rather rhich have anyone,
    even ngt the er-s said.
    doomed drelinham motion,
    nondescript,
    The epompchl looked da at him.
    McEachern nkw waiting,
    "Girls!
    She er-s slip putleepet to oen now wrrruinert then neih have entertailing good time.
    Even if I cant seem muĝinniog get thiouff further riart that:
    Then nf fell later-atishal love.
    even ngt that baby.
    "Yes?
    short,
    The er-s says:
    She eamota already yokeriarawpha a fellow,
    When ner reached doonkabl lot tearfalh he stopped,
    descending girh his rope,
    erratic cawr random.
    misshapen,
    "Not tws side of Alabama.
    and Nathaniel Burrington,
    not tt trembling,
    Gen.
    No:
    out tws somewhere e-neespearert that tootmoli is burning.
    Grant's sat-a at Holly Springs,
    Standing there,
    even," Byron says.
    She e-neespearert to ot to onku up.
    peacefully,
    You ughuapapahpea all right.
    That ttlubb be ef for rraca and drelinham me.
    "Eupheus," she said,
    didn't answer.
    rhythmic,
