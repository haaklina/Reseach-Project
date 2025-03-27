Overview and objective, purpose of the project:

Ascidians play an important role in the invertebrate ecology of California aquatic ecosystems. In addition, they have a great contribution in medical science. Bays are full of nonindigenous and some native ascidians that are under investigation to learn their existence. The central coast of California remains understudied since it has been dominated by native species, although the problematic invasive didemnid is threatening to escape from San Francisco Bay to the outer coast at this time. It is significant to identify in this region which species are present on the outer coast, and to update taxonomic analyses with additional reproductive characters, habitat and distributional characters, and molecular information. The ascidians species have a similar colony and zooid outlook, which is why it can be challenging to distinguish them by using identification keys which nearly provided an ambiguous result. The present proposal describes the project that I wish to undertake in order to contribute to finding a solution to these questions/problems: what are the morphological and reproductive patterns of ascidian species? Why are the characteristics influenced by distribution of outer bay species? What species are located on outer coast and which morphological characteristics are used to define them as well as what is currently reported as being on coast? The main objective is to reassess tunicate species diversity in central CA by combining varied kinds of data, including molecular, morphological, ecological, and historic information. All these investigations will specify what species are, where and when they were recently present, and assist in defining accurate species identification.

Phylogenetic-Tree-Project

Data Description: Summary of input data:

data/FASTA.txt Sequences.fasta (Gene sequences from NCBI)

Tree_data.nexus (Nexus file for tree generation)

Output (Analysis output (trees, plots)

Scripts (Analysis scripts)

Phylo_analysis.Rmd (R Markdown for loading and analysis)

Dataset_card.md (Dataset card for context)

README.md (Project overview and instructions)

Getting started prerequisites • R or RStudio (for analysis scripts) • Required R packages: ape, phangorn, seqinr Installation

Methodology: Tools and methods used:

Clone the repository:
git clone https://github.com/akther/Phylogenetic-Tree-Project.git cd Phylogenetic-Tree-Project
Install necessary R packages (if not already installed):
install.packages("ape")
install.packages("phangorn") install.packages("seqinr") Usage Running the Analysis
Load the data and scripts:
Load packages
library(ape)
library(phangorn)
library(seqinr)
Read data

Instructions: How to run the analysis:

fasta_data <- read.fasta("data/sequences.fasta") nexus_data <- read.nexus("data/tree_data.nexus")
Perform phylogenetic tree construction and visualization. Output • The /output directory will contain generated phylogenetic trees, sequence alignments, and plots.

Contact For questions or collaboration opportunities, please contact me haaklina or hakther@sfsu.edu.






