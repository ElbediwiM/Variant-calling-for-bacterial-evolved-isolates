# Variant-calling-for-bacterial-evolved-isolates
Genomic analysis of evolved Salmonella Typhimurium isolates  with colisitin antibiotic
# Salmonella Typhimurium Experimental Evolution Variant Calling Pipeline

This project analyzes genomic variants in *Salmonella* Typhimurium isolates from a colistin antibiotic experimental evolution experiment (Day 1 to Day 68). The pipeline processes raw FASTQ files into filtered variant calls (VCF) using ATCC 14028 as the reference genome.

---

## **Project Structure**
project_root/
├── data/
│ ├── raw_fastq/ # Raw FASTQ files (copied or symlinked here)
│ ├── aligned/ # SAM/BAM alignment files
│ ├── sorted/ # Sorted and deduplicated BAM files
│ └── variants/ # VCF files (raw and filtered)
├── reference/
│ ├── ATCC14028.fna # Reference genome
│ └── indexes/ # BWA/SAMtools indexes
├── scripts/ # Pipeline bash/snakemake scripts
├── fastqc_raw/ # FastQC reports for raw reads
├── fastqc_trimmed/ # FastQC reports for trimmed reads
└── README.md # This file


---

## **Dependencies**
Install tools via Conda:
```bash
conda create -n variant_calling -c bioconda fastqc trimmomatic bwa samtools picard bcftools
conda activate variant_calling

