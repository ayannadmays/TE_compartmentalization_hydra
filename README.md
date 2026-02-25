# TE_compartmentalization_hydra
Undergraduate project identifying globally compartmentalized TEs in Hydra vulgaris AEP and 105

##General steps
1. download genome
2. obtain and process RepeatModeler libraries (we'll use a custom one I already made)
   - used Blast to identify TE sequences from RepeatModeler library
   - removed the ones that were species transcripts (e-value < 1e-25) (not TEs)
3. Annotated TEs with RepeatMasker and converted to repeatmasker file to bed file (https://github.com/rmhubley/RepeatMasker/blob/master/util/RM2Bed.py)
4. Used bedtools to extract flanking regions from bed file
5. Extracted flanking regions/coding sequences overlap witrh bedtools intersect
6. Calculate TE density with bedtools coverage for noncoding flanking regions of each gene (compartmenalized = 90th or 95th)
7. GO (gene ontology) to see what the function of genes are that are compartmentalized

