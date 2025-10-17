Sputum bacterial microbiota signature as a surrogate for predicting disease progression of nontuberculous mycobacterial lung disease/Experiment 1
BugSigDB Curation Guide: Approaching Microbiome Papers
Based on PMID 38740280 - NTM-LD Progression Study
You can find a link to the curated paper on here https://bugsigdb.org/38740280
Introduction
This guide walks through how to systematically approach and curate a microbiome paper for BugSigDB. We use the NTM-LD progression study as an example, highlighting decision points and reasoning at each step.

Step 1: Understand the Study Design
What to look for:

Is this observational or experimental?
If observational, is it cross-sectional or longitudinal?
Where were subjects recruited/samples collected?

For this paper: Read the introduction and methods carefully to find the enrollment timeline and follow-up period. The paper explicitly states: "We conducted a prospective longitudinal follow-up study." Patients were enrolled between May 2020–December 2021 and then followed for 2 years. This is not a one-time cross-sectional snapshot but rather a study tracking the same subjects over an extended period.
Decision: Longitudinal Observational
Why this matters: Different study designs indicate different strengths and limitations for the data.

Step 2: Identify the Study Population & Location
What to look for:

Where were patients recruited? (country/city/institution)
What host species? (humans, mice, environmental?)
What was the final analytic sample size?

For this paper: Methods section states enrollment was at "Kaohsiung Medical University Hospital and National Taiwan University Hospital." Looking up these institutions identifies them as located in Taiwan. The host species is Homo sapiens (human). The sample flow proceeded as follows: 200 patients initially screened, 159 recruited after applying diagnostic criteria, and finally 126 analyzed after excluding one sample due to low read count.
Key decision: Use the final analytic sample size of 126, not the initial screening number of 200. The Curation Policy specifies: "Sample sizes should be the final analytic sample size used for the experiment." This matters because you are reporting numbers that were actually used in the statistical analysis.

Step 3: Identify Each Experiment/Comparison
What to look for:

What are the authors comparing? (disease vs. healthy, treatment vs. control, time 1 vs. time 2?)
Is there more than one comparison?
Do not force multiple experiments—only curate distinct, clear comparisons

For this paper: The primary comparison is between the progression group (n=49) and nonprogression group (n=77). This is defined by outcome status at the 2-year follow-up mark. The results section clearly focuses on this single main comparison as the study's central finding. Supplementary analyses (examining differences by NTM species or cavitary status) are exploratory secondary work.
Decision: Curate one experiment focusing on the primary comparison.
Reasoning: Do not force artificial experiments. Stick to what the paper actually presents as the main finding. Forcing multiple experiments from secondary analyses waters down the curation and misrepresents the study's focus.

Step 4: Define Your Groups Precisely
What to look for:

Who is in Group 0? (control/reference/unexposed)
Who is in Group 1? (case/exposed/outcome of interest)
What are the exact sample sizes for each group?

For this paper:

Group 0 = Nonprogressors: Did NOT develop disease progression over 2 years (n=77) — this is your reference/baseline
Group 1 = Progressors: DID develop disease progression over 2 years (n=49) — this is your comparison group

Naming principle:

Group 0 is the "negative" or reference state
Group 1 is the "positive" or outcome state you're characterizing

Why this matters: Clear group definitions prevent confusion about which direction the abundance changes go. If you mix this up, your signatures will be backwards.

Step 5: Define the Condition (Carefully)
What to look for:

What disease or health state is being studied?
Avoid describing measurement or methodology—describe the actual clinical condition
Check the EFO ontology for the standardized term

Common pitfall: Using "microbiome measurement" or "bacterial measurement" as the condition. This is wrong. Measurement is what you're doing, not what you're studying.
For this paper:

What you might want to say: "NTM-LD disease progression"
Why that's problematic: "Progression" is the variable measured, not the condition itself
What to actually enter: Search EFO for standardized term → "Pulmonary non-tuberculous mycobacterial infection"
The condition is the underlying disease; progression vs. nonprogression is captured in your Group 0 vs. Group 1 contrast

Process:

Identify the disease: nontuberculous mycobacterial lung disease
Formalize it using EFO: Pulmonary non-tuberculous mycobacterial infection
Enter exact term from dropdown

