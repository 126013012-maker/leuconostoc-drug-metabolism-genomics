# Drug-Metabolizing Potential of Lactic Acid Bacteria: Leuconostoc Genomic Analysis

> Exploratory comparative genomics of drug-metabolizing genes in *Leuconostoc* using 16S phylogenetics, BLASTp and OrthoFinder.

## Project Overview

This project explores the potential presence of drug-metabolizing genes in *Leuconostoc*, a group of lactic acid bacteria, through comparative genomic analysis.

**Project Type:** Mini Project (BIN300)  
**Degree:** B.Tech Bioinformatics  
**Institution:** SASTRA Deemed University  
**Academic Year:** 2024–2025  
**Project Team:** Three members  

Completed as part of a three-member team under faculty guidance.

**Note:** This repository documents only my individual contribution: the *Leuconostoc* analysis.

> An exploratory, time-limited student project. Findings are homology-based predictions and have not been experimentally validated.

## Background

Gut bacteria can chemically modify drugs and change their effects. Drug-metabolizing genes in lactic acid bacteria are not well characterized, and comparative genomic studies in this area are limited.

This project explores drug-metabolizing gene candidates in *Leuconostoc* using genome data, phylogenetic analysis, protein sequence similarity searches and ortholog identification.

## My Contribution

My individual contribution focused on the genomic analysis of *Leuconostoc*.

1. Retrieved 71 complete *Leuconostoc* genomes from NCBI.
2. Built a 16S rRNA neighbour-joining phylogenetic tree using MEGA12.
3. Curated strain-level drug-metabolizing gene data using MagMD, AGORA, literature and NCBI GenBank/RefSeq cross-mapping.
4. Performed BLASTp from the Linux command line against *Leuconostoc* proteomes.
5. Built a local protein BLAST database using `makeblastdb`.
6. Predicted orthologs using OrthoFinder.
7. Used Bash commands (`grep`) to extract drug-metabolizing gene IDs from the OrthoFinder `Orthogroups.tsv` output.

## Tools and Technologies

- **NCBI:** Genome retrieval and sequence information
- **MEGA12:** 16S rRNA phylogenetic analysis
- **BLAST+:** Protein sequence similarity search
- **OrthoFinder:** Ortholog identification and orthogroup analysis
- **MagMD:** Drug-metabolizing gene information
- **AGORA:** Gut microbial metabolic reconstruction data
- **Linux Shell (Bash):** Command-line operations and data extraction

## Workflow

The analysis followed these major steps:

**NCBI Genome Retrieval → 16S rRNA Phylogenetic Tree → Drug-Metabolizing Gene Query Set → BLASTp Search → OrthoFinder Analysis → Gene ID Extraction**

The commands used during the analysis are documented in [`commands.md`](commands.md).

## Results

- Putative drug-metabolism homologs were found in *L. lactis*, *L. mesenteroides* and *L. carnosum*.
- OrthoFinder placed 122,284 genes (99.0%) into 4,055 orthogroups.
- Only one orthogroup contained genes from all species.

These results represent sequence-based predictions and do not confirm actual drug-metabolizing activity.

## Figures and Analysis Outputs

The following figures illustrate the major stages of my analysis.

| Figure | Description |
|---|---|
| [Strain-Level Genome Records](images/leuconostoc_strain_identification.png.jpeg) | Genome records retrieved from NCBI, including chromosome and plasmid sequences |
| [16S Phylogenetic Tree](images/leuconostoc_16s_tree.png.jpeg) | 16S rRNA neighbour-joining phylogenetic tree of *Leuconostoc* strains |
| [BLASTp Results](images/blastp_leuconostoc.png.jpeg) | BLASTp hits against *Leuconostoc* proteomes |
| [OrthoFinder Output](images/orthofinder_leuconostoc.png.jpeg) | OrthoFinder orthogroup analysis output |

## Limitations

- Many BLASTp hits showed low-to-moderate sequence identity, so gene function was inferred based on homology.
- No experimental or structural validation was performed.
- Limited project time restricted deeper analysis, including stricter filtering and functional annotation.

## What I Learned

Through this project, I gained experience in:

- Retrieving and working with genome data from NCBI.
- Understanding 16S rRNA phylogenetic analysis.
- Performing protein sequence similarity searches using BLASTp.
- Understanding ortholog identification using OrthoFinder.
- Working with Linux command-line tools and Bash commands.
- Interpreting genomic predictions carefully and understanding their limitations.

## Possible Next Steps

- Apply stricter sequence identity and coverage cutoffs.
- Include additional functional annotation.
- Compare top candidate genes with published literature.
- Explore further validation of predicted drug-metabolizing genes.

## Repository Structure

```text
leuconostoc-drug-metabolism-genomics/
│
├── images/
│   ├── leuconostoc_strain_identification.png.jpeg
│   ├── leuconostoc_16s_tree.png.jpeg
│   ├── blastp_leuconostoc.png.jpeg
│   └── orthofinder_leuconostoc.png.jpeg
│
├── README.md
├── commands.md
└── dmg_query_table.csv
```

## Data Sources

- [NCBI Genome Database](https://www.ncbi.nlm.nih.gov/genome/)
- MagMD – Microbiome Drug Metabolism Database
- AGORA – Gut microbial metabolic reconstruction resource

Genome sequences are not included in this repository. They are available through the NCBI Genome Database.
