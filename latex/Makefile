########################################################################
#
# name: Makefile
# date: 11 Jan 14
# auth: Zach Hartig
#
# desc: GNUmakefile to control building of the MFE Formulary from the
#       .tex LaTeXsource files. Make will build a Postcript (.ps) and
#       a PODF (.pdf) of the Formulary in the top-level directory. The
#       LaTeX source files are contained within the latex/ directory;
#       all the transient LaTeX build files are contained in the
#       build/ directory.
#
# 2run : To build the Postscript and PDF type : make
#        To clean up the build type           : make clean
#
########################################################################

PDFTARGET = MFEFormulary.pdf
PSTARGET = MFEFormulary.ps

FORMULARY = MFEFormulary.tex
IDX = MFEFormulary.idx
REF = MFEFormulary.bib

TEXFILES = $(wildcard *.tex)
FIGFILES = $(wildcard figures/*.eps)

BUILDDIR = build
DVI = $(BUILDDIR)/MFEFormulary.dvi

all: $(PDFTARGET)

$(PDFTARGET): $(PSTARGET)
	ps2pdf $(PSTARGET)

$(PSTARGET): $(DVI)
	dvips -o $(PSTARGET) $(DVI)

$(DVI): $(TEXFILES) $(FIGFILES)
	latex --output-directory=$(BUILDDIR) $(FORMULARY)
	cp $(REF) $(BUILDDIR)
	cd $(BUILDDIR); bibtex MFEFormulary
	latex --output-directory=$(BUILDDIR) $(FORMULARY)
	makeindex $(BUILDDIR)/MFEFormulary.idx
	latex --output-directory=$(BUILDDIR) $(FORMULARY)
	latex --output-directory=$(BUILDDIR) $(FORMULARY)

.PHONY: install clean
install:
	@cp $(PDFTARGET) $(PSTARGET) ../
	$(info Copying MFEFormary.pdf and MFEFormulary.ps to top-level directory)

clean:
	@rm $(BUILDDIR)/* $(PDFTARGET) $(PSTARGET) -f 2> /dev/null
	$(info All unnecessary makefile dependencies have been removed!)
