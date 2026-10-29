# leuconostoc-drug-metabolism-genomics

> Exploratory comparative genomics of drug-metabolizing genes in *Leuconostoc* using 16S phylogenetics, BLASTp and OrthoFinder.

**Drug-Metabolizing Potential of Lactic Acid Bacteria: Leuconostoc Genomic Analysis**

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
1. Retrieved 71 complete *Leuconostoc* genomes from NCBI
2. Built a 16S rRNA neighbour-joining phylogenetic tree in MEGA12
3. Curated strain-level drug-metabolizing gene data (MagMD, AGORA, literature,
   NCBI GenBank/RefSeq cross-mapping)
4. Ran BLASTp from the Linux command line (built a local protein BLAST
   database with `makeblastdb`) against *Leuconostoc* proteomes
5. Predicted orthologs with OrthoFinder
6. Used bash (`grep`) to extract the drug-metabolizing gene IDs from the
   OrthoFinder `Orthogroups.tsv` output

**Tools:** NCBI, MEGA12, BLAST+, OrthoFinder, MagMD, AGORA, Linux shell (bash)

## Workflow
NCBI genomes → 16S rRNA tree (MEGA12) → curated drug-metabolizing gene (DMG) query set
→ BLASTp (local database) → OrthoFinder orthogroups → `grep` extraction of DMG hits

The commands I used are in [`workflow/commands.md`](workflow/commands.md).

## Results
- Putative drug-metabolism homologs found in *L. lactis*, *L. mesenteroides* and *L. carnosum*
- OrthoFinder placed 122,284 genes (99.0%) into 4,055 orthogroups
- Only one orthogroup contained genes from all species

## Figures
| Figure | Description |
|---|---|
| [Strain-level genome records](images/leuconostoc_strain_identification.png.jpeg) | Genome records retrieved from NCBI (chromosome and plasmid sequences) |
| [16S phylogenetic tree](images/leuconostoc_16s_tree.png.jpeg) | 16S rRNA phylogenetic tree of *Leuconostoc* strains |
| [BLASTp results](images/blastp_leuconostoc.png.jpeg) | BLASTp hits against *Leuconostoc* proteomes |
| [OrthoFinder output](images/orthofinder_leuconostoc.png.jpeg) | OrthoFinder orthogroup output |

## Limitations
- Many BLASTp hits had low-to-moderate sequence identity, so function is only inferred
- No experimental or structural validation
- Limited time for deeper analysis (stricter filtering, functional annotation)

## What I Learned
Genome retrieval, phylogenetics, homology search, ortholog inference,
Linux command-line workflows, and interpreting predictions cautiously.

## Possible Next Steps
Apply identity/coverage cutoffs, add functional annotation, and check
top candidates against the literature.

## Repository Structure
- `README.md`: project overview
- `images/`: figures from my analysis
- `workflow/commands.md`: command-line steps
- `data/dmg_query_table.csv`: curated DMG query table (small file only)

Genome sequences are not included. They are available from the
[NCBI Genome database](https://www.ncbi.nlm.nih.gov/genome/).

## Data Sources
NCBI Genome, MagMD (microbiome drug metabolism database), AGORA
(gut microbe metabolic reconstructions).

## License
MIT License. See [`LICENSE`](LICENSE). Third-party databases (NCBI, MagMD, AGORA)
keep their own terms of use.
