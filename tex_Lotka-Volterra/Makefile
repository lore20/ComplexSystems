PROJECT=Lotka-Volterra

.PHONY: $(PROJECT).pdf pdf clean distclean

pdf: $(PROJECT).pdf

$(PROJECT).pdf:
	latexmk	-pdf \
		-jobname=$(PROJECT) \
		-pdflatex="pdflatex -interactive=nonstopmode" \
		-use-make \
		main.tex

continuous:
	latexmk -pdf \
		-jobname=$(PROJECT) \
		-pdflatex="pdflatex -interactive=nonstopmode" \
		-use-make \
		-pvc \
		-view=none \
		main.tex

clean:
	latexmk -c \
		-jobname=$(PROJECT) \
		main.tex
	rm -f $(PROJECT).bbl

distclean:
	latexmk -C \
		-jobname=$(PROJECT) \
		main.tex
	rm -f $(PROJECT).bbl
