# makefile: Rnw -> tex -> pdf
# v 3.0
# .Rnw extension is automatically added
file_name = pr201_final
file_name2 = pr201_final_answers
file_name3 = pr201_final_bank


all: $(file_name).pdf # $(file_name2).pdf $(file_name3).pdf

$(file_name).pdf: $(file_name).tex probs_test_bank.tex
	# protection against biber error
	# http://tex.stackexchange.com/questions/140814/
	rm -rf `biber --cache`

	# create pdf
	# will automatically run pdflatex/biber if necessary
	latexmk -xelatex -pdf $(file_name).tex

	# clean auxillary files
	latexmk -c $(file_name).tex

# $(file_name).tex : $(file_name).Rnw
# 	Rscript -e "library(knitr); knit('$(file_name).Rnw')"

clean:
	rm $(file_name).pdf
	# rm $(file_name).tex
