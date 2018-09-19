BIBFILE  = tpcalign
INPUTFILES = $(wildcard ./inputs/*.tex)
TEXFILE  = $(BIBFILE).tex
PDFFILE  = $(BIBFILE).pdf

LATEX    = latex
BIBTEX   = bibtex
PDFLATEX = pdflatex
DVIPS    = dvips
ACROREAD = acroread
PSTOPDF  = ps2pdf
MP       = mpost

all: $(PDFFILE)

$(PDFFILE): $(TEXFILE) $(BIBFILE).bib $(INPUTFILES)
	@echo launching pdflatex 1st time
	$(PDFLATEX) $(TEXFILE)
	@echo launching bibtex 1st time
	$(BIBTEX) $(BIBFILE)
	@echo launching bibtex 2nd time
	$(BIBTEX) $(BIBFILE)
	@echo launching bibtex 3rd time
	$(BIBTEX) $(BIBFILE)
	@echo launching pdflatex 2nd time
	$(PDFLATEX) $(TEXFILE)
	@echo launching pdflatex 3rd time
	$(PDFLATEX) $(TEXFILE)

clean: 
	rm -f *.bbl *.spl *.aux *.log *.blg *.dvi *.toc *.lot *.lof *.out $(PDFFILE)
