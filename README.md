BugSigDB Curation Contribution: NTM Microbiota Signatures
Overview
This contribution documents the curation of a peer-reviewed research paper on pulmonary non-tuberculous mycobacterial (NTM) disease microbiota into BugSigDB, a curated database of microbial signatures associated with human health and disease.
Paper Curated
Title: Distinct lung microbiota community states are associated with pulmonary nontuberculous mycobacterial disease prognosis
Source: BMC Microbiology, Volume 25, Article 653 (2025)
DOI: https://doi.org/10.1186/s12866-025-04420-7
Study Location: Zhongshan Hospital, Shanghai, China (October 2018 - October 2021)
What Is This About?
NTM infections are increasingly common respiratory diseases that are difficult to diagnose and treat. This research paper analyzed lung microbiota samples from NTM patients and identified distinct microbial community types (pneumotypes) that predict treatment outcomes. Understanding these microbiota signatures is important for improving NTM patient care globally, including in resource-limited settings like Cameroon where NTM is often misdiagnosed as tuberculosis.
Contributions Made
Experiment 1: Pneumotype Comparison Within PNTM Patients
Groups Compared: Pneumotype 1 (dysbiotic, worse prognosis) vs. Pneumotype 2 (balanced microbiota, better prognosis)
Sample Sizes: 31 patients (Pneumotype 1) vs. 29 patients (Pneumotype 2)
Key Finding: Pneumotype 1 had only 31% treatment success rate vs. 63.6% for Pneumotype 2

Experiment 2: PNTM vs. Pulmonary Tuberculosis (PTB)
Groups Compared: PNTM patients vs. PTB (tuberculosis) patients
Sample Sizes: 69 PNTM patients vs. 46 PTB patients
Key Finding: PNTM and PTB have distinct microbial dysbiosis patterns despite both being mycobacterial infections
Signatures Documented
Total Signatures Created: 4
Signature 1a: Dysbiotic Pneumotype 1 - Increased taxa (pathobionts and anaerobes)
Signature 1b: Dysbiotic Pneumotype 1 - Decreased taxa (commensal bacteria)
Signature 2a: PNTM-specific microbiota - Increased taxa (vs. PTB)
Signature 2b: PNTM-specific microbiota - Decreased taxa (vs. PTB)
Each signature includes NCBI taxon identifiers and detailed descriptions of the microbial communities and their clinical significance.
Methodology
Sequencing Type: Whole Metagenome Sequencing (WMS)
Platform: BGI Sequencer
Statistical Tests: Kruskal-Wallis, PERMANOVA, DESeq2, Cox Proportional-Hazards Regression, Spearman Correlation, Random Forest Analysis
Significance Threshold: P < 0.05 with False Discovery Rate correction
Personal Motivation
As a Cameroonian, I became aware that in my country, a significant proportion of people diagnosed with tuberculosis actually have NTM instead - and diagnostic difficulty makes treatment extremely challenging. This curation was motivated by a desire to understand global NTM research and connect it to local health challenges in Cameroon, where improved NTM diagnosis and understanding could directly impact patient outcomes.
Learning Outcomes
This was my first experience with scientific data curation, and I gained:
Understanding of how microbial signatures are identified and formally documented
Deeper knowledge of NTM pathophysiology and the role of dysbiosis in treatment outcomes
Practical skills in mapping research findings into structured databases
Experience critically reading complex microbiome papers and extracting relevant experimental comparisons
Familiarity with BugSigDB's curation workflow and interface
Technical Observations & Future Work
While conducting this curation, I observed that the BugSigDB signature interface has performance limitations. I investigated the possibility of contributing technical improvements by locating the project source code, but was unable to find the main repository. I plan to continue investigating this and would be interested in contributing performance optimizations if the codebase becomes accessible.
How to Access This Curation
Link to BugSigDB entry: https://bugsigdb.org/41068590
The curation includes detailed metadata about study design, subject demographics, laboratory methods, and statistical analyses, along with the 4 documented microbial signatures.
Next Steps
Future contributions could include:
Curation of additional NTM microbiota studies, particularly from African populations
Investigation of BugSigDB performance optimization
Development of tools for applying these microbiota signatures in clinical practice

