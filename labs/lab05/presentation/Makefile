SRC = presentation.md
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
FILES += $(patsubst %.md, %.html, $(wildcard *.md))

FILTERS = -F pandoc-crossref
PDF_ENGINE = --pdf-engine=xelatex
PDF_OPTIONS =
PDF_FORMAT_OPTIONS = -t beamer --slide-level=2

REVEALJS_THEME = beige

%.pdf: %.md
	-@pandoc "$<" $(FILTERS) $(PDF_ENGINE) $(PDF_OPTIONS) $(PDF_FORMAT_OPTIONS) -o "$@"

%.html: %.md
	-@pandoc "$<" --embed-resources --standalone -t revealjs -V theme=$(REVEALJS_THEME) -o "$@"

all: $(FILES)

clean:
	-@rm -f $(FILES) *~

cleanall: clean