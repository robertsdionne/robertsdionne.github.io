---
layout: post
title:  "Reading and Writing Electronic Text: Final Project"
date:   2014-04-30 20:38:00
tags: rwet
---
**Reading Between the Lines with word2vec**

Within the natural language processing research community, researchers are exploring new
representations for words derived from statistical properties of texts. One such representation is
the distributed word vector, an n-dimensional quantity that somehow captures information about the
meaning of a word in relation to all other words. An example of what a word vector might look like
is x = [0.4, 0.8, 0.1, -0.2, …, 0.03].

Distributed word vectors can be computed in several ways:

* by training a neural network to recognize when a word actually appears within a sentence from
Wikipedia versus when it has been swapped into a random sentence from Wikipedia. ([Collobert and
Weston 2008](http://ronan.collobert.com/pub/matos/2008_nlp_icml.pdf))
* by training a logistic regression model called a continuous bag-of-words model that predicts a
word as a mixture of the words around it within training sentences ([Mikolov et al. 2013](http://
arxiv.org/pdf/1301.3781.pdf))
* by training a logistic regression model called a skip-gram model that predicts the neighboring
words around a word within training sentences ([Mikolov et al. 2013](http://arxiv.org/pdf/
1301.3781.pdf))

The n-dimensional vector representations for words turn out to have interesting properties
([Mikolov et al. 2013](https://www.aclweb.org/anthology/N/N13/N13-1090.pdf)). For instance,
analogies can be expressed as approximate vector addition and subtraction operations. Thus, the
following hold true:

* kings - king + queen ~= queens (plurality)
* Paris - France + Germany ~= Berlin (quality of being a capitol city)
* red + fruit ~= apple (mixture of words)

Furthermore, similar words have similar vector representations and can be compared with their dot
product. As an example, hello ~= howdy.

Encouragingly, Tomas Mikolov and others have released an open source project called
[word2vec](https://code.google.com/p/word2vec/) along with [pretrained word vector data](https://
drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit?usp=sharing) that allows anybody to
experiment with this method of representing words.

For my final project, I wanted to explore how I could use word2vec and its word vector
representations to create generative poetry. I began by figuring out how to load the word vector
data to a Python program using the [numpy](http://www.numpy.org) library. Once I was able to query
the nearest words to a given word, I began exploring what form would best exploit the interesting
properties of word vectors.

I decided that being able to mix two words together and find the closest word to the mixture was an
interesting basis for generative poetry. I then asked myself how I could decide which words to mix
together within a source text. After several iterations, I decided that I should simply mix every
pair of words together from two lines of source text, a couplet.

The resulting form yields a matrix of word mixtures. For each word in the first line, and for each
word in the second line, the first and second words' vector representations are added together to
search for the 100 closest matches. Then one of the matches is chosen to fill in that grid location
in the matrix.

The resulting poem transforms the initial line into several modified rows warped by each word in the
second line. It also transforms the second line into several modified columns warped by each word in
the first line. Thus, it can be read either horizontally or vertically. The new words swapped into
the generated lines are determined both by mixture and by randomness, because I choose at random one
of the 100 closest words to the mixture of the two original words.

Sometimes a given word in the input text does not appear within the word2vec database. I used a 3.6
gigabyte database trained on the entire corpus of Google News, which is very large. Sometimes a word
might not appear in the database because it is extremely rare. Some proper names fall into this
category. However, I noticed that the Google News database also excludes very common words, such as
"the," "of," or "and." When input words are not present in the database, my poetry generator ends up
choosing random synonyms for the other words mixed with the missing word instead of mixing two words
together, but the result is sometimes interesting given the vast size of the database.

All of my generated poems can be visited [here](http://robertsdionne.github.io/rwet/final). I
rendered the matrix of word mixtures to an HTML table and changed the background of each cell in the
table so that darker cells indicate a closer match between the chosen word and the mixture of the
row and column headings.

Here is one example generated from a couplet of Emily Dickinson: [robertsdionne.github.io/rwet/
final/reading8g.html](http://robertsdionne.github.io/rwet/final/reading8g.html)

And another generated from a couplet of William Faulkner's Light in August: [robertsdionne.github.
io/rwet/final/reading9a.html](http://robertsdionne.github.io/rwet/final/reading9a.html)

[README](https://github.com/robertsdionne/rwet/tree/master/final#readme)
