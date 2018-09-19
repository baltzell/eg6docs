STUB  = icradcor
INPUTFILES = $(wildcard ./inputs/*.tex ./pics/*)
TEXFILE  = $(STUB).tex
PDFFILE  = $(STUB).pdf
BIBFILE  = $(STUB).bib
BIBNOTE  = $(STUB)Notes.bib

LATEX    = latex
BIBTEX   = bibtex
PDFLATEX = pdflatex
DVIPS    = dvips
ACROREAD = acroread
PSTOPDF  = ps2pdf
MP       = mpost


all: $(PDFFILE)

$(PDFFILE): $(TEXFILE) $(STUB).bib $(INPUTFILES)
	@echo launching pdflatex 1st time
	$(PDFLATEX) $(TEXFILE)
	@echo launching bibtex 1st time
	$(BIBTEX) $(STUB)
	@echo launching bibtex 2nd time
	$(BIBTEX) $(STUB)
	@echo launching bibtex 3rd time
	$(BIBTEX) $(STUB)
	@echo launching pdflatex 2nd time
	$(PDFLATEX) $(TEXFILE)
	@echo launching pdflatex 3rd time
	$(PDFLATEX) $(TEXFILE)

clean: 
	rm -f *.bbl *.spl *.aux *.log *.blg *.dvi *.toc *.lot *.lof *.out $(PDFFILE) $(BIBNOTE)
