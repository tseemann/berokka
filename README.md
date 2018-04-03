[![Build Status](https://travis-ci.org/tseemann/berokka.svg?branch=master)](https://travis-ci.org/tseemann/berokka) [![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

# berokka
Trim, circularise, orient & filter long read bacterial genome assemblies

## Introduction

There is already a good piece of software to trim/circularise and orient
genome assemblies called [Circlator](https://sanger-pathogens.github.io/circlator/).
Please try that first!

You should only try Berokka if:

1. You only have the contig files and do not have the corrected reads anymore
2. Your contigs are simple cases with clear overhang and could be done manually with BLAST
3. Circlator fails on your data even after [troubleshooting](https://github.com/sanger-pathogens/circlator/wiki/Troubleshooting)

**NOTE:** orientation to *dnaA* or *rep* genes is not yet implemented,
nor is filtering against Pacbio control sequences.

## Installation

### Homebrew
Using Homebrew will install all the dependencies for you:
[Linux](http://linuxbrew.sh) or [MacOS](http://brew.sh)
```
brew install brewsci/bio/berokka  # COMING SOON!
```

### Conda
```
conda -c bioconda -c conda-forge berokka  # COMING SOON!
```

### Source
```
git clone https://github.com/tseemann/berokka.git
./berokka/bin/berokka -h
```
You will need to install all the dependencies manually:
* [BioPerl](http://bioperl.org/) >= 1.6 (for `Bio::SeqIO` and `Bio::SearchIO`)
* [BLAST+](ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST/) >= 2.3.0 (for `blastn`)

## Usage

### Input

Input should be completed long-read assemblies in FASTA format, such as those from
[CANU](https://github.com/marbl/canu)
or
[HGAP](https://github.com/PacificBiosciences/Bioinformatics-Training/wiki/HGAP-in-SMRT-Analysis).

### Command line

```
% berokka --outdir trimdir canu.contigs.fasta
<snip>

% ls trimdir/
01.input.fa
02.trimmed.fa
03.results.tab

% cat trimdir/03.results.tab

#sequence   old_len new_len trimmed
tig00000000 5461026 5448790 12237
tig00000001  234319  207334 26986
tig00000002  138825  113601 25225
tig00000003   57075   43297 13779
```

### Output

Filename | Format | Description
---------|--------|--------------
01.input.fa | FASTA | All the input sequences
02.trimmed.fa | FASTA | The (possibly) trimmed sequences
03.results.tab | TSV | Summary of results

The `02.trimmed.fa` output has been augmented with new header data (unless `--noanno` used):
* `circular=true` - inform that this is a circular sequence (Rebaler uses this)
* `overhang=N` - informs that N bp were trimmed off
* `len=N` - the new contig length if it was present (Canu adds this)
* `suggestCircular=yes` if the `no` version was present (Canu adds this)

## Etymology

[Berocca](https://en.wikipedia.org/wiki/Berocca) is a brand of effervescent drink and vitamin tablets containing vitamin B and C.
It is a popular cure for a [hangover](https://en.wikipedia.org/wiki/Hangover). A key role of the `berokka` tool is to remove the
"overhang" that occurs at the ends of long-read assemblies of circular genomes.

## Feedback

Please file questions, bugs or ideas to the [Issue Tracker](https://github.com/tseemann/berokka/issues)

## License

[GPLv3](https://raw.githubusercontent.com/tseemann/berokka/master/LICENSE)

## Citation

Not published yet.

## Authors

* Torsten Seemann
* Anna Syme
