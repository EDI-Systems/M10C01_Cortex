NAME=v2pc
PAPER=$(NAME).tex

default: quick clean

quick:
	-pdflatex \\nonstopmode\\input $(PAPER)

all: biblink setupsty thorough cleansty

thorough:
	pdflatex \\nonstopmode\\input $(PAPER)
	bibtex $(NAME)
	pdflatex \\nonstopmode\\input $(PAPER)
	pdflatex \\nonstopmode\\input $(PAPER)

prepress: all
	gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -dEmbedAllFonts=true -sOutputFile=final.pdf -f $(NAME).pdf

final: prepress

cleansty:
	rm -f *.sty *.bst *.cls

biblink:
	rm -f $(NAME).bib
	ln -s ../bibliography/biblio.bib $(NAME).bib

clean: cleansty
	rm -f *.aux *.bbl *log *.blg *.pdf *.toc $(NAME).out

distclean: clean
	rm -f *.aux *.bbl *log *.blg $(NAME).out *.pdf



