# Curation Walk-through for Experiment 1  
_Curator: Nina Takang_  
_Date: 2025-10-21_

## 📖 Purpose  
This document provides a clear, step-by-step guide for curating **Experiment 1** from the study:  
> “Gut microbiota dysbiosis promotes coronary heart disease comorbid with depression through lipopolysaccharides and Toll-like receptor 4.”  

The goal is to help future BugSigDB curators understand how to extract, interpret, and document data accurately and transparently.

---

## 🔍 Experiment Overview  
- **Experiment ID:** 40999363 / Experiment 1  
- **Study Context:**  
  Fecal microbiota transplantation (FMT) in healthy rats receiving either autologous feces (Control) or feces from rats with coronary heart disease comorbid with depression (CHDWD).  
- **Groups:**  
  - *Group 0 (Control):* Healthy rats receiving autologous fecal matter transplant – n = 7  
  - *Group 1 (Case):* Healthy rats receiving fecal matter transplant from CHDWD rats – n = 7  
- **Host species:** Rattus norvegicus  
- **Body site:** Feces  
- **Sequencing type:** 16S rRNA (V3-V4, Illumina)  
- **Data transformation:** Relative abundances  
- **Statistical tests:** Mann-Whitney / T-Test  
- **Significance threshold:** p = 0.05 (no MHT correction)

---

## 🧭 Step-by-Step Curation Workflow  

### 1. Identify and Review the Experiment  
Locate **Experiment 1** on BugSigDB and open the corresponding research article.  
Read the **Methods**, **Results**, and **Figure Legends** sections carefully. Focus on sample grouping, sequencing methods, and which bacterial taxa were reported as significantly different.

---

### 2. Extract Metadata  
Record key details directly from the paper, including:
- Host organism  
- Sample body site  
- Sequencing platform and variable region  
- Type of data transformation  
- Statistical test used  
- Significance threshold and correction method  

Make sure all values match exactly what is reported in the publication.

---

### 3. Define the Groups  
Document clear and descriptive names for each group:  
- **Group 0:** Healthy rats receiving autologous fecal matter transplant  
- **Group 1:** Healthy rats receiving fecal matter transplant from diseased rats  

Then, define **Group 1** precisely using context from the study, e.g.:
> “Healthy rats receiving fecal microbiota transplantation from rats with coronary heart disease comorbid with depression (CHDWD), leading to altered gut microbiota and depressive behaviors.”

---

### 4. Determine Sample Sizes  
Note the number of subjects included in analysis after any exclusions.  
In this study, both groups had **n = 7** rats after outlier removal.

---

### 5. Curate Signatures  
For each **signature** (set of taxa with similar direction of change):

- Identify bacteria **increased** in Group 1 (FMT-Disease).  
- Identify bacteria **decreased** in Group 1 (FMT-Disease).  
- Use the exact taxon names as listed in the paper or tables.  
- Include the **source** (e.g., Figure 3, Table 2).  

**Example format:**

| Direction | Description | Source |
|------------|--------------|---------|
| Increased | *Allobaculum*, *Bifidobacterium*, *Candidatus Parasutterella gallistercoris*, *Enterorhabdus*, *Oligella*, *Pygmaiobacter*, *Turicibacter*, *Lachnospiraceae_FCS020_group* | Figure 3, Table 2 |
| Decreased | *Abiotrophia*, *Anaerovibrio*, *Odoribacter*, *Paludicola*, *Tyzzerella*, *UCG_004*, *Coriobacteriaceae_UCG_002*, *[Eubacterium]_ventriosum_group* | Figure 3, Table 2 |

---

### 6. Document Assumptions and Notes  
If you made any interpretation choices, document them clearly.  
For example:
> “Sample sizes were confirmed after exclusion of outliers as described in the Methods section.”  
> “Taxon names were standardized to match NCBI taxonomy.”

---

### 7. Review for Accuracy and Consistency  
Before finalizing, ensure:
- Group labels and sample sizes match across all sections.  
- Statistical methods and significance levels are consistent.  
- Each signature has a clear description and verified taxon names.

---

## ✅ Tips and Insights  
- **Be precise:** Small details (like sequencing platform or significance test) can affect reproducibility.  
- **Stay transparent:** Always note how you handled ambiguous or missing information.  
- **Think like a reviewer:** Ask whether someone unfamiliar with the paper could replicate your curation from your notes.  
- **Keep learning:** Reviewing multiple studies improves both technical and biological understanding.

---

## 🔗 References  
- Curated record: [Experiment 1 – BugSigDB 40999363](https://bugsigdb.org/40999363/Experiment_1)  
- Original article: Wang et al., “Gut microbiota dysbiosis promotes coronary heart disease comorbid with depression…”  
- Related reading: [Why microbiome signatures need both increased and decreased bacteria](https://medium.com/@takangnina0/why-microbiome-signatures-need-both-increased-and-decreased-bacteria-fd6fa3e69a35)

---

**Prepared by:**  
Nina Takang  
Outreachy Contributor — 2025 Curation Phase
