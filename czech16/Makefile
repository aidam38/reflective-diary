TEXS=$(wildcard *.tex)
IMAGES=$(wildcard ../img/*)
PRINTS=$(wildcard ../print/*.tex)
PDFS=$(wildcard *.pdf)

all: diary16.pdf print print_no_duplex clean

%.pdf : %.tex $(TEXS) $(IMAGES)
	latexmk -pdf $<

print:
	pdfbook2 --paper=a5paper --no-crop diary16.pdf

print_no_duplex:
	pdftk A=diary16-book.pdf cat Aeven output diary16-book-even.pdf
	pdftk A=diary16-book.pdf cat Aodd output diary16-book-odd.pdf

clean:
	latexmk -c diary16

remake:
	rm -f $(PDF)
	make all

.PHONY: all print clean remake
