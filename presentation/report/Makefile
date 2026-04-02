FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))

FILTERS =
OPTIONS =
PDF_ENGINE =
PDF_OPTIONS =
FORMAT_OPTIONS =

### Cross references
## Use pandoc-crossref (https://github.com/lierdakil/pandoc-crossref)
FILTERS += --filter pandoc-crossref
###
PDF_ENGINE += --pdf-engine=lualatex --pdf-engine-opt=--shell-escape
OPTIONS += --number-sections
BIB_OPTIONS = --citeproc
PDF_BIB_OPTIONS = --citeproc

%.docx: %.md
	-pandoc "$<" $(FILTERS) $(OPTIONS) $(BIB_OPTIONS) -o "$@"

%.pdf: %.md
	-pandoc "$<" $(FILTERS) $(PDF_ENGINE) $(PDF_OPTIONS) $(PDF_BIB_OPTIONS) $(FORMAT_OPTIONS) $(OPTIONS) -o "$@"

all: $(FILES)


clean:
	-rm $(FILES) *~

cleanall: clean
