Overview and objective, purpose of the project:

Ascidians play an important role in the invertebrate ecology of California aquatic ecosystems. In addition, they have a great contribution in medical science. Bays are full of nonindigenous and some native ascidians that are under investigation to learn their existence. The central coast of California remains understudied since it has been dominated by native species, although the problematic invasive didemnid is threatening to escape from San Francisco Bay to the outer coast at this time. It is significant to identify in this region which species are present on the outer coast, and to update taxonomic analyses with additional reproductive characters, habitat and distributional characters, and molecular information. The ascidians species have a similar colony and zooid outlook, which is why it can be challenging to distinguish them by using identification keys which nearly provided an ambiguous result. The present proposal describes the project that I wish to undertake in order to contribute to finding a solution to these questions/problems: what are the morphological and reproductive patterns of ascidian species? Why are the characteristics influenced by distribution of outer bay species? What species are located on outer coast and which morphological characteristics are used to define them as well as what is currently reported as being on coast? The main objective is to reassess tunicate species diversity in central CA by combining varied kinds of data, including molecular, morphological, ecological, and historic information. All these investigations will specify what species are, where and when they were recently present, and assist in defining accurate species identification.

Phylogenetic-Tree-Project

Data Description: Summary of input data:

data/FASTA.txt Sequences.fasta (Gene sequences from NCBI)

data/nexus.text Tree_data.nexus (Nexus file for tree generation)

Output Analysis (trees, plots)

Scripts (Analysis scripts)

Phylo_analysis.Rmd (R Markdown for loading and analysis)

Dataset_card.md (Dataset card for context)

README.md (Project overview and instructions)

Getting started prerequisites • R or RStudio (for analysis scripts) • Required R packages: ape, phangorn, seqinr Installation

Methodology: Tools and methods used:
The data will be analyzed using Bayesian inference methods. I will analyze the nucleotide sequence data and translated amino acid sequence to compare the resulting topologies. As the amino acid data will be conducted using the Bayesian inference (BI) method, I will use the MrBayes 3.0b4 program followed by Turon and López-Legentil (2004), where I will include a model of amino acid substitution particularly developed for mtDNA-encoded proteins and the mtREV model. 
For creating phylogenetic tree of selected species of tunicate ascidians as a demo, I have chosen mostly solitary ascidians except three of them are compound which are Synocium kincaidi, Distaplia occidentalis and Diplosoma listerianum. They have been taken from different literatures and tunicate website:  https://seanet.stanford.edu/Urochordata (Table 1). My sample subset sequenced at the cytochrome c oxidase subunit I (COX1) gene (N = 20), all are identified as tunicate ascidian species in with 99-100% identify match at least >500 (longer is better by searching nucleotide region) in the NCBI GeneBank database (Prentice et al 2020). It is important to have similar or closer lengths gene bp of the species that provides robust phylogenomic tree for each species. Afterwards, I compiled fasta files of the gene for all species by following copy fasta from gene bank and paste to text editing BBedit, then save file of fasta sequences for all the 20 species. After that, I aligned sequences in AliView and realigned everything as well as possible to trim because some sequences may contain irregular length for maintaining the similar lengths for run convenient in the end and saved it as nexus file. I prepared the nexus file to run in the MrBayes program. In that case, when I open nexus file I can see the section as BEGIN DATA; DIMENSIONS NTAX = 20 NCHAR = 1488 FORMAT DATATYPE = DNA GAP = MISSING =?; MATRIX. This view provides information to understand number of taxa and total characters, e.g. length of sequences. Then I started MrBayes and it showed mcmcp number of gene is 1000000, print and sample frequencies are 1000. Here, number of gene is running for 1 million or it may need to up it to 10 million, depending on the resolution of the tree. I saved this nexus file again, now ready to run it in the MrBayes. I copied the file into the folder that contained MrBayes, particularly the bin folder where I can paste the nexus file. Here the file is ran until it says run done and the p-value is <0.01 (this means average standard deviation of split frequencies). If the p-value would display >0.01 then I will need to continue to run more generations. In my case, I ran two times in order to get the p-value <0.01. First time the p-value showed 0.02 which means p-value is too high, then I selected yes and specified the number of generations and inputted 1000000 to run the generations again. It then showed the p-value as 0.009147<0.01. After this happened the program was closed and all materials are saved in the bin folder. To look at the result I need to analyze the data from the saved files in the bin folder. I saw four new folders named sample.nex.run1.p, sample.nex.run1.t, sample.nex.run2.p and sample.nex.run2.t. Run 1 and 2.p shows the probabilities/p-value for all the different trees created, run 1 and 2.t contains all the trees populated. MrBayes saves every 1000th tree so if I ran 1 million times my .t file contains 1000 trees. The forwarding step was to ‘burn’ or delete all the trees with very low probabilities, these were typically my first couple trees. Then I created a consensus tree with my better tree. In this regard, I opened the Beast program which is located within the bin folder called the Tree Annotator. In this stage, I selected the number of trees to burn and put 100. 10% of the trees can burn so if I have a 1000, I can select 100 trees to burn. This number can be increased if I want to run more generations, I will need to just take 10% of that number to burn. In the settings menu, I altered median height to mean height and rest remained the same. Now I put/add in one of my .t files as the input file and made sure .t file is copied into the same folder as the tree annotator program in order for it to open. After that I named my output file as same.tre. In visualization, I viewed my final tree. I open the Figtree and it showed the tree (figure 1). I then re-rooted, checked the node labels box and showed all the values between all species. These values provides the insight of evolutionary biology of these species.
![image](https://github.com/user-attachments/assets/3bc97fb6-0e03-4be2-8b0e-25ed4c98a523)


Clone the repository:
git clone https://github.com/haaklina/Reseach-Project.git
Install necessary R packages:
install.packages("MrBayes")
install.packages("AliView") install.packages("Beast") Usage Running the Analysis
Load the data and scripts:
Load packages
library(MrBayes)
library(AliView)
library(Beast)
Read data

Instructions: How to run the analysis:

fasta_data <- read.fasta("data/sequences.fasta") nexus_data <- read.nexus("data/tree_data.nexus")
Perform phylogenetic tree construction and visualization. Output • The /output directory will contain generated phylogenetic trees, sequence alignments, and plots.

Contact For questions or collaboration opportunities, please contact me haaklina or hakther@sfsu.edu.






