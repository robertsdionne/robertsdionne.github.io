---
layout: post
title:  "Reading and Writing Electronic Text: Homework #2"
description: "My goal for assignment #2 was to make a cut-up method that still creates flowing text.
To create a flowing text, I employed two cut-up methods, one operating on lines and a second
operating on tokens, to connect cut-up parts by matching starting and ending sounds."
date:   2014-03-06 16:14:00
categories: rwet
---
My goal for assignment #2 was to make a cut-up method that still creates flowing text. To create a
flowing text, I employed two cut-up methods, one operating on lines and a second operating on
tokens, to connect cut-up parts by matching starting and ending sounds.

The first method scans in all the lines of a text and remembers each line by the first character in
the first word using a Python dictionary. Then, it chooses a random starting line. Once a line is
picked, it examines the line's last character, which it uses to randomly pick a connecting line. The
first and last characters of neighboring lines must match. If a suitable neighbor cannot be found,
it starts a new stanza with a new random line.

For example:

> We went to the even**t**.
>
> **T**ime knows no bound**s**.
>
> **S**ee you tomorrow.

The second method modifies the lines chosen by the first method by examining intermediate words and swapping them out with a random word from the original text that matches its first and last letters to the last letter of the previous word and first letter of the next word.

For example:

> Twitter proclaim**s** *its* **d**estiny.

becomes:

> Twitter proclaim**s** **s**unne**d** **d**estiny.

Please see the [README](https://github.com/robertsdionne/rwet/tree/master/hw2#readme) for
instructions to use hw2.py.

I chose to use [Dr. Seuss childrens' books](https://github.com/robertsdionne/rwet/blob/master/hw2/
drseuss.txt) as input because their rhythmic quality pairs well with the flowing aspect of the
generated texts.

[reading1.txt](https://github.com/robertsdionne/rwet/blob/master/hw2/reading1.txt) is an example
output:

    Eat there Eat them!
    Mike does all low work when the eating get high.
    He cleaned out that icebox as quick as a flash.
    He eight the enough He eight the roast beast!
    Then now went that the enough himself, the old liar.
    RED don't They call me Red.
    Did dark know what to do.
    Oh hello oh dear! I ish hear.
    RED BED I i in bed.
    Did does stop the old down No! The Grinch heads said,
    Duck takes licks still lakes still Luck likes.
    So he called did dog, get Then night took some red thread,
    "Did dish have any fun?
    "Now look at teeth house!

    "Put told down!" night the fish.
    He will live at our rush he eating grow waking grow.
    We eight take enough home, we will call him Clark.
    Knox on fox in socks in box.

    But thing Grinch,Who lived just to of found Did NOT!
    They yet to of fun.”
    Now, would don't tomorrow why. No one quite knows star reason.
    Not tell little eight Then Sally and I
    I in not that them with a fox.

    Fox in socks, sing game ed done, sir.
    RED don't TED dove ED dumb BED
    Do you choose to chew what too, sir?
    Rose grows.
    SEE BEE We see a bee.
    Every day, from met to there.
    Every Who down now Whoville, eight tall let the small,
    Look at me NOW!
    Would you like them
    My tongue isn't to or ribbons sir.

    Oh, how will not like it
    Thing Two and do One!
    Eleven! This is seven new.
    with himself fox?

    on night train?
    "Now would do as I say.
    You may like them.
    Mr. run Now when now. when now.
    We like our Mike, and this is why:
    You sank our ribbons ship,
    Pop guns! And dear Roller read Drums!
    So we sat that the house.
    Eat things snack with Brown and Black.
    Knox
