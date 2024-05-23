# ParAquaSeq Repository

## Introduction

Welcome to the ParAquaSeq repository. This database is a part of a larger, innovative project aimed at addressing the significant impact of zoosporic parasites on both natural ecosystems and the microalgae biotech industry. Zoosporic parasites, which include fungi and fungi-like aquatic microorganisms, are crucial drivers of natural populations and can cause severe host mortality. Their economic impacts are particularly notable in the microalgae biotech industry, affecting the production of food ingredients, biofuels, pharmaceuticals, and nutraceuticals.

## Aims of ParAqua:
* Integration and Collaboration: Establish a dynamic European network that connects scientists, industries, and stakeholders. This network aims to optimize information exchange, equalize access to resources, and develop a joint research agenda.
* Information Compilation: Compile and make available comprehensive information on the occurrence of zoosporic parasites and their relationships with hosts.
* Impact Assessment: Elucidate the drivers and evaluate the impacts of parasitism in both natural and man-made aquatic environments.
* Tool Development: Implement new tools for monitoring and preventing infections, and create protocols and a Decision Support Tool for detecting and controlling parasites in the microalgae biotech industry.
* Applied Knowledge: Explore whether the developed tools can be applied for monitoring lakes and reservoirs, feeding back industry knowledge to ecological research.
* Education and Training: Organize Short-Term Scientific Missions and Training Schools for early-stage scientists and managers, with a specific focus on inclusivity and integration of both scientific and applied expertise.

## Database Objective
The specific objective of this database (D1.WG3) within the ParAqua project is to compile and integrate a searchable database on zoosporic parasites across Europe. This database aims to:

* Catalogue Expertise: Identify and catalogue available expertise based on a comprehensive questionnaire survey.
* Inventory Parasite Effects: Document and analyze the effects of zoosporic parasites on algal hosts in both natural and biotechnological contexts.

## Accessing to Zoosporic Databases
- [Metadata](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/ParAquaSeq_curated.xlsx)
- [Fasta file](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/sequences.fasta)
- [Fasta file for VSEARCH]()
- [Database for blast search]()

## Using a BLAST Database
In this section, we will guide you through the process of perform BLAST searches.

### Prerequisites
Before you begin, ensure that you have BLAST (Basic Local Alignment Search Tool) installed on your system/server. You can download and install BLAST from the [NCBI BLAST+ download page.](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastDocs&DOC_TYPE=Download)
### Download the BLAST Database
Download the provided BLAST database files from the repository. The database consists of several files with a common prefix (Seq_blast_db). Ensure all files are downloaded to the same directory.
### Run a BLAST Search
Once you have downloaded the database files, you can run a BLAST search against the database using the blastn command. Here’s an example of how to run a nucleotide BLAST search:
```shell
blastn -query query_sequence.fasta -db  Seq_blast_db -out results.txt -outfmt 6
```
- query query_sequence.fasta: Specifies the query sequence file in FASTA format.
- db path/to/my_blast_db: Specifies the path and prefix of the provided database files.
- out results.txt: Specifies the output file to write the results.
- outfmt 6: Specifies the output format (tabular).

## Using the Provided Database with VSEARCH
In this section, we will guide you through the process of using the provided database to perform searches with VSEARCH.
### Prerequisites
Before you begin, ensure that you have VSEARCH installed on your system. You can download and install VSEARCH from the [VSEARCH GitHub repository.](https://github.com/torognes/vsearch)
### Download the VSEARCH Database
Download the provided VSEARCH fasta file from the repository.
### Run a VSEARCH Search
Once you have downloaded the database files, you can run a search against the database using VSEARCH. Here’s an example of how to perform a search:
```shell
vsearch --usearch_global query_sequence.fasta --db vsearch.fasta --id 0.9 --blast6out results.txt
```
- usearch_global: Specifies the search mode for global alignment.
- db path/to/my_vsearch_db: Specifies the path and prefix of the provided database files.
- id 0.9: Specifies the minimum percentage identity for matches (e.g., 90%).
- blast6out results.txt: Specifies the output file in BLAST tabular format (outfmt 6).

```shell
vsearch --sintax query_sequences.fasta --db path/to/sintax_db.fasta --tabbedout results.sintax --sintax_cutoff 0.8
```
- sintax query_sequences.fasta: Specifies the query sequence file in FASTA format.
- db path/to/sintax_db.fasta: Specifies the path to the SINTAX database file.
- tabbedout results.sintax: Specifies the output file for the SINTAX results in tab-separated format.
- sintax_cutoff 0.8: Specifies the confidence threshold for taxonomic assignment (e.g., 0.8 for 80% confidence).
  
## Report issues
Please report any issue on [GitHub](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/issues)

