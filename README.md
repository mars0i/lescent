Lescent makes diagrams for lessons on the coalescent, i.e. diagrams
that may be useful for teaching coalescent concepts and other related
concepts.

Live demo: <a href="http://bl.ocks.org/mars0i/e08f6e578076560bf3bf">http://bl.ocks.org/mars0i/e08f6e578076560bf3bf</a><br/>
Github gist page: <a href="https://gist.github.com/mars0i/e08f6e578076560bf3bf">https://gist.github.com/mars0i/e08f6e578076560bf3bf</a><br/>
Full github repository with latest source code: <a href="https://github.com/mars0i/lescent">https://github.com/mars0i/lescent</a>

This project began with modifications of Mike Bostock's Random Tree:
<a href="http://bl.ocks.org/mbostock/999346">http://bl.ocks.org/mbostock/999346</a>.
All new text and software is copyright 2015 by Marshall Abrams. The
software is distributed under the Gnu General Public License version
3.0, available in the file LICENSE at 
<a href="https://github.com/mars0i/lescent/blob/master/LICENSE">https://github.com/mars0i/lescent/blob/master/LICENSE</a>.

Author:
Marshall Abrams 
<a href="http://members.logical.net/~marshall">http://members.logical.net/~marshall</a>
(m a b r a m s &nbsp;&nbsp;at&nbsp;&nbsp; u a b &nbsp;&nbsp;dot&nbsp;&nbsp; e d u) <br/>
If you find lescent useful, feel free to let me know.

### What it does:

Generates a schematic diagram of a random genealogy with fixed
population size and discrete genreations.  There are options to
highlight or show only those lineages that still have members in the
latest generation, and to show how mutations propagate.  Lescent is a
forward Wright-Fisher simulation with asexual reproduction and no
natural selection.

Controls (choose "Open in a new window") allow:

* Setting population size and number of generations for a new genealogy.
* Generating a new genealogy.
* Generating mutations.
* Showing only lineages still present in the last generation.
* Hiding all other lineages.
* Emphasizing lineages present in the last generation, and de-emphasizing others.
* Printing the page (without the buttons).

### Things to try:

Click on the "Open in a new window" link, and experiment with the
buttons at the bottom.

(The print button is useful for generating PDF diagrams if your
software allows you to generate PDFs using your printing system.)

### Things to notice:

Usually, not all members of a population succed in producing offspring who
make it to adulthood.  This is likely to happen purely by chance, even without any
influence of natural selection.  (It's unlikely only when a population is growing *very*
rapidly.)  So in each generation, some lineages are lost.  As a result, very few members
of the population have descendants after many generations.  Many genetic variants are
lost in this way, even after they spread.

When scientists do computer simulations of evolutionary processes--for
example to generate simulated genetic data for comparison with real
genetic data--it's inefficient to generate lots of genetic data that is
just thrown away because it represents lineages that don't last into the
present.  That's what this program illustrates: With a "forward"
simulation that runs from the past to the present, a lot of data is
generated for no good reason.  To see this, try using the "Hide/show
exitinct" and "de/emphasize non-exinct" buttons.  (While the lescent
program runs quickly, that's because it simulates very few organisms in
very few generations, and their "genes" consist of a few numbers.)

As a result, scientists often use "coalescent" simulations, which
generate lineages beginning from the present and moving backward in
time.  Lineages that don't reach the present are never generated.
(Although lescent is not a coalescent simulation, the kind of pattern
that coalescent simulations generate can be illustrated with it by
using the button that hides the exinct lineages.)  Then, once a tree
of lineages has been generated, patterns representing genetic data can
be added to the lineages.  This can be illustrated using lescent with
the "new mutations" button.

### More info about the coalescent:

This is a good introduction to concepts underlying the coalescent process and
coalescent simulations:

  "Genealogical trees, coalescent theory and the analysis of genetic polymorphisms"<br/>
  Rosenberg, Noah A. and Nordborg, Magnus<br/>
  *Nature Reviews Genetics*, May 2002, v. 3 no. 5, pp. 380-390.<br/>

For an in-depth treatment see:<br/>

*Gene Genealogies, Variation and Evolution: A Primer in Coalescent Theory*<br/>
by Jotun Hein, Mikkel Schierup, and Carsten Wiuf<br/>
Oxford University Press, 2005.

*Coalescent Theory: An Introduction*<br/>
by John Wakely<br/>
Roberts and Company, 2009.

### Some related graphical tools on the web that may be of interest:

From <a href="http://bedford.io/projects">Trevor Bedford</a>:
ancestry, coaltrace, divergence, haplotypes, stem, and nextflu. 

From the authors of the book *Gene Genealogies*, listed above:
The Wright-Fisher animator and Hudson animator at <a
href="www.coalescent.dk">www.coalescent.dk</a>, 

### Note:

"Wright-Fisher model" in this context doesn't imply that there are
multiple alleles that are tracked; all that's required for generating a
genealogical tree using a Wright-Fisher model is that reproductive
success be random (with replacement) in discrete generations with fixed
population size.
