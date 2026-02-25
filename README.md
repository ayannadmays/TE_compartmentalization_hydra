# TE_compartmentalization_hydra
Undergraduate project identifying globally compartmentalized TEs in Hydra vulgaris AEP and 105

##General steps
1. download genome
2. obtain and process RepeatModeler libraries (we'll use a custom one I already made)
   - used Blast to identify TE sequences from RepeatModeler library
   - removed the ones that were species transcripts (e-value < 1e-25) (not TEs)
3. Annotated TEs by running RepeatMasker on the genome using the library
4. Converted the resulting repeatmasker file to bed file (https://github.com/rmhubley/RepeatMasker/blob/master/util/RM2Bed.py)
5. Used bedtools to extract 50 kilobases upstream and downstream of all genes (flanking regions) from bed file
6. Overlapped flanking regions with coding sequences (CDS) with bedtools intersect to get only information from coding regions of DNA
7. Calculate TE density with bedtools coverage for noncoding flanking regions of each gene (wanted to see how much of the area around genes/CDS are made up of TEs; 90th or 95th percentile)
8. GO (gene ontology) to see what the function of genes are that are compartmentalized