Why this matters: The condition field enables proper database searching and cross-study comparison. Vague or incorrect conditions make the database less useful.

Step 6: Document Exclusion Criteria (Antibiotics Only)
What to look for:

Did the study exclude patients on antibiotics? If so, for how long?
The Curation Policy only captures antibiotic exclusions

For this paper: The methods section states: "patients who used systemic antibiotics...within 3 months prior to enrollment." You would enter this as: 3 months. The Curation Policy restricts this field to antibiotic exclusions only. While the paper also excluded patients with active TB, malignancy, HIV infection, and pregnancy, these are not captured in the BugSigDB curation for reasons of standardization.
Reasoning: Antibiotics significantly alter microbiota composition, making this the most critical exclusion criterion for microbiome studies. Other exclusion criteria like malignancy or immunosuppression don't have standardized reporting across studies, so BugSigDB focuses on antibiotic exclusion for consistency across its database.

Step 7: Identify the Body Site and Sequencing Details
What to look for:

Where did they collect samples? (sputum, stool, oral, skin?)
What sequencing technology? (16S vs. shotgun)
If 16S, what variable regions? (V3-V4, V4, etc.)
What sequencing platform? (Illumina, Ion Torrent, etc.)

For this paper:

Body site: Sputum (respiratory tract)
Sequencing type: 16S rRNA
Variable regions: V3-V4
Platform: Illumina MiSeq, 2 × 300 bp paired-end

Location: Methods section, "Sputum sample collection and sequencing" and "Bioinformatics analysis"
Why this matters: These technical details affect what organisms can be detected and how results compare across studies.

Step 8: Identify the Statistical Approach
What to look for in methods:

What statistical test did they use for differential abundance? (Mann-Whitney U, t-test, DESeq2, LEfSe, etc.)
Did they transform the data? (raw counts, relative abundance, log-transformed, etc.)
What was their significance threshold? (p < 0.05, q < 0.1, etc.)
Did they correct for multiple hypothesis testing? (Bonferroni, FDR, etc.)

For this paper:
ItemAnswerWhere FoundData transformationRelative abundance"ASV abundance dataset was then organized by species and genus level"Statistical testMann-Whitney U test"nonparametric statistical methods, including the Wilcoxon rank-sum"Significance thresholdP < 0.05Standard methods sectionMHT correctionNoNo mention of Bonferroni, FDR, or q-values in main analysisLDA scoreN/ALEfSe was one of 6 methods, but not the primary test
Important distinction:

They used six feature selection methods (including LEfSe) to identify consistent taxa
But their primary differential abundance test was Mann-Whitney U, not LEfSe
Therefore, LDA score is not applicable

Why this matters: Different statistical approaches have different assumptions and power. This context is crucial for interpreting results.

Step 9: Check Alpha Diversity Results
What to look for:

