#export TEXINPUTS=../tex//:

all: manuscript.pdf

# LaTeX must be run multiple times to get references right
manuscript.pdf: manuscript.tex $(wildcard *.tex) refs.bib 
	pdflatex $<
	bibtex manuscript
	pdflatex $<
	pdflatex $<

clean:
	rm -f *.log *.dvi *.aux *.toc *.lof *.lot *.out *.bbl *.blg *.xmpi
	rm -f acs-manuscript.bib
	rm -f manuscript.pdf
