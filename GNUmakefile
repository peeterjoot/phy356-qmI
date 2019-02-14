THISDIR := phy356-qmI
THISBOOK := phy356

export BOOKSUBVER := 1
export BOOKMAJVER := 0
export REVISIONNUMBER := 8

#.revinfo/gitCommitDateAsMyTime.tex:\newcommand{\myTime}{April 2018}\newcommand{\myVersion}{version V0.117\xspace}
VER := $(shell grep Version .revinfo/gitCommitDateAsMyTime.tex | sed 's/.*{//;s/.xspace.*//;')

include ../latex/make.bookvars

FIGURES := ../figures/phy356-qmI

SOURCE_DIRS += chapters
SOURCE_DIRS += $(FIGURES)

GENERATED_PDFS += desaiTypos.pdf
#GENERATED_PDFS += reproSaveSize.pdf

#ONCEFLAGS := -justonce

include ../latex/make.rules

dist:
	cp $(THISBOOK).pdf $(THISBOOK).$(VER).pdf

# a for annotate (releases).
tag:
	git tag -a $(THISBOOK).$(VER).pdf

desaiTypos.pdf :: desaiTyposInnards.tex
