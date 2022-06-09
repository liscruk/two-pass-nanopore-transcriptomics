### two-pass-nanopore-transcriptomics
A two pass minimap and salmon based snakemake pipeline to extract and estimate transcript abundances from nanopore long read data.

The main idea is that we can get accurate estimation of non-reference transcripts by first mapping with minimap in a splice aware fashion.
This has the advantage that transcripts that may be trunctated or have larger mismatches are getting assgined aswell. In a second pass, a transcriptome gets generated from the coordinates produced by stringtie and the first mapping round.
Then minimap2 is run again against this transcriptome and finally salmon is used for quantification.

Additionally, unmapped reads are also extracted since, assuming they are good quality, may hold some meta information may it be contaminations or other non-reference material.

The pipeline also produces some quality benchmarks.
