# leuconostoc-drug-metabolism-genomics
Exploratory comparative genomics of drug-metabolizing genes in Leuconostoc using 16S phylogenetics, BLASTp and OrthoFinder.

# Drug-Metabolizing Potential of Lactic Acid Bacteria: Leuconostoc Genomic Analysis

Mini project (BIN300), B.Tech Bioinformatics, SASTRA Deemed University, 2024-25.
Completed as part of a three-member team under faculty guidance.
**This repository documents only my individual contribution: the Leuconostoc analysis.**

> An exploratory, time-limited student project. Findings are homology-based
> predictions and have not been experimentally validated.

## Background
Gut bacteria can chemically modify drugs and change their effect.
Drug-metabolizing genes in lactic acid bacteria are poorly characterized,
and comparative genomic studies are scarce.

## My Contribution
1. Retrieved 71 complete Leuconostoc genomes from NCBI
2. Built a 16S rRNA neighbour-joining phylogenetic tree in MEGA12
3. Curated strain-level drug-metabolizing gene data (MagMD, AGORA, literature,
   NCBI GenBank/RefSeq cross-mapping)
4. Ran BLASTp of known drug-metabolizing proteins against Leuconostoc proteomes
5. Predicted orthologs with OrthoFinder

**Tools:** NCBI, MEGA12, BLAST+, OrthoFinder, MagMD, AGORA

## Results
- Putative drug-metabolism homologs found in L. lactis, L. mesenteroides and L. carnosum
- OrthoFinder placed 122,284 genes (99.0%) into 4,055 orthogroups
- Only one orthogroup contained genes from all species

## Limitations
- Many BLASTp hits had low-to-moderate sequence identity, so function is only inferred
- No experimental or structural validation
- Limited time for deeper analysis (stricter filtering, functional annotation)

## What I Learned
Genome retrieval, phylogenetics, homology search, ortholog inference,
and interpreting predictions cautiously.

## Possible Next Steps
Apply identity/coverage cutoffs, add functional annotation, and check
top candidates against the literature.
