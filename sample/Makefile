all:slide.pdf

clean:
	latexmk -c -xelatex
	rm *.bbl *.nav *.snm

slide.pdf:slide.tex img/
	latexmk -xelatex slide.tex

.PHONY:pvc
pvc:slide.tex img/
	latexmk -xelatex -pvc slide.tex
