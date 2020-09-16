TEXS=$(wildcard *.tex)
IMAGES=$(wildcard ../img/*)
PRINTS=$(wildcard ../print/*.tex)
PDFS=$(wildcard *.pdf)

all: diary20.pdf print print_no_duplex clean

%.pdf : %.tex $(TEXS) $(IMAGES)
	latexmk -pdf $<

print:
	pdfbook2 --paper=a5paper --no-crop diary20.pdf

print_no_duplex:
	pdftk A=diary20-book.pdf cat Aeven output diary20-book-even.pdf
	pdftk A=diary20-book.pdf cat Aodd output diary20-book-odd.pdf

clean:
	latexmk -c diary20

remake:
	rm -f $(PDF)
	make all

.PHONY: all print clean remake
