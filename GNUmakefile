THISDIR := phy356-qmI
THISBOOK := phy356

export BOOKSUBVER := 1
export BOOKMAJVER := 0
# This isn't a good way to version.  It depends on the local git reflog history count.
export REVCOUNTSTART := 1

include ../latex/make.bookvars

FIGURES := ../figures/phy356-qmI

SOURCE_DIRS += chapters
SOURCE_DIRS += $(FIGURES)

GENERATED_PDFS += desaiTypos.pdf
#GENERATED_PDFS += reproSaveSize.pdf

#ONCEFLAGS := -justonce

include ../latex/make.rules

desaiTypos.pdf :: desaiTyposInnards.tex