Did they test alpha diversity (within-sample diversity)?
Which metrics? (Shannon, Simpson, Chao1, Faith's PD, etc.)
Were results statistically significant?
Did diversity increase, decrease, or stay unchanged?

For this paper:

Results state: "The progression group exhibited significantly lower α-diversity than did the nonprogression group according to the Shannon and Simpson indexes"
Record as:

Shannon: Decreased in Group 1
Simpson: Decreased in Group 1
Other metrics: Leave blank (not reported)



Why this matters: Alpha diversity (species richness/evenness) is a key marker of microbiota health. Lower diversity often indicates dysbiosis.

Step 10: Identify Confounders & Matching
What to look for:

Are baseline characteristics reported? (age, sex, smoking, etc.)
Are they matched between groups or balanced statistically?
Critical: Did the authors use these as covariates in a regression model?

For this paper:

Table 1 shows baseline characteristics (age, sex, BMI, comorbidities, etc.)
Conclusion: "The baseline characteristics...did not differ significantly between the two groups"
But nowhere do they state: "We adjusted for X in a regression model"
No stratified analyses (e.g., separate results for men vs. women)

Decision: No confounders controlled for
Why this matters:

Just because groups are balanced doesn't mean confounders were controlled in the analysis
Only model adjustment (regression) or stratification count as "controlling for"
Bivariate tests (Mann-Whitney U, t-test) cannot adjust for confounders


Step 11: Determine What to Curate - Single vs. Multiple Signatures
Key principle from Curation Policy:

"A separate signature should be created for the increased and decreased group."

What to look for:

Are there taxa significantly increased in Group 1?
Are there taxa significantly decreased in Group 1?
Create separate signatures for each direction

For this paper:
Signature 1 (Increased in Group 1):

Seven genera identified consistently across all six feature selection methods
Higher abundance in progression group
Source: Figure 3B

Signature 2 (Decreased in Group 1):

Four genera mentioned as "more abundant in nonprogression group"
Lower abundance in progression group
Source: Figure 2B and Results text

Decision: Create both signatures to show the complete microbiota shift
Why this matters: Both increased and decreased taxa are biologically meaningful. Protective bacteria (Streptococcus, Prevotella) are lost in progressors, while pathogenic bacteria (Burkholderia) proliferate. The full picture matters.

Step 12: Extract Taxa and Find NCBI IDs
What to look for:

Which specific taxa showed differential abundance?
What is the lowest (most specific) taxonomic rank reported for each?

For this paper:
All taxa are reported at genus level:
Signature 1 (Increased):

Burkholderia
Pseudomonas
Sphingomonas
Candidatus Saccharibacteria
Phocaeicola
Pelomonas
Phascolarctobacterium

Signature 2 (Decreased):

Streptococcus
Prevotella
Veillonella
Fusobacterium

Process to find NCBI IDs:

Try typing taxon name into BugSigDB autocomplete
If autocomplete shows it, use that (already in database)
If not, go to NCBI Taxonomy Browser (https://www.ncbi.nlm.nih.gov/Taxonomy)
Search for the exact taxon name
Copy the NCBI Taxonomy ID (integer)
Paste into BugSigDB

Why this matters: NCBI IDs standardize taxonomy across the database, accounting for synonyms and name changes.

Step 13: Document Source & Biological Context
What to look for:

Where in the paper are the differential abundance results shown? (which figure/table?)
What is the biological or clinical significance?

For this paper:
Signature 1 (Increased):

Source: Figure 3B (box plots of relative abundances)
Biological context: These seven genera were identified through consensus of six differential abundance methods, used to build a predictive model (AUC 0.871) for disease progression. Associated with virulence pathways (biofilm formation, chemotaxis, secretion systems).

Signature 2 (Decreased):

Source: Figure 2B and Results text
Biological context: These are commensal bacteria commonly found in healthy individuals. Their loss indicates dysbiosis and reduced colonization resistance.

Why this matters: Context helps future users understand the clinical relevance of these signatures.

Common Pitfalls to Avoid

Confusing Group 0 and Group 1: Remember: Group 1 is the "case" or outcome group you're characterizing
Using measurement terms as conditions: "Microbiome measurement" is not a condition
Including all taxa mentioned: Only include significantly differentiated taxa
Forcing multiple experiments: If it's not a distinct comparison, don't curate it separately
Forgetting decreased signatures: Both increased AND decreased matter
Using incorrect taxonomy: Always verify NCBI IDs; synonyms can be confusing
Misidentifying the statistical test: Know what the primary differential abundance test was, not just what methods they used


Checklist Before Finalizing

 Study design clearly identified (longitudinal observational)
 Location identified (Taiwan)
 Host species identified (Homo sapiens)
 Body site identified (Sputum)
 Final analytic sample size correct (126)
 Groups defined (Progression n=49, Nonprogression n=77)
 Condition term from EFO dropdown ("Pulmonary non-tuberculous mycobacterial infection")
 Antibiotic exclusion documented (3 months)
 Sequencing details complete (16S, V3-V4, Illumina MiSeq)
 Statistical test identified (Mann-Whitney U)
 Data transformation identified (Relative Abundance)
 Significance threshold entered (0.05)
 MHT correction status noted (No)
 Alpha diversity results recorded (Shannon and Simpson decreased)
 Matching/Confounders verified (None)
 Both signatures created (Increased and Decreased)
 NCBI taxonomy IDs verified for all taxa
 Source figures/tables documented
 Descriptions added with biological context


Key Takeaway
Careful curation means:

Read thoroughly to understand the actual study design and comparisons
Use standardized terminology (EFO, NCBI taxonomy)
Respect what the paper shows rather than forcing interpretations
Document decisions so future curators understand your reasoning
Include both increased and decreased signatures for complete biological picture