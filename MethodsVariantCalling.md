## Variant Calling

There are a total of 5 steps in variant calling. 

### 1) Alignment:
Tools used for this purpose are BWA(Burrow Wheel Alligner),Speedseq,Bowtie2,BFAST,Illumina Isaak WGS,etc. Using the BWA aligner, in here. BWA is a software package for mapping low-divergent sequences against a large reference genome, such as the human genome. It consists of three algorithms: BWA-backtrack, BWA-SW and BWA-MEM.The first algorithm is designed for Illumina sequence reads upto 100bp,while the rest two for longer sequences ranged from 70bp to 1Mbp.

## 2) Generate Reads:
For the second step of getting the reads, we use the fastq-dump function which allows to split files SRR6808334 and gets the specific .log and .err function.
 
## 3) Somatic Variant Calling: 
Somatic variant calling includes steps like SNP , Indels, CNVs and SVs.After getting the reads from SRR6808334, we are trying to trim thte reads using Trimmomatic. Trimmomatic helps to trim the read files and distinguish between the paired and unpaired fastq files. Trimmomatic as a more flexible and efficient preprocessing tool, which could correctly handle paired-end data. The value of NGS read preprocessing is demonstrated for both reference-based and reference-free tasks. Trimmomatic is shown to produce output that is at least competitive with, and in many cases superior to, that produced by other tools, in all scenarios tested.

## 4) Indexing Genomes & Germline Variant Calling:
Genomes are subsequently indexed. Germline variant calling is performed.A germline variant caller generally has a ploidy-based genotyping algorithm built in to part of the algorithm/pipeline. Germline variant caller uses SNPs,Indels,CNVs and SVs as well.

## 5) Align Reads:
Reads are aligned using BWA mem and are then sorted by the same algorithm. The reads are then indexed and a VCF file is produced using DeepVariant. The variants are filtered and annotated using the tools like Snpedd,snpsift,annovar,Frequency db,gnomad, dbsnp and RareVariantVis.

Data is finally visualised using tools, GV ,UCSC and RareVariantVis. The plots are available in heatmaps,circos plots,scatter plots, log2 plots,etc

## References
[1] Burrows-Wheeler Aligner
https://bio-bwa.sourceforge.net/

[2] Human genetic variation: EMBL-EBI Training
Embl-Ebi
https://www.ebi.ac.uk/training/online/courses/human-genetic-variation-introduction/

[3] Comparison of three variant callers for human whole genome sequencing
Supernat et al.
https://www.nature.com/articles/s41598-018-36177-7
