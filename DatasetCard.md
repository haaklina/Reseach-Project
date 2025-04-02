## Dataset Summary:
Phylogenetic Tree Project
Title:
Phylogenetic Tree of Gene Sequences from National Center for Biotechnology Information (NCBI)
Description:
This dataset contains gene sequence data (nucleotide) obtained from the (NCBI) (https://www.ncbi.nlm.nih.gov/nuccore/?term=Ascidian) in FASTA format and a corresponding Nexus file used for generating phylogenetic trees. The purpose of this project is to construct and analyze phylogenetic relationships among Ascidian species using sequence data.

## Data format:
All data are DNA sequences in standard fasta files, grouped either by species (in the case of the animals) or in sequencing run (in the case of the ascidians samples).

## Languages:
English

## Data Sources:
Data retrieved from: NCBI (National Center for Biotechnology Information)

## Data Instances: 
File Formats: .fasta for gene sequences, .nexus for phylogenetic tree generation
sequences.fasta: Contains around 600bais pairs (bp) gene sequences different tunicate species (demo species collected: source: https://seanet.stanford.edu/Urochordata) in FASTA format.

## Documentation for Source Datasets
### Tunicate datasets

| Species Name  | Genetic Marker  | Tunicate Population   | Sources  |
|---|---|---|---|
| *Pyura chilensis* | 614 bp, DNA, CO1* gene | Solitary | Gao et al 2023 |

## Preprocessing and Data Formatting
I downloaded all the genomes as fasta files and renamed them to include the genus and species in the file names including population's name.

For the read files, I downloaded them in fastq format, and if a species had multiple read files from the same sequencing platform, I concatenated them into a single file for all downstream processing. I used ALiView for alignment and trimming all the short read files to remove adapter sequences, though I did trim them for quality as well. 

Collect them into a final fasta file and after alignment I got organized data in Nexus format for analysis in MrBayes or R program for generating tree.

## Usage: 
Analysis goals (phylogenetic tree construction).

## Limitations: 
Biases or limitations (e.g., incomplete gene sequences).


