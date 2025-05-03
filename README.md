# nf-dnaseq

A Nextflow pipeline for primary analysis of DNA sequence data for variant calling analyses.

## Features

- 🧬 Accepts both SE and PE reads
- 🚀 Runs with Singularity on SLURM HPC
- 📊 MultiQC summary report
- 📝 Output summary CSV for downstream use

## Quick Start

### 1. Clone the repo

```bash
git clone https://github.com/javibio-git/nf-dnaseq.git

```

### 2. Create a sample sheet

Create a CSV file named `samplesheet.csv` in the root directory of the repository. The sample sheet should contain the following columns:

```bash
sample_id,species,fastq_1,fastq_2
S1,human,/absolute/path/S1_R1.fastq.gz,/absolute/path/S1_R2.fastq.gz
S2,mouse,/absolute/path/S2_R1.fastq.gz,
```
### 3. Run the pipeline

```bash
nextflow run nf-dnaseq/ \
	--samplesheet ./samplesheet.csv \
	--outdir ./results \
	-profile slurm \
	-resume
```
