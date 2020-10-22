# ![nfcore/test-datasets](docs/images/test-datasets_logo.png)
Test data to be used for automated testing of the nf-core/eager archaeodiet pipeline

## Repository Contents

The test data of nf-core/archaeodiet contains the following:

1. MALT (v0.5.0) database of 'Target' taxa 
  - NC_012681.1 Coelodonta antiquitatis mitochondrion, complete genome
  - NC_007596.2 Mammuthus primigenius mitochondrion, complete genome
  - NC_011112.1 Ursus spelaeus mitochondrion, complete genome
2. MALT (v0.5.0) database of 'Contaminant' taxa
  - NC_006853.1 Bos taurus mitochondrion, complete genome
  - NC_040970.1 Gallus gallus isolate ZJ mitochondrion, complete genome
  - NC_012920.1 Homo sapiens mitochondrion, complete genome

## Test Data construction notes

### Databases

FASTA files for MALT databases were downloaded from [NCBI Genome](https://www.ncbi.nlm.nih.gov/genome).

MALT v0.5.0 was used to index the FASTAs for each database, using the [`megan-nucl-Jul2020.db.zip`](https://software-ab.informatik.uni-tuebingen.de/download/megan6/) taxa ID mapping file and with the following command. 

```bash
malt-build \
-i test-datasets/databases/malt/contaminant/*.fasta \
-s DNA -d test-datasets/databases/malt/contaminant/ \
-t 16 \
-mdb assets/megan-nucl-map-Jul2020.db
```
