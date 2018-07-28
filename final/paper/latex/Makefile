# for latex circular reference problem, you need to remove all the old
# aux files, then do one latex run, one bibtex run, then 2 more latex run
# https://tex.stackexchange.com/questions/63852/question-mark-or-bold-citation-key-instead-of-citation-number

all: file open
file:
	rm -rf *.aux *.bbl *.blg *.dvi *.fdb_latexmk *.fls *.out
	pdflatex finalpaper.tex
	bibtex finalpaper
	pdflatex -synctex=1 -interaction=nonstopmode finalpaper.tex
	pdflatex -synctex=1 -interaction=nonstopmode finalpaper.tex

open:
	open finalpaper.pdf > /dev/null
