THISDIR := phy356-qmI
THISBOOK := phy356

include make.revision
include ../latex/make.bookvars

FIGURES := ../figures/phy356-qmI

SOURCE_DIRS += chapters
SOURCE_DIRS += $(FIGURES)

GENERATED_PDFS += desaiTypos.pdf
#GENERATED_PDFS += reproSaveSize.pdf

#ONCEFLAGS := -justonce
DO_SPELL_CHECK := $(shell cat spellcheckem.txt)

include ../latex/make.rules

.PHONY: spellcheck
spellcheck: $(patsubst %.tex,%.sp,$(filter-out $(DONT_SPELL_CHECK),$(DO_SPELL_CHECK)))

%.sp : %.tex
	spellcheck $^
	touch $@

scrpage2.sty : ../latex/scrpage2.sty
	cp $^ $@

desaiTypos.pdf :: desaiTyposInnards.tex
