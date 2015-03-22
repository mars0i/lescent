# lescent
Diagrams for lessons on the coalescent<br/>
i.e. programs that may be useful for teaching coalescent concepts.

All new text and software is copyright 2015 by Marshall Abrams. The
software is distributed under the Gnu General Public License version
3.0, available in the file LICENSE.

This project began as modifications of a small program by Mike Bostock:
https://gist.github.com/mbostock/999346 .

### What WrightFisherTree.html does:

Generates a random genealogy, and then allows you to highlight the
ancestors of everyone in the last generation.  The program is a forward
Wright-Fisher simulation, not a coalescent simulation.  However,
comparing the genealogy of the current generation with all lineages
starting from the same population helps one to understand the utility of
coalescent simulations.

Buttons at the bottom allow:

* Generating a new genealogy.
* Highlighting those lineages that still are still present in the
  last generation.  (These are the ones that a coalescent simulation
  could generate.)
* Removing all other lineages.
* Printing the page (without the buttons).

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

### Possible future additions:

* Cause tree to appear to extend sequentially from the top of the window,
rather than seeming to rise up from the bottom as it's done now.

* Allow user to mark individuals and the display their most recent
common ancestor.

* Place mutations on individuals and then track the mutations through
the tree.

* Generate trees using a true coalescent simulation, i.e. a backward
simulation.
