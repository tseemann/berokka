
FASTA = test.fa
OUTDIR = out

.PHONY: test1

all: test1

test1: $(FASTA)
	../bin/berokka --force --outdir $(OUTDIR) --keepfiles $(FASTA)
	ls $(OUTDIR)
	grep '>' $(FASTA)
