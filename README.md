## The Magnetic Fusion Energy Formulary

The Magnetic Fusion Energy Formulary (the "Formulary" hereafter) is a
reference book containing much of the critical mathematics and physics
required for students and researchers in the field of magnetic fusion
energy. It compiles over 500 equations drawn from the leading
scientific literature into a comprehensive and convenient book. Each
equation includes a citation that provides the original source and
page number to provide further reading, and all equations are
comprehensively indexed for easy on-the-fly access.

The formulary consists of three sections. Chapters 1-2 cover the
mathematics, fundamental units, and physical constants relevent to
magnetic fusion. Chapters 3-9 covers the basic physics of
thermonuclear fusion plasmas, beginning with electrodynamics as a
foundation and developing single particle physics, plasma parameters,
plasma models, plasma transport, plasma waves, and nuclear
physics. Finally, Chapters 10-13 covers the physics of toroidally
confined core and edge plasmas, as well as the fundamentals of
magnetic fusion energy in deuterium-tritium tokamaks. Chapter 13
contains a large table of parameters for major tokamaks of the world.


### Contributing and Licensing

We have decided to release the Formulary source code on GitHub as a
sort of experiment, where we will attempt to maintain an open-source
reference book for the plasma physics and magnetic fusion community
*to which you can contribute your expertise*. If you feel that
essential, standard, and widely-used fusion science is missing from
the Formulary, please make us aware, or better yet, write a few
snippets (or a whole section!) of LaTeX code with your additions,
providing the most respected reference(s) and page number(s) for the
new information. Your name will be added to the front section of
contributors. If this model proves successful, we may even remove
ourselves as the authors and transition to a *community authored and
maintained work*. Let us know if you're interested in pursuing this
path with us.

We encourage any interested user to fork (on GitHub) or clone the
repository, make corrections to existing content and add important
content that you feel is missing, and then submit a pull request so
that we can incorporate your work into the Formulary. (Of course,
contributions are always welcome by email.) As such, the LaTeX source
code and build system that comprises the Formulary has been released
as open source software under the GNU General Public License (GPL
v3.0). In addition to contributing to the Formulary, we encourage you
to download, redistribute, modify, and use the source code in any way
you might find useful in your own projects under the terms outlined in
the licenses above.


### Build instructions  

On Linux, clone into the repository and then use the provided
GNU Makefile to build PDF and Postscript:

```bash
  # Clone the MFE Formulary from GitHub:
  git clone https://github.com/MFEFormulary/MFEFormulary.git  

  # Move to the LaTeX source code directory:
  cd MFEFormulary/latex
  
  # To build a publication-ready PDF and PS:
  make  

  # To install the PDF and PS in the top-level directory
  make install

  # To cleanup all build files:  
  make clean  
```

### Dependencies

1. LaTeX - The MFE Formulary is built with the LaTeX typesetting
system. Unix/Linux users usually use
[TexLive](http://www.tug.org/texlive/), which is available from the
standard package managers (YUM on Fedora/Redhat-based distributions,
apt-get on Debian-based distributions). Windows users will usually use
[MiKTeX](http://www.miktex.org).  The following LaTex packages,
which can be obtained at [CTAN](http://www.ctan.org)) if not included
by default on your system, are required:  

  - amsbsy, amsmath, amssymb, caption, enumerate, fix-cm, float, graphicx, graphics, hyperref  
    longtable, makeidx, multicol, multirow, natbib, rotating, tocloft, tools, xcolor  

  
2. GNU make - The MFE Formulary build system is controlled using [GNU
make](http://www.gnu.org/software/make/). The makefile provides
automatic compilation of the final PostScript and PDF from the raw
LaTeX source in a user-friendly way.


### Directory structure

The Formulary directory structure and build system are pretty
straightforward and easy to understand:  

  - **archive/**     : Previous versions of the Formulary in PDF format  

  - **ipython/**     : IPython notebooks for useful computation and figure generation  

  - **latex/**       : LaTeX code for the Formulary. Contains all \*.tex files and GNU makefile  
    -- **figures/**  : EPS format figures contained in the Formulary  
    -- **build/**    : location of transient LaTeX build files  

  - **CHANGELOG.md** : List of major content updates and fixes for each Formulary release

  - **LICENSE.md**   : GNU GPL v3.0 covers the Formulary source code

  - **README.md**    : You're currently reading it

