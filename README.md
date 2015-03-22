# lescent
Diagrams for lessons on the coalescent<br/>
i.e. programs that may be useful for teaching coalescent concepts.

All new text and software is copyright 2015 by Marshall Abrams. The
software is distributed under the Gnu General Public License version
3.0, available in the file LICENSE.

This project began as modifications of a small program by Mike Bostock:
https://gist.github.com/mbostock/999346 .

### What it does:

Generates a random genealogy, and then allows you to highlight the
ancestors of everyone in the last generation.  The program is a forward
Wright-Fisher simulation, not a coalescent simulation.  However,
comparing the genealogy of the current generation with all lineages
starting from the same population helps one to understand the utility of
coalescent simulations.

Controls at the bottom allow:

* Generating a new genealogy.
* Highlighting those lineages that still are still present in the
  last generation.  (These are the ones that a coalescent simulation
  could generate.)
* Removing all other lineages.
* Setting population size and number of generations.
* Printing the page (without the buttons).

Tip: In OS X, Safari is a good option for generating a PDF via the
print dialog, because it doesn't add a header and footer giving
information about the filename, etc.

Note that "Wright-Fisher model" in this context doesn't imply that
there are multiple alleles that are tracked; all that's required for
generating a genealogical tree using a Wright-Fisher model is that
reproductive success be random (with replacement) in discrete
generations with fixed population size.

One good introduction to concepts underlying the coalescent process and
coalescent simulations is:

  "Genealogical trees, coalescent theory and the analysis of genetic polymorphisms"<br/>
  Rosenberg, Noah A. and Nordborg, Magnus<br/>
  *Nature Reviews Genetics*, May 2002, v. 3 no. 5, pp. 380-390.<br/>

### Possible future changes/additions:

* Add random mutations.

* Allow user to mark individuals in last generation and the display
their most recent common ancestor.

* Allow reformatting the non-extinct trees using the d3 tree layout when
  the extinct branches are hidden.

* Cause tree to appear to extend sequentially from the top of the window,
rather just appearing at once.

* Fix small bug that causes top of trees to be in middle of page when
  number of generations is small.  (This is due to the fact that there's
  actually a hidden one-individual "generation" that's needed by d3's
  tree layout function.  To fix it I can special-case the y-coordinates
  of the first proper generation.)

* Possibly rearrange main tree generation code so that it's not adjusting the
  layout repeatedly as the data is being generated.

* Generate trees using a true coalescent simulation, i.e. a backward
simulation.
