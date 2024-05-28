# ParAquaSeq Repository  <img src="https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/paraqua-logo.png" alt="Logo" width="100" />

## Introduction

Zoosporic parasites (i.e. fungi and fungi-like aquatic microorganisms) constitute important drivers of natural populations, causing severe host mortality. Economic impacts of parasitic diseases are notable in microalgae biotech industry, affecting production of food ingredients, biofuels, pharma- and nutraceuticals.. While scientific research on this topic is gaining traction by increasing studies elucidating the functional role of zoosporic parasites in natural ecosystems, we are currently lacking integrated and interdisciplinary efforts for effectively detecting and controlling parasites in the microalgae industry. To fill this gap we propose to establish an innovative, dynamic European network connecting scientists, industries and stakeholders to optimize information exchange, equalize access to resources and to develop a joint research agenda. ParAqua aims at compiling and making available all information on the occurrence of zoosporic parasites and their relationship with hosts, elucidate drivers and evaluate impacts of parasitism in natural and man-made aquatic environments. We aim to implement new tools for monitoring and prevention of infections, and to create protocols and a Decision Support Tool for detecting and controlling parasites in the microalgae biotech production. Applied knowledge on zoosporic parasites can feed back from industry to ecology, and we therefore will explore whether the developed tools can be applied for monitoring lakes and reservoirs. Short-Term Scientific Missions and Training Schools will be organised specifically for early- stage scientists and managers – with a specific focus on ITC – with the aim to share and integrate both scientific and applied expertise and increase exchange between basic and applied researchers and stakeholders.

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
- [Metadata](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/ParAquaSeq_curated_240515.xlsx)
  <details><summary> Click to see details</summary>
  <p>
    Contains the information of all the databases sequences, includes XXX fields:
    
    - Id: Sequence identificator
    - Behavior
    - VerbatimScientificName
    - Synonims: All the sinonyms available for the seqeunce
    - Scientific name
    - ....
  </p>
  </details>
  
- [Fasta file](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/sequences.fasta)
  <details><summary> Click to see details</summary>
  <p>

    Contains the sequences in FASTA format for easy access and analysis. The ID of each sequence in the FASTA file consists of several fields separated by underscores (`_`):
    - **ID**: The unique sequence identifier
    - **GenBank Code**: The GenBank accession number for the sequence.
    - **Region**: The region of the gene or genome that the sequence represents. (ITS, 18S or )
    - **Taxa**: The taxonomic classification of the organism from which the sequence was obtained. Includes 7 ranks: Kingdom (k), Phylum (p), Class (c), Order (o), Family (f), Genere (g), Specie (s).
    </p>
    </details>
- [Fasta file for VSEARCH](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/sequences_vsearch.fasta)
  <details><summary> Click to see details</summary>
  <p>
    
    Contains the file fasta to perform a taxonomic assignment with VSEARCH. The identificator consist on:
    - **ID**: sequence identifier
    - **taxa inforamtion**: "taxa=" follows of the 7 taxonomic rankss: Kingdom (k), Phylum (p), Class (c), Order (o), Family (f), Genere (g), Specie (s).
    </p>
    </details>
      
## Using a BLAST Database
In this section, we will guide you through the process of perform BLAST searches.

<details><summary> Click to see details</summary>
<p>
 
  ### Prerequisites
  Before you begin, ensure that you have BLAST (Basic Local Alignment Search Tool) installed on your system/server. You can download and install BLAST from the [NCBI BLAST+ download page.](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastDocs&DOC_TYPE=Download)
  ### Download the BLAST Database
  Download the provided BLAST database files from the repository. The database consists of several files ([.nhr](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/blast_ddbb.nhr), [.nin](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/blast_ddbb.nin) and [.nsq](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/blast_ddbb.nsq)) with a common prefix (blast_ddbb). Ensure all files are downloaded to the same directory.
  ### Run a BLAST Search
  Once you have downloaded the database files, you can run a BLAST search against the database using the blastn command. Here’s an example of how to run a nucleotide BLAST search:
  ```shell  
  blastn -query query_sequence.fasta -db  blast_ddbb -out results.txt -outfmt 6
  ```
  - query query_sequence.fasta: Specifies the query sequence file in FASTA format.
  - db path/to/my_blast_db: Specifies the path and prefix of the provided database files.
  - out results.txt: Specifies the output file to write the results.
  - outfmt 6: Specifies the output format (tabular).
</p>
</details>

## Using the Provided Database with VSEARCH
In this section, we will guide you through the process of using the provided database to perform searches with VSEARCH.

<details><summary> Click to see details</summary>
<p>

  ### Prerequisites
  Before you begin, ensure that you have VSEARCH installed on your system. You can download and install VSEARCH from the [VSEARCH GitHub repository.](https://github.com/torognes/vsearch)
  ### Download the VSEARCH Database
  Download the provided [VSEARCH fasta file](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/sequences_vsearch.fasta) from the repository.
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

</p>
</details>

## NCBI Search and Parasite Information Extraction Script

This R script performs a search on the NCBI database to extract sequence information and associated parasite data. The output is an Excel file containing the extracted data.

<details><summary> Click to see details</summary>
<p>

  ### Prerequisites
  Before you begin, ensure that you have R installed on your system. You can download and install R from [CRAN](https://cran.r-project.org/).
  Download the [Rscript](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/scripts/NCBI_Search_script.R) and this [file](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/blob/main/files/ParasiteList_UniMain.txt). Ensure all files are downloaded to the same directory.

  ### Run the script
  - Open the script and modify if it's nedded the lines after the comment `# NOTE`
  - Run the script in your R environment or RStudio
</p>
</details>
  
## Report issues
Please report any issue on [GitHub](https://github.com/NataliaTimoneda/ZoosporicParasitesRepository/issues)

