THISDIR := phy356-qmI
THISBOOK := phy356
BASEVER := a9de223

include ../latex/make.bookvars

FIGURES := ../figures/phy356-qmI

SOURCE_DIRS += chapters
SOURCE_DIRS += $(FIGURES)

GENERATED_PDFS += desaiTypos.pdf
#GENERATED_PDFS += reproSaveSize.pdf

#ONCEFLAGS := -justonce

include ../latex/make.rules

desaiTypos.pdf :: desaiTyposInnards.tex
