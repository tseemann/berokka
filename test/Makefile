
BEROKKA = ../bin/berokka
OPTS = 
FASTA = test.fa
OUTDIR = out

.PHONY: test1 issue13

all: test1

test1: $(FASTA)
	$(BEROKKA) $(OPTS) --force --outdir $(OUTDIR) --keepfiles $(FASTA)
#	ls $(OUTDIR)
#	grep '>' $(FASTA)
#	grep '>' $(OUTDIR)/02.trimmed.fa

issue13: issue13.fa
	$(BEROKKA) $(OPTS) --force --outdir $@ --keepfiles $<
#	ls $@
#	grep '>' $@/02.trimmed.fa
