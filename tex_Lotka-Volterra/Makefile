PROJECT=Lotka-Volterra

.PHONY: $(PROJECT).pdf pdf clean distclean synctex

pdf: $(PROJECT).pdf

$(PROJECT).pdf:
	latexmk -pdf \
		-jobname=$(PROJECT) \
		-pdflatex="pdflatex -interactive=nonstopmode" \
		-use-make \
		main.tex

continuous:
	latexmk -f -pdf \
		-pdflatex="pdflatex -interactive=nonstopmode" \
		-use-make \
		-pvc \
		-view=none \
		main.tex

synctex:
	latexmk -f -pdf \
		-pdflatex="pdflatex -interactive=nonstopmode -synctex=1" \
		-use-make \
		main.tex

clean:
	latexmk -c \
		-jobname=$(PROJECT) \
		main.tex
	latexmk -c \
		main.tex
	rm -f $(PROJECT).bbl
	rm -f main.pdf

distclean:
	latexmk -C \
		-jobname=$(PROJECT) \
		main.tex
	latexmk -C \
		main.tex
	rm -f $(PROJECT).bbl
	rm -f main.pdf
