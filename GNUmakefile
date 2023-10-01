THISDIR := phy356-qmI
THISBOOK := phy356

BIBLIOGRAPHY_PATH := classicthesis_mine
HAVE_OWN_CONTENTS := 1
HAVE_OWN_TITLEPAGE := 1
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/Index.tex
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/ContentsAndFigures.tex
BOOKTEMPLATE := ../latex/classicthesis_mine/ClassicThesis2.tex

include make.revision
include ../latex/make.bookvars

# comment this out for online pdf version (uncomment for KDP)
#PRINT_VERSION := 1
#ifdef KINDLE_VERSION
#PARAMS += --kindle
#endif

ifdef PRINT_VERSION
SUBFIGDIR := bw
else
SUBFIGDIR := color
endif

ifndef PRINT_VERSION
PARAMS += --no-print
endif
#PARAMS += -subfig $(SUBFIGDIR)
DISTEXTRA := $(SUBFIGDIR)
ifdef PRINT_VERSION
DISTEXTRA := $(DISTEXTRA).kdp
#DISTEXTRA := kdp
endif

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
