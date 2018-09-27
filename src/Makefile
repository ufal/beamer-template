SHELL=bash
NAME=demo
LATEX=xelatex

all: $(NAME).pdf sty

$(NAME).pdf: $(NAME).tex references.bib ufalslides.sty
	latexmk -pdflatex="$(LATEX) %O %S" -pdf -dvi- -ps- -halt-on-error $(NAME)
	cp demo.pdf ..

watch:
	latexmk -pdflatex="$(LATEX) %O %S" -pdf -dvi- -ps- -interaction=nonstopmode -synctex=1 -pvc $(NAME)

view:
	xdg-open $(NAME).pdf

clean:
	rm $(NAME).{aux,bbl,log,out,pdf,toc}

sty:
	perl latexpand ufalslides.sty > ../ufalslides.sty
