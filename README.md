# berokka
Trim, circularise and orient long read bacterial genome assemblies

## Introduction

There is already a good piece of software to trim/circularise and orient 
genome assemblies called [Circlator](https://sanger-pathogens.github.io/circlator/).

You should try Berokka when:
1. Circlator fails on your data even after [troubleshooting](https://github.com/sanger-pathogens/circlator/wiki/Troubleshooting)
2. You only have the contig files and do not have the corrected reads anymore
3. Your contigs are simple cases
4. You can't get Circlator or its dependencies working for some reason

## Installation

### Homebrew

```
brew tap homebrew/science
brew tap tseemann/bioinformatics-linux
brew install berokka
```
Using Homebrew will install all the dependencies for you:
[Linux](http://linuxbrew.sh) or [MacOS](http://brew.sh)

### Source

```
git clone https://github.com/tseemann/berokka.git
./berokka/berokka -h
```
You will need to install all the dependencies manually:
* [BioPerl](http://bioperl.org/) >= 1.6
* [BLAST+](ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST/) >= 2.4.0
* [SAMtools](http://www.htslib.org/download/) >= 1.3

## Usage

FIXME

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
