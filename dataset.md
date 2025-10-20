## Dataset Description — Somatic Mutation Annotation File

This dataset contains **genomic mutations** identified from **tumor samples** using high-throughput DNA sequencing.
Each row represents a **single genetic variant** (mutation) detected in a patient’s tumor, along with detailed biological, clinical, and computational annotations.

The data follows the **MAF (Mutation Annotation Format)** commonly used by projects like **TCGA (The Cancer Genome Atlas)**.

---

### 1. Gene and Genomic Location

These columns describe **where in the genome** the mutation occurred.

| Column                               | Description                                                                                    |
| ------------------------------------ | ---------------------------------------------------------------------------------------------- |
| **Hugo_Symbol**                      | Official gene name according to the HUGO Gene Nomenclature Committee (e.g., *TP53*, *DNMT3A*). |
| **Entrez_Gene_Id**                   | Numerical identifier for the gene in the NCBI Entrez database.                                 |
| **Chromosome**                       | Chromosome where the mutation occurs (1–22, X, Y, MT).                                         |
| **Start_Position**, **End_Position** | Genomic coordinates of the mutation on the reference genome.                                   |
| **Strand**                           | Indicates whether the mutation is on the forward (+) or reverse (−) DNA strand.                |
| **NCBI_Build**                       | Version of the reference human genome (e.g., GRCh38).                                          |

---

### 2. Mutation Details

These fields describe **what kind of mutation it is** and how it changes the DNA or protein sequence.

| Column                                                             | Description                                                                                                                                    |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Variant_Classification**                                         | The biological consequence of the mutation — for example:                                                                                      |
|                                                                    | • *Missense_Mutation*: one amino acid is changed.                                                                                              |
|                                                                    | • *Nonsense_Mutation*: a premature stop codon ends the protein early.                                                                          |
|                                                                    | • *Frame_Shift_Ins* or *Frame_Shift_Del*: insertion/deletion changes the reading frame.                                                        |
|                                                                    | • *Silent*: DNA change that does not alter the amino acid sequence.                                                                            |
| **Variant_Type**                                                   | DNA-level change — e.g., SNP (single base change), INS (insertion), DEL (deletion).                                                            |
| **Reference_Allele**, **Tumor_Seq_Allele1**, **Tumor_Seq_Allele2** | Show the reference DNA base(s) and the observed base(s) in the tumor sample.                                                                   |
| **Consequence**                                                    | A standardized term for the mutation’s effect on the gene or protein (e.g., *missense_variant*, *frameshift_variant*, *splice_donor_variant*). |

---

### 3. Sample Information

These link each mutation to the specific tumor sample (and its matched normal sample).

| Column                          | Description                                                                      |
| ------------------------------- | -------------------------------------------------------------------------------- |
| **Tumor_Sample_Barcode**        | Unique identifier for the tumor sample (e.g., *TCGA-AB-2895-03A*).               |
| **Matched_Norm_Sample_Barcode** | Identifier for the patient’s normal (non-tumor) tissue sample.                   |
| **Center**                      | Sequencing or analysis center that processed the sample (e.g., Broad Institute). |
| **Sequencer**                   | Type of sequencing platform used (e.g., Illumina).                               |

---

### 4. Functional and Biological Annotations

These describe how the mutation may affect the resulting **protein** and its **biological role**.

| Column                                | Description                                                                                                                 |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **HGVSc**, **HGVSp**, **HGVSp_Short** | Standard HGVS notation showing the change at the DNA (c.) and protein (p.) level — e.g., *c.1762G>A* or *p.Val588Met*.      |
| **Protein_position**, **Codons**      | Show where in the protein the mutation occurs and what codon is affected.                                                   |
| **IMPACT**                            | Predicted severity of the mutation: *HIGH*, *MODERATE*, *LOW*, or *MODIFIER*.                                               |
| **SIFT**, **PolyPhen**                | Computational predictions of whether a mutation affects protein function (*deleterious*, *tolerated*, *probably damaging*). |
| **CLIN_SIG**                          | Known or predicted clinical significance (e.g., *pathogenic*, *likely benign*, *uncertain significance*).                   |
| **COSMIC**, **dbSNP_RS**              | Links to public mutation databases (COSMIC for cancer-specific mutations; dbSNP for general variants).                      |

---

### 5. Experimental Read Counts and Frequencies

These reflect **how strongly** the mutation is supported by sequencing data and how **rare** it is in populations.

| Column                           | Description                                                                                                                                                     |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **t_ref_count**, **t_alt_count** | Number of sequencing reads supporting the reference (normal) and alternate (mutated) allele in the **tumor** sample.                                            |
| **n_ref_count**, **n_alt_count** | Same counts for the **matched normal** sample.                                                                                                                  |
| **gnomAD_AF**, **1000G_AF**      | Population allele frequencies from global databases — show how common or rare the variant is. Low values usually indicate rare or disease-associated mutations. |

---

###  6. Quality Control and Metadata

| Column                                         | Description                                                       |
| ---------------------------------------------- | ----------------------------------------------------------------- |
| **Validation_Status**, **Verification_Status** | Indicate whether the mutation was experimentally validated.       |
| **Annotation_Status**                          | Notes whether the variant passed quality filters.                 |
| **PUBMED**, **GENE_PHENO**                     | References to publications or known gene–phenotype relationships. |

---

### Educational Summary

Mutations can range from harmless to highly disruptive:

* **Missense** → changes one amino acid (possible functional impact).
* **Nonsense** → introduces a stop signal (usually destroys protein).
* **Frameshift** → shifts reading frame (drastic effect).
* **Splice Site** → alters RNA processing.
* **Silent** → no amino acid change but might affect regulation.

Each mutation tells part of a story about how the **tumor’s genome evolved**, which can reveal **driver mutations**, **drug targets**, or **biological pathways** involved in cancer.

