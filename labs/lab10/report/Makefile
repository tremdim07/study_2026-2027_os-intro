FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))

LATEX_FORMAT =

FILTER = --filter pandoc-crossref

%.docx: %.md
	pandoc "$<" $(FILTER) -o "$@"

%.pdf: %.md
	pandoc "$<" $(FILTER) --pdf-engine=xelatex -o "$@"

all: $(FILES)
	@echo "Скомпилированы файлы: $(FILES)"

clean:
	rm -f $(FILES) *~