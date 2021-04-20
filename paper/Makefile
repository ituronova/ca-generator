# the name of the output
# CO=working
CO=final
#CO=main-sigplanconf

# names of files other than sources the change of which should recompile the
# source
#CHANGED_FILES_OTHER =literature.bib
CHANGED_FILES_OTHER+=$(wildcard figures/*.tikz) $(wildcard figures/*.tex) $(wildcard *.tex) $(wildcard *.bib)

EXTERNAL_FIGS=$(wildcard TikzPictures/*.md5) $(wildcard TikzPictures/*.pdf) $(wildcard TikzPictures/*.log) $(wildcard TikzPictures/*.dpth) $(wildcard TikzPictures/*.synctex.gz)

# List of TeX files
TEX_FILES=$(wildcard *.tex)

###############################################################################
#                                 Rules                                       #
###############################################################################

.PHONY: all clean

all: $(CO).pdf

$(CO).pdf: $(CO).tex $(CHANGED_FILES_OTHER)
	 # rubber --pdf $<
	 rubber --unsafe --pdf $<

clean:
	rm -f *.dvi *.log $(CO).blg $(CO).bbl $(CO).toc *.aux $(CO).out $(CO).lof
	rm -f $(CO).pdf
	rm -f *~
	rm -f *.synctex.gz
	rm -f $(EXTERNAL_FIGS)

#$(CO).pdf: $(CO).tex $(CHANGED_FILES_OTHER)
#	pdflatex $<
#	pdflatex $<
#	rubber --pdf $<
#	rubber-info --errors $<
#	rubber --unsafe --pdf $<
#	rubber-info --check $<
