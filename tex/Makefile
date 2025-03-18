MASTER  = 14_time_distribution_sliced

handout: clean
	@tail -n +4 $(MASTER).tex > temp.tex
	@echo '\documentclass[handout]{beamer}' | cat - temp.tex > ${MASTER}_handout.tex
	@pdflatex -shell-escape ${MASTER}_handout.tex
	@bibtex ${MASTER}_handout
	@pdflatex -shell-escape ${MASTER}_handout.tex
	@pdflatex -shell-escape ${MASTER}_handout.tex
	@rm -f temp.tex ${MASTER}_handout.tex

lecture: clean
	@tail -n +4 $(MASTER).tex > temp.tex
	@echo '\documentclass[aspectratio=169]{beamer}' | cat - temp.tex > ${MASTER}_lecture.tex
	@pdflatex -shell-escape ${MASTER}_lecture.tex
	@bibtex ${MASTER}_lecture
	@pdflatex -shell-escape ${MASTER}_lecture.tex
	@pdflatex -shell-escape ${MASTER}_lecture.tex
	@rm -f temp.tex ${MASTER}_lecture.tex

clean:
	@rm -rf *run.xml *-blx.bib *.aux *.bbl *.blg *.brf *.log *.lof *.lot *.lol *.out *.tcp *.toc *.tps *.bak *.backup *.pdfsync *.synctex.gz *.nav *.snm *.vrb *.*~
	@for i in run.xml -blx.bib aux bbl blg brf log lof lot lol out tcp toc tps bak backup pdfsync synctex.gz nav snm vrb; do find . -name *.$$i -exec rm -f {} + ; done
	@find . -name *.*~ -exec rm -f {} +

cleanall: clean
	@rm *.pdf

fulda: lecture handout