# MORRISON-1-public
Katie M. Campbell, Meelad Amouzgar, Shannon M. Pfeiffer, Timothy R. Howes, Egmidio Medina, Michael Travers, Gabriela Steiner, Jeffrey S. Weber, Jedd D. Wolchok, James Larkin, F. Stephen Hodi, Silvia Boffo, Lisa Salvador, Daniel Tenney, Tracy Tang, Marshall A. Thompson, Christine N. Spencer, Daniel K. Wells, and Antoni Ribas. _Prior anti-CTLA-4 therapy impacts molecular characteristics associated with anti-PD-1 response in advanced melanoma._ Cancer Cell, April 10, 2023.

DOI: [https://doi.org/10.1016/j.ccell.2023.03.010](https://doi.org/10.1016/j.ccell.2023.03.010)

This repository contains the processed genomics and transcriptomics data, with harmonized clinical annotation, used in the above Cancer Cell publication.

## DATA DICTIONARY
### Clinical
**Subjects-CancerCell-MORRISON1-metadata.tsv**: Metadata file describing subjects from the reported study.
- subject.id=unique subject identifier
- sample.tumor.type=tumor type (cutaneous, acral, mucosal, uveal, unknown)
- meddra.disease.preferred.name=MedDRA coded disease type
- subject.age=subject age
- subject.sex=subject sex
- treatment.regimen.name=treatment regimen
- bor=best overall response defined by RECIST
- pfs=progression free survival (in months, see Note)
- os=overall survival (in months, see Note)
- previous.treatment=prior treatment group (previously received anti-CTLA-4 or anti-CTLA-4 naive)
- cohort=cohort described in manuscript (CheckMate 038=038, CheckMate 064=064, CheckMate 067=067, Gide, et al.=gide, Liu, et al.=liu, Van Allen, et al.=va)

_Note:_ Event status was not available, so the authors express precaution in survival analysis.

### Whole exome sequencing (WES)
**WES-CancerCell-MORRISON1-metadata.tsv**: Metadata file describing samples and subjects from the reported WES data.
- sample.id=unique sample identifier
- subject.id=unique subject identifier
- matched.normal=matched normal WES identifier
- sample.tumor.type=tumor type
- cohort=cohort described in manuscript
- timepoint.id=timepoint of sample in the context of the treatment regimen
- treatment.regimen.name=treatment regimen
- bor=best overall response defined by RECIST
- response=RECIST: as CRPR, PD, or SD
- previous.treatment=prior treatment group
- subject.age=subject age
- subject.sex=subject sex
- sample.freetext.anatomic.site=anatomical site of tumor
- purity=tumor purity estimated by Sequenza
- ploidy=tumor ploidy estimated by Sequenza
- contamination=estimated contamination by GATK CalculateContamination
- tmb=quantified tumor nonsilent TMB in mutations per megabase

**WES-CancerCell-MORRISON1-variants.tsv**: File containing all variants detected across all samples.
- sample.id=unique sample identifier
- subject.id=unique subject identifier
- response=RECIST: as CRPR, PD, or SD
- previous.treatment=prior treatment group
- variant.id=unique identifier corresponding the mutation (genome:chromosome:strand:start:end:referance allele:variant allele)
- gene.hgnc.symbol=HGNC gene symbol
- collapsed.consequences=VEP variant annotation (collapsed to the highest impact)
- variant.HGVSp=HGVSp annotation of mutation
- aa.change=amino acid change
- vaf=tumor VAF

### RNA sequencing (RNAseq)
**RNA-CancerCell-MORRISON1-metadata.tsv**: Metadata file describing samples and subjects that match to RNAseq data.
- sample.id=unique sample identifier
- subject.id=unique subject identifier
- sample.tumor.type=tumor type
- cohort=cohort described in manuscript
- timepoint.id=timepoint of sample in the context of the treatment regimen
- treatment.regimen.name=treatment regimen
- bor=best overall response defined by RECIST
- response=RECIST: as CRPR, PD, or SD
- previous.treatment=prior treatment group
- subject.age=subject age
- subject.sex=subject sex
- sample.freetext.anatomic.site=anatomical site of tumor

**RNA-CancerCell-MORRISON1-immune_signatures-tiara_pd1-all_samples.tsv**: File containing gene, celltype, tiara-pd1, tide, and impres signatures across all samples.
- sample.id=unique sample identifier
- subject.id=unique subject identifier
- response=RECIST: as CRPR, PD, or SD
- previous.treatment=prior treatment group
- BCell=gene signature
- CD8+ Tcell infiltration=gene signature
- cDC1=gene signature
- cytotoxic-activity-khan2018=gene signature
- imsig_B cells=gene signature
- imsig_Macrophages=gene signature
- imsig_Monocytes=gene signature
- imsig_Neutrophils=gene signature
- imsig_NK cells=gene signature
- imsig_Plasma cells=gene signature
- imsig_T cells=gene signature
- mdsc-mahler=gene signature
- myeloid-macrophage-mahler=gene signature
- neutrophil_ox40treated-vs-untreated_avg_logFC0.4-p_val_adj0.1=gene signature
- neutrophil_ox40treated-vs-untreated_subcluster_avg_logFC0.4-p_val_adj0.1=gene signature
- neutrophil-BindeaImmunity2013=gene signature
- STING=gene signature
- Th1=gene signature
- Th17=gene signature
- Th2=gene signature
- TLS=gene signature
- TLS-fDC=gene signature
- TLS-MemoryB=gene signature
- TLS-Tfh=gene signature
- TReg=gene signature
- IMPRES=IMPRES score
- TIDE=TIDE score, computed with prior immunotherapy status considered for samples with prior anti-CTLA-4 experience
- tiara_pd1=TIARA-PD1 score 

**RNA-CancerCell-MORRISON1-immune_signatures-tiara_pd1-cutaneous_melanoma-antiPD1_regimen.tsv**: File containing gene, celltype, tiara-pd1, tide, and impres signatures across all samples corresponding to primary dataset focus in the manuscript: the baseline cutaneous, anti-PD1 treatment regimen, CRPR/PD group.
- sample.id=unique sample identifier
- subject.id=unique subject identifier
- response=RECIST, as CRPR, PD, or SD
- previous.treatment=prior treatment group
- BCell=gene signature
- CD8+ Tcell infiltration=gene signature
- cDC1=gene signature
- cytotoxic-activity-khan2018=gene signature
- imsig_B cells=gene signature
- imsig_Macrophages=gene signature
- imsig_Monocytes=gene signature
- imsig_Neutrophils=gene signature
- imsig_NK cells=gene signature
- imsig_Plasma cells=gene signature
- imsig_T cells=gene signature
- mdsc-mahler=gene signature
- myeloid-macrophage-mahler=gene signature
- neutrophil_ox40treated-vs-untreated_avg_logFC0.4-p_val_adj0.1=gene signature
- neutrophil_ox40treated-vs-untreated_subcluster_avg_logFC0.4-p_val_adj0.1=gene signature
- neutrophil-BindeaImmunity2013=gene signature
- STING=gene signature
- Th1=gene signature
- Th17=gene signature
- Th2=gene signature
- TLS=gene signature
- TLS-fDC=gene signature
- TLS-MemoryB=gene signature
- TLS-Tfh=gene signature
- TReg=gene signature
- IMPRES=IMPRES score
- TIDE=TIDE score, computed with prior immunotherapy status considered for samples with prior anti-CTLA-4 experience
- tiara_pd1=TIARA-PD1 score 

**RNA-CancerCell-MORRISON1-no_batch_correction-logcpm-all_samples.tsv**: Logcpm count data across all samples, without batch correction.
- gene.hgnc.symbol=Gene symbol
- remaining columns=Corresponding sample.id found in metadata file

**RNA-CancerCell-MORRISON1-combat_batch_corrected-logcpm-all_samples.tsv**: Logcpm Batch-corrected data across all samples.
- gene.hgnc.symbol=Gene symbol
- remaining columns=Corresponding sample.id found in metadata file

**RNA-CancerCell-MORRISON1-combat_batch_corrected-logcpm-cutaneous_antiPD1_only.tsv**: Logcpm batch-corrected data corresponding to primary dataset focus in the manuscript: the baseline cutaneous, anti-PD1 treatment regimen, CRPR/PD group.
- gene.hgnc.symbol=Gene symbol
- remaining columns=Corresponding sample.id found in metadata file
