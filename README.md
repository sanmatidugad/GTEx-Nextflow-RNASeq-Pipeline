# GTEx-Nextflow-RNASeq-Pipeline
This repository contains a Nextflow RNA-Seq analysis pipeline tailored for GTEx data analysis. The pipeline aligns RNA-Seq reads using STAR, marks duplicates, quantifies with RSEM, and performs QC with RNA-SeQC. The Dockerfile provides a containerized environment with all the tools. It is designed for parallel processing and executed on AWS Batch.
