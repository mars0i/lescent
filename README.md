Lescent makes diagrams for lessons on the coalescent, i.e. diagrams
that may be useful for teaching coalescent concepts and other related
concepts.

Live demo: <a href="http://members.logical.net/~marshall/lescent">http://members.logical.net/~marshall/lescent</a><br/>
<!-- <a href="http://bl.ocks.org/mars0i/e08f6e578076560bf3bf">http://bl.ocks.org/mars0i/e08f6e578076560bf3bf</a><br/> -->
<!-- Github gist page: <a href="https://gist.github.com/mars0i/e08f6e578076560bf3bf">https://gist.github.com/mars0i/e08f6e578076560bf3bf</a><br/> -->
<!-- Full github repository with latest source code: <a href="https://github.com/mars0i/lescent">https://github.com/mars0i/lescent</a> -->

This project began with modifications of Mike Bostock's <a href="http://bl.ocks.org/mbostock/999346">Random Tree</a>.
All new text and software is copyright 2015 by Marshall Abrams (<a
href="http://members.logical.net/~marshall">http://members.logical.net/~marshall</a>,
m a b r a m s &nbsp;&nbsp;at&nbsp;&nbsp; u a b
&nbsp;&nbsp;dot&nbsp;&nbsp; e d u), and is distributed
under the Gnu General Public License version 3.0, available in the
file LICENSE at  <a
href="https://github.com/mars0i/lescent/blob/master/LICENSE">https://github.com/mars0i/lescent/blob/master/LICENSE</a>.

If you find lescent useful, feel free to let me know.&nbsp; -Marshall

### What it does:

Lescent generates a schematic diagram of a random genealogy, with fixed
population size and discrete generations.  There are options to
highlight or show only those lineages that still have members in the
latest generation, and to show how mutations propagate.  For an informal
introduction to the concepts that lescent illustrates, see "Things to
notice" below.

Specifically, lescent is a forward Wright-Fisher simulation with fixed
population size, asexual reproduction, and no natural selection. 
(Lescent's name reflects its pedagogical purpose, not its
functioning.  It's not a coalescent simulation.)  Mutations in lescent
are best thought of as following an infinite alleles model.  Each new
color represents a new mutation, which replaces the old one. 
(However, lescent uses a fixed number of colors, so the same color may
be reused for different mutations when there are many mutations.)

### How to use it:

Experiment with the buttons.  Try clicking "New genealogy" first.  You
may need to click on "Open in new window" first.

Lescent includes the following controls (first choose "Open in a new window"
if necessary):

* **pop size**, **generations**: Set the population size and number of generations for a new genealogy.
* **new genealogy**: Generate a new genealogy.
* **new mutations**: Remove all mutations and generate new mutations.
* **hide/show extinct**: Show only lineages still present in the last generation.
* **de/emphasize non-extinct**: Emphasize lineages present in the last generation, de-emphasizing others.
* **print**: Print the page without buttons and other controls.

The print button is useful for generating PDF diagrams, if your printing
software can generate PDFs.

In the full git repository, there are two versions of lescent:
lescent.html, and lescentGrayScale.html.  The latter generates figures
using shades of gray rather than colors, and it has different size
settings.

### Things to notice:

Generations are represented by circles that are all at the same
level.  The earliest generation is at the top; the most recent one is
at the bottom.  Each generation has the same number of organisms
(specified by the "pop size" dropdown). 
Mutations are represented by colors.  In the version of the diagram
that's displayed first, thicker lines represent those lineages that
last until the most recent generation.  (However, when you choose "new
genealogy", you'll see a simpler diagram, which you can then modify
using the other buttons.)

Usually, not all members of a population succeed in producing
offspring who make it to adulthood.  This is likely to happen purely
by chance, even without any influence of natural selection.  (This
kind of random pruning is unlikely only when a population is growing
*very* rapidly.)  As a result of this process, in each generation,
some lineages are lost.  This happens over and over again, with the
consequence that very few members of the initial population have
descendants many generations later.  Many genetic variants are lost in
this way, even after they spread.

When scientists do computer simulations of evolutionary processes--for
example to generate simulated genetic data for comparison with real
genetic data--it's inefficient to generate lots of genetic data that is
just thrown away: Lineages that don't last into the present can't
generate present-day data.  That's part of what lescent illustrates:
With a "forward" simulation that runs from the past to the present, a
lot of data is generated for no good reason.  To see this, try using the
"Hide/show extinct" and "de/emphasize non-extinct" buttons.  (Lescent
runs quickly, but that's because it simulates very few organisms in very
few generations, with "genes" that consist of a few numbers.)

Thus, scientists studying evolutionary processes often use "coalescent"
simulations, which generate lineages by starting from the present,
then moving backward in time.  (In this way, lineages that won't reach
the present are never generated at all.)  Although lescent is not a
coalescent simulation, the kind of pattern that coalescent simulations
generate can be illustrated by using the button that hides the extinct
lineages.

Once a  tree of lineages has been generated in a coalescent
simulation, patterns representing genetic data can be added to the
lineages.  This can be illustrated using the "new mutations" button
after hiding extinct lineages. 

### More info about the coalescent:

The following article is a good introduction to concepts underlying
the coalescent process and coalescent simulations for people who
already know something about evolutionary biology:

"Genealogical trees, coalescent theory and the analysis of genetic polymorphisms"<br/>
Rosenberg, Noah A. and Nordborg, Magnus<br/>
*Nature Reviews Genetics*, May 2002, v. 3 no. 5, pp. 380-390.<br/>

For an in-depth treatment see the following books:<br/>

*Gene Genealogies, Variation and Evolution: A Primer in Coalescent Theory*<br/>
by Jotun Hein, Mikkel Schierup, and Carsten Wiuf<br/>
Oxford University Press, 2005.

*Coalescent Theory: An Introduction*<br/>
by John Wakeley<br/>
Roberts and Company, 2009.

### Some related graphical tools on the web:

* From <a href="http://bedford.io/projects">Trevor Bedford</a>:
ancestry, coaltrace, divergence, haplotypes, stem, and nextflu. 

* From the authors of the book *Gene Genealogies*, listed above:
The Wright-Fisher animator and Hudson animator at <a
href="www.coalescent.dk">www.coalescent.dk</a>.

### Miscellaneous:

* Lescent is written using <a href="http://d3js.org">d3.js</a>, a
Javascript library by Mike Bostock.  There are a number of good books
and web resources on d3.js.

* "Wright-Fisher model" in this context doesn't imply that there are
multiple alleles that are tracked; all that's required for generating a
genealogical tree using a Wright-Fisher model is that reproductive
success be random (with replacement) in discrete generations with fixed
population size.

* Internally, an individual in lescent stores all mutations that
occurred  its ancestors. In that sense, lescent is more like an
infinite sites model than an infinite alleles model.  However, at
present, only the most recent mutation affects color, which is why I
described it above in terms of the infinite alleles model.
