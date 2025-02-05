# Description
Forked version for development, cleaning, & documentation

bp-utils are command-line utilities that are wrappers of popular BioPerl classes (`Bio::SeqIO`, `Bio::Seq`, `Bio::AlignIO`, `Bio::SimpleAlign`, etc). The motivation is to relieve BioPerl users from writing full-blown scripts for routine manipulations of sequences, alignments, trees, and others. For common operations of sequences and alignments, bp-utils make it easy to create workflows with a single BASH script containing a combination of bp-utils calls (and no Perl or BioPerl coding is necessary).

Internally, bp-utils follow a "Wrap, don't Write" design principle. That is, we have full faith in the robustness of the BioPerl development framework. As such, bp-utils methods should ALL be wrappers to BioPerl methdos so that exceptions can be handled properly by BioPerl. 

In reality, though, some methods are new and unique to bp-utils. In the future, all non-wrapper methods in bp-utils should ideally be re-factored into BioPerl class methods. This way, the bp-utils layer could be as thin as possibe and new methods could be added with minimal coding.

# Dependencies
* Perl 5.10.0 or higher
* BioPerl 1.6.924 or higher

You can check your version of perl using

```
perl -v
```

and your version of BioPerl using

```
perl -MBio::Root::Version -Mversion -e 'print version->parse($Bio::Root::Version::VERSION)->normal,"\n"'
```

in a terminal.

# Install & Test (assuming a UNIX/Linux-like environment)
* Go to repository: https://github.com/bioperl/bp-utils
* Download current release: https://github.com/bioperl/bp-utils/releases/download/v1.0/bp-utils-release-v1.0.tar.gz
* Unzip and untar
  
        tar -zxf bp-utils-current-release.tar.gz

* Add "bp-utils" directory to your `$PATH`:
  
        # Add this line to your .profile (or equivalent) to make it permanent
        export PATH=$PATH:/path/to/bputils

* Run test scripts: `./Test-bioseq` and `./Test-bioaln`

# Get Help
* Run `perldoc`: e.g., `perldoc bioseq`; `perldoc bioaln`
* Run with `--help` or `--man`: e.g., `bioseq --help`; `bioaln --help`
* A help file with use cases is maintained at: http://diverge.hunter.cuny.edu/labwiki/Bioutils

# Developers, Contact, Citation
* Yozen Hernandez
* Pedro Pagan
* Girish Ramrattan
* Weigang Qiu, City University of New York, Hunter College (Correspondence: weigang@genectr.hunter.cuny.edu)
* If you find the tools useful, please cite: Hernandez Y., P. Pagan,  G. Ramrattan, & W.-G. Qiu. (2015). Bp-utils (Release 1.0): BioPerl-based command-line utilities for manipulating sequences, alignments, and phylogenetic trees. URL: https://github.com/bioperl/bp-utils. 

# Checklist for adding a method (for developers):
* We encourage BioPerl developers to add command-line interface to their BioPerl methods by using bp-utils.
* To do so, please contact Weigang Qiu, City University of New York, Hunter College  (weigang@genectr.hunter.cuny.edu)
* For each new mehtod, first pick a long option (--option) and (optionally) a one-letter short (-x) option
* Add one line to the POD Synopsis
* Add to the POD Usage. Note that POD usages are ordered by short names alphabatically
* Add a subroutine to the script itself. Note that subroutines are ordered according to POD usage (alphatically by short names)
* Add a test command to the testing file (add a test file if necessary)

# Release Notes
* Release 1.0. (Feb 10, 2015): Contains two utilities with tests: bioseq & bioaln. To be released: biopop & biotree

# To Do List
* bioaln: --gapstates implemented, but needs to add to POD & test
* biotree: deroot a tree
* biotree: --multi2bi; need to add to POD & test
* biotree: --bi2multi
* biotree: --cleanbr remove branch length; need to add to POD & test
* biotree: --cleanboot remove boot/node labels; need to add to POD & test
* biotree: --remove an OTU
* bioaln: -- add --informative
* biopop: bipart added; needs to add POD & test
* biotree: bipart (sister_pairs) added; needs to add POD & test
* biotree: swap-otus added; needs to add POD & test



