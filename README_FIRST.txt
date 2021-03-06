[15/09/2014]

MOSES FOR MERE MORTALS 1.23
===========================

Moses for Mere Mortals v. 1.23 is a maintenance fix to v. 1.16. It now is compatible with Ubuntu 12.04 (64b) and 
Ubuntu 14.04 (64b) and includes all the packages upon which it depends (one of which is Moses 1.0) in a new 
downloads subdirectory.

Authors
=======
* João Luís A. de C. Rosas (author of the code)
* Hilário Leal Fontes (author of the Tutorial; many very helpful suggestions and tests)
* Maria José Bellino Machado (author of the Tutorial; very helpful suggestions and many tests, including the organization 
  of human evaluations)

***IMPORTANT NOTICE***
======================

Moses for Mere Mortals (MMM) has been tested with the following 64 bit versions (AMD64) Linux distributions:

Ubuntu 12.04 LTS
Ubuntu 14.04 LTS

Packages used by MMM:
Moses: version 1.0            (https://github.com/moses-smt/mosesdecoder/tree/RELEASE-1.0)
IRSTLM: version 5.70.02       (http://sourceforge.net/projects/irstlm/files/irstlm/irstlm-5.70/)
RandLM: version 0.25          (http://sourceforge.net/projects/randlm/)
Mgiza:                        (downloaded from https://github.com/moses-smt/mgiza on 14/10/2014)
Scripts:                      (http://homepages.inf.ed.ac.uk/jschroe1/how-to/scripts.tgz; this link is now broken)
Mteval:                       (ftp://jaguar.ncsl.nist.gov/mt/resources/mteval-v11b.pl)

***PURPOSES***
==============

1) MOSES INSTALLATION WITH A SINGLE COMMAND
-------------------------------------------
If you aren't used to compiling Linux programs (both Moses and the packages upon which it depends), you'll love this! If you have problems, consult either the Tutorial or the Quick Start Guide (in the docs subdirectory).

2) MOSES VERY SIMPLE DEMO
-------------------------
MMM is meant to quickly allow you to get results with Moses. You can place MMM wherever you prefer on your hard disk 
and then call, with a single command, each of its scripts (their version number is omitted here): 
a) install (in order to download and install the packages needed by Ubuntu to support Moses for Mere Mortals);
a) create (in order to compile Moses and the packages it uses with a single command); 
b) make-test-files (in order to create out of a corpus separate files for training, tuning and testing the training); 
c) train (in order to train the corpus you are intesrested in; a demo corpus is included with this package); 
d) translate (in order to translate documents with the files resulting from the training phase); 
e) score the translation(s) you got; and 
f) transfer trained corpora between users or to other places of your disk. 


MMM uses non-factored training, a type of training that in our experience already produces good results in a significant 
number of language pairs, and mainly with non-morphologically rich languages or with language pairs in which the target 
language is not morphologically rich. A Quick-Start-Guide should help you to quickly get the feel of it and start getting
results. 

It comes with a small demo corpus, too small to do justice to the quality that Moses can achieve, but sufficient for you 
to get a general overview of SMT and an idea of how useful Moses can be to your work, if you are starting to use it. In 
order to use this corpus, please make sure to follow the instructions in the 
Moses-for-Mere-Mortals/docs/Quick-Start-Guide.md.

 
3) PROTOTYPE OF A REAL WORLD TRANSLATION CHAIN
----------------------------------------------
MMM enables you to use very large corpora and is being used for that purpose (translation for real translators) in our 
working environment. It was made having in mind that, in order to get the best results, corpora should be based on 
personal (ou group's) files and that many translators use translation memories. Therefore, we have coupled it with two 
Windows addins that enable you to convert your TMX files into Moses corpora and also allow you to convert the Moses 
translations into TMX files that translators can use with a translation memory tool. 

4) WAY OF STARTING LEARNING MOSES AND MACHINE TRANSLATION
---------------------------------------------------------
MMM also comes with a very detailed Tutorial. It therefore should ease the learning path for true beginners. Most of the
scripts code should be easily understandable even by beginners (if they read the Moses documentation, that is!). What's 
more, it does work!

MMM was designed to be very easy and immediately feasible to use and that's indeed why it was made for mere mortals and 
called as such.

***SOME CHARACTERISTICS***
==========================
 1) Compiles all the packages used by these scripts with a single instruction;
 2) Removes control characters from the input files (these can crash a training);
 3) Extracts from the corpus files 2 test files , 2 train files and 2 tuning files by pseudorandomly selecting 
    non-consecutive segments that are erased from the corpus files;
 4) A new training does not interfere with the files of a previous training;
 5) A new training reuses as much as possible the files created in previous trainings (thus saving time);
 6) Stops with an informative message if any of the phases of training (language model building, recaser training, 
    corpus training, memory-mapping, tuning or training test) doesn't produce the expected results;
 7) Can limit the duration of tuning;
 8) Generates the BLEU and NIST scores of a translation or of a set of translations placed in a single directory;
 9) Allows you to transfer your trainings to someone else's computer or to another Moses installation in the same 
    computer;
10) The mkcls, GIZA and MGIZA parameters can be controlled through parameters of the train script;
11) Selected parameters of the Moses scripts and the Moses decoder can be controlled with the create, train, translate, 
    score and transfer scripts.
