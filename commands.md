# Commands Used

Command-line steps from the *Leuconostoc* analysis, run in a Linux terminal.
Replace file and database names with your own where marked.

## 1. Build a local protein BLAST database

Combine the protein FASTA files of the selected *Leuconostoc* strains into one
file, then build the database:

```bash
makeblastdb -in combined_proteins.faa -dbtype prot -out leu_db
```

- `-in`: combined protein sequences of the selected strains
- `-dbtype prot`: protein database (for BLASTp)
- `-out`: database name (use the name you actually used)

## 2. BLASTp search

Known drug-metabolizing proteins (the curated query set, see
[`data/dmg_query_table.csv`](../data/dmg_query_table.csv)) were searched
against the local database.

```bash
# TODO: add your exact blastp command here, for example:
# blastp -query dmg_queries.faa -db leu_db -out blastp_results.txt -outfmt 6
```

## 3. Ortholog prediction

OrthoFinder was run on the folder of protein FASTA files (one per genome).

```bash
# TODO: add your exact OrthoFinder command here, for example:
# orthofinder -f <folder_with_protein_fasta_files>
```

OrthoFinder output used: `Orthogroups.tsv`
(orthogroups, with the genes of each genome listed per orthogroup).

## 4. Extract drug-metabolizing gene hits with `grep`

`gene_ids.txt` holds the UniProt IDs of the known drug-metabolizing proteins,
one ID per line.

List which of those IDs occur in the orthogroups (prints only the matched IDs):

```bash
grep -Fof gene_ids.txt Orthogroups.tsv
```

Save the full orthogroup rows that contain those IDs:

```bash
grep -Ff gene_ids.txt Orthogroups.tsv > trial.tsv
```

Check genes OrthoFinder left unassigned to any orthogroup:

```bash
grep -Fof gene_ids.txt Orthogroups_UnassignedGenes.tsv
```

Flags: `-F` fixed strings (not regex), `-f` read patterns from a file,
`-o` print only the matching part.
