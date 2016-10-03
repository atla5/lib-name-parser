# lib-name-parser

### Description ###

#### short ####
Parse a list of names from raw text into a dictiory of unique authors. [for use with LIS authority control]

#### long ####
The lib-name-parser was originally intended for use with the
  [dublin-core-text-parser](https://github.com/atla5/dublin-core-text-parser/). It will be used to process 
  a list of unformatted strings containing names (e.g. "Dr. Douglas Raymond Murrow III") and create 
  a uniquely identified and combined object used for matching. 
  
This will (hopefully) enable the linking of similar names across multiple occurances ("Douglas Murrow", "Douglas Ray Murrow"
  "Doug R. Murrow"), and perspectively allow for the detection of typos or misspellings ("Daug R. Marrow"). With some extra
  work, it could also automate the creation of authority records between issues and within collections.
  
_The program follows the lineage from Josh Fraser's original implementation of the 
  [php-name-parser](https://github.com/joshfraser/PHP-Name-Parser), and from Garve Hays's java port, 
  [NameParser](https://github.com/gkhays/NameParser). Its naming scheme is meant to reflect this geneology._
  
### Purpose ###

#### short ####
Automate the complex, time-consuming, and often mind-numbing process of manual authority control in an extensible, 
  manageable way.

#### long ####
Going through any periodical or other succession of similarly sourced items and logging metadata about its 
  contributors, you often find small inconsistencies with how the names are displayed.
  
Whether this comes in the form of typos/OCR errors (Doug Murrow <=> Dog Murrow), progressive revelation 
  (Doug Murrow => Douglas Murrow => Douglas R. Murrow), or title acquisition (Douglas R. Murrow => 
  Dr. Douglas R. Murrow, PhD), these minor changes over time can complicate searching and collocation
  in catalogs, databases, etc. 
  
This software is intended for use as an external library (software sense) to other applications, assisting 
  them with combining these disparate references to the same author/individual by combining them under a 
  single universal ID, object, and/or authority record (maybe doing this, we'll see) in a way that can 
  remain controlled/monitored or fully automated. 
  
I intend to ensure that the program itself remains agnostic as to the balance between _standardization_ 
  (fixing things to make them match up) and _provenance_ (retaining how they originally appeared), by
  providing the means to run it at varying levels of automation and with certain features turned off.
  Knowing, of course, that this will be an open source project and more advanced edits can be made 
  by the user according to need.
  
### Background ###
Name parsing is a very common operation in software development. I wanted to find (or create) a standard algorithm for 
  doing this with LIS software, but found that [@joshfraser](https://github.com/joshfraser) had already created one 
  in PHP and JavaScript (links below).
  
Looking into these derivatives, I first forked [@gkhays](https://github.com/gkhays) 'NameParser', but found that this would 
  be a much heftier implementation given the time/occurrences component and that it might be wise to create my own from 
  scratch instead of pull requesting a gigantic alteration. 
  
This software, as mentioned, follows this authorial lineage from Josh to Garve to myself. The application of this 
  algorithm to library authority control is, to my knowledge, a novel and meaningful contribution. 

### External Links ###

#### names (general) ####
* 2010 article by [Patrick McKenzie](https://github.com/patio11) of [Kalzumeus Software](https://www.kalzumeus.com/)
  on '[Faleshoods Programmers Believe About Names](https://www.kalzumeus.com/2010/06/17/falsehoods-programmers-believe-about-names/)'.
* academic [paper](https://arxiv.org/pdf/1308.0749.pdf) entitled "Accuracy of simple, initials-based methods for 
  author name disambiguation" by Stasa Milojevic.
* ...

#### software/algorithm ####
* [Josh Fraser](https://github.com/joshfraser)'s original 2009 article 
  '[splitting names](http://www.onlineaspect.com/2009/08/17/splitting-names/)' describing algorithm
* associated [php](https://github.com/joshfraser/PHP-Name-Parser) and
  [js](https://github.com/joshfraser/JavaScript-Name-Parser) github repositories. 
* port by [Garve Hays](https://github.com/gkhays) in [java](https://github.com/gkhays/NameParser) that was very helpful 


#### authority control (LIS) ####
* short introductory [write-up](https://library.fiu.edu/about-us/cataloging/authority-control) by 
  the library at Florida International University (FIU)
* wikipedia entry on [authority control](https://en.wikipedia.org/wiki/Authority_control)
  with a section specifically about 
  [authority records](https://en.wikipedia.org/wiki/Authority_control#Authority_records_and_files)
* long but approachable 2007 article on '[the purpose of authority control](https://bibwild.wordpress.com/2007/08/08/the-purpose-of-authority-control/)'
* In-depth [presentation](http://researcharchive.calacademy.org/research/informatics/taf/proceedings/Calhoun.html) 
  by Karen Calhoun from the Taxonomic Authority File (TAF) Workshop 

_note: I did come up with a very similar algorithm and parsing scheme independent of these sources, 
  but given the clarity of their documentation and the prior existence of their implementations and
  their usefulness to me, it would be dishonest to claim full credit for it_
